<!-- SPDX-License-Identifier: Apache-2.0 -->

# Fork guide: experimental components and package contracts

This public fork of [apache/opennlp-sandbox](https://github.com/apache/opennlp-sandbox) is documented at [b49147a2df6e](https://github.com/hsoliwal/opennlp-sandbox/tree/b49147a2df6e26ed1e52b17ed192e59afabb9119), inspected 2026-10-14.

**The [upstream README](README.md) explicitly says these components are experimental, not intended for production use and not official ASF releases.** A module or example existing here does not establish production readiness, security support or M3 integration.

[Package evidence and gaps](PACKAGE_INVENTORY.md) · [Contribution guide](.github/CONTRIBUTING.md) · [License](LICENSE) · [Notices](NOTICE)

## Complete Maven project/module map

All 21 POM projects (root plus 20 descendants) were inspected. The actual directory spelling is caseditor, even where historical prose says caseeditor. The parent includes opennlp-brat-annotator as a separate child.

| Manifest | Responsibility and boundary |
| --- | --- |
| [caseditor-corpus-server-plugin/pom.xml](caseditor-corpus-server-plugin/pom.xml) | Eclipse/UIMA CAS editor integration with corpus-server resources; UI selection and corpus access boundary |
| [caseditor-opennlp-plugin/pom.xml](caseditor-opennlp-plugin/pom.xml) | CAS editor background jobs/views for name finding, sentence detection and tokenization; depends on IDE/CAS lifecycle |
| [corpus-server/corpus-server-connector/pom.xml](corpus-server/corpus-server-connector/pom.xml) | UIMA collection reader/writer connectors between CAS processing and corpus-server tasks |
| [corpus-server/corpus-server-core/pom.xml](corpus-server/corpus-server-core/pom.xml) | Corpus REST resources, storage/search contracts and task queues; storage operations have persistent effects |
| [corpus-server/corpus-server-impl/pom.xml](corpus-server/corpus-server-impl/pom.xml) | OSGi bundle with service activation and Derby-backed store implementations; owns persistence/service lifecycle |
| [corpus-server/corpus-server-tools/pom.xml](corpus-server/corpus-server-tools/pom.xml) | Corpus import, backup, creation and task-queue command-line utilities; inspect targets before any mutating operation |
| [corpus-server/pom.xml](corpus-server/pom.xml) | Aggregator of core contracts, store implementation, command-line tools and UIMA connector |
| [mallet-addon/pom.xml](mallet-addon/pom.xml) | Mallet-backed trainer/model adapters including CRF and MaxEnt; external ML library boundary |
| [modelbuilder-addon/pom.xml](modelbuilder-addon/pom.xml) | Model builder parameters, entity/sentence providers and model-validation helpers; file-backed implementations live in impls |
| [nlp-utils/pom.xml](nlp-utils/pom.xml) | Experimental classification, n-gram, language-model, CFG, regression and anomaly utilities; not the core OpenNLP API |
| [opennlp-brat-annotator/pom.xml](opennlp-brat-annotator/pom.xml) | Brat-facing name-finder service/resource adapters; separate annotation-service integration |
| [opennlp-coref/pom.xml](opennlp-coref/pom.xml) | Coreference linking, mentions, resolvers, dictionary/similarity helpers and CLI training/inference |
| [opennlp-dl/pom.xml](opennlp-dl/pom.xml) | Sandbox deeplearning4j adapter and dataset helpers; different implementation/package boundary from the ONNX module in OpenNLP core |
| [opennlp-grpc/opennlp-grpc-api/pom.xml](opennlp-grpc/opennlp-grpc-api/pom.xml) | Protocol schema and generated Java protobuf/gRPC bindings; opennlp.proto is source of truth |
| [opennlp-grpc/opennlp-grpc-service/pom.xml](opennlp-grpc/opennlp-grpc-service/pom.xml) | Server with POS, tokenizer and sentence services; packages shaded opennlp-grpc-server-${project.version}.jar |
| [opennlp-grpc/pom.xml](opennlp-grpc/pom.xml) | Aggregator of schema/generated Java API and service implementation; examples are a separate non-reactor project |
| [opennlp-similarity/pom.xml](opennlp-similarity/pom.xml) | Experimental text similarity, parse-thicket, classification and application utilities; includes web/email/Solr-oriented code, so not all helpers are pure local transforms |
| [opennlp-wsd/pom.xml](opennlp-wsd/pom.xml) | Word-sense disambiguation interfaces, implementations, dataset readers and CLI utilities; sense identifiers depend on configured model/dictionary |
| [pom.xml](pom.xml) | Root POM aggregator: 14 direct children, shared dependencies and validation. Snapshot version 3.0.0-SNAPSHOT; not a consumable all-in-one runtime JAR |
| [summarizer/pom.xml](summarizer/pom.xml) | TextRank, lexical-chain and meta summarization implementations with preprocessing; outputs summaries from text |
| [tagging-server/pom.xml](tagging-server/pom.xml) | OSGi bundle with REST resources for names, POS, sentences and tokens; deployment/service lifecycle differs from gRPC |

## API and lifecycle guides

### Corpus storage is stateful

[CorporaStore](corpus-server/corpus-server-core/src/main/java/org/apache/opennlp/corpus_server/store/CorporaStore.java) must be initialized before other store methods. initialize(String) chooses a database base path; null means the current working directory. createCorpus takes a unique corpus name, type-system bytes and index mapping. getCorpus can return null. dropCorpus permanently removes its data, and shutdown marks the store no longer usable. I/O-bearing operations declare IOException. These are effects and lifecycle obligations, not pure NLP transformations.

Keep storage implementations in [corpus-server-impl](corpus-server/corpus-server-impl/pom.xml) separate from the API/resources and [connector](corpus-server/corpus-server-connector/pom.xml). Storage authentication, concurrency and recovery guarantees need implementation-specific review; this inventory does not establish them. CLI import/backup/delete utilities require careful target selection.

### Coreference separates inference from training

[Linker](opennlp-coref/src/main/java/opennlp/tools/coref/linker/Linker.java) groups Mention arrays into DiscourseEntity arrays via getEntities, and builds MentionContext arrays for features. getMentionFinder/getHeadFinder expose associated collaborators. Training is stateful: setEntities supplies labeled mentions, then train compiles accumulated data and can throw IOException. Do not treat training and inference as interchangeable calls. Existing package docs for mentions, dictionaries, resolvers and similarity are linked in the package inventory.

### Word senses and summaries

[Disambiguator](opennlp-wsd/src/main/java/opennlp/tools/disambiguator/Disambiguator.java) accepts a WSDSample or parallel token/tag/lemma arrays and a token index/span. It returns a sense identifier or list of senses and documents IllegalArgumentException for invalid parameters. Token positions are not character offsets. Validate the concrete implementation's index bounds and dictionary/model requirements; the interface alone does not prove all implementations agree.

[Summarizer.summarize(String, int)](summarizer/src/main/java/opennlp/summarization/Summarizer.java) requires non-null, nonblank text and maxWords greater than zero, and can return an empty string when it derives no summary. TextRank, lexical-chain and meta implementations occupy separate packages. Interface requirements do not establish model quality or identical enforcement by every implementation.

## gRPC protocol, server and generated code

[opennlp.proto](opennlp-grpc/opennlp-grpc-api/opennlp.proto) declares the opennlp package and three services:

- PosTaggerService: Tag, TagWithContext and GetAvailableModels; requests carry token arrays, POS format and model_hash
- TokenizerTaggerService: Tokenize, TokenizePos and GetAvailableModels; inputs are sentence text and model_hash
- SentenceDetectorService: sentDetect, sentPosDetect and GetAvailableModels; outputs are string or span lists

Span messages contain start, end, prob and type; model discovery returns hash, name and locale. POS format includes UD, PENN, UNKNOWN and CUSTOM; the schema notes UD-to-PENN conversion is lossy. Use exact service/method names from the schema, including their case. Generated Java sources and Python bindings should be regenerated from this schema using the [API guide](opennlp-grpc/opennlp-grpc-api/README.md), not treated as independent hand-maintained APIs.

[OpenNLPServer](opennlp-grpc/opennlp-grpc-service/src/main/java/opennlp/OpenNLPServer.java) is the executable entry point. Its actual options are -p/--port (default 7071) and -c/--config, plus standard picocli help/version. Its configuration reader skips blank/comment lines and reads key=value pairs. Source defaults include server.enable_reflection=false and server.max_inbound_message_size=10485760. It registers all three services, starts a listening server, marks readiness, installs a shutdown hook and waits for termination. stop() asks the server to shut down; it does not itself await full termination. Missing/unreadable configuration can exit the process; start can throw.

The [service POM](opennlp-grpc/opennlp-grpc-service/pom.xml) shades an executable named opennlp-grpc-server-3.0.0-SNAPSHOT.jar in that module's target directory. The existing [gRPC README](opennlp-grpc/README.md) includes mixed historical version examples and a -h host argument not declared as a host option by the inspected server; prefer the actual source options and artifact version above. The root requires Java 21, even though this nested README still says 17.

This is a proof-of-concept server. The inspected ServerBuilder construction does not configure TLS/authentication. Keep experiments isolated and use non-sensitive test text; production transport/security/deployment is unresolved, not supplied by these docs.

## Python example project and modules

The separate [pyproject.toml](opennlp-grpc/examples/python-client/pyproject.toml) and [README](opennlp-grpc/examples/python-client/README.md) define the client example. It is not a Maven reactor module and is not counted among the 21 POM projects.

| Python module | Source and behavior |
| --- | --- |
| [main.py](opennlp-grpc/examples/python-client/main.py) | POS demo opens an insecure localhost:7071 channel, lists models, then submits a request using a hard-coded sample hash. Replace/select a hash returned by the running service; the sample does not guarantee that model exists |
| [sentdetect_example.py](opennlp-grpc/examples/python-client/sentdetect_example.py) | run() lists sentence models with a five-second timeout, handles RPC errors/empty results, chooses the first returned model and sends text with a five-second timeout; closes its channel via a context manager |
| [opennlp_pb2.py](opennlp-grpc/examples/python-client/opennlp_pb2.py) | Generated message definitions; schema is authoritative |
| [opennlp_pb2_grpc.py](opennlp-grpc/examples/python-client/opennlp_pb2_grpc.py) | Generated service stubs; schema is authoritative |

These four importable modules are an example script project, not evidence of a separately supported Python distribution. Do not assume the first listed model has the language/domain you need.

## Build and test distinctions

The [root README](README.md) and [POM](pom.xml) specify JDK 21+ and Maven 3.3.9+. The parent selects OpenNLP 3.0.0-M6 and model artifacts 1.3.0 in this snapshot. Requirements in individual modules can add dependencies and resources.

- mvn install: documented whole-reactor build/local installation from the repository root
- mvn -pl opennlp-grpc/opennlp-grpc-service -am test: focused unit lifecycle plus reactor prerequisites; service Surefire excludes *IT.java
- mvn -pl opennlp-grpc/opennlp-grpc-service -am verify: reaches the configured integration-test lifecycle; service tests also copy model JAR resources
- From opennlp-grpc/examples/python-client, the existing README's uv sync and uv run python sentdetect_example.py prepare/run a client against an already running server; that is a separate environment and network operation

No installation, builds, tests, server startup, client calls, model downloads or corpus mutations were performed for this Markdown-only change. Source inspection does not verify a successful service response.

[aws-ec2-testing-scripts](aws-ec2-testing-scripts/README.md) is additional infrastructure tooling, outside the Java package/POM count. It prepares an AMI and launches CloudFormation/EC2 evaluation work, with possible cloud cost and remote side effects. It is not needed merely to read or build these documentation files and was not executed.

## Proposed M3 use, not implemented

Experimental NLP components could be evaluated behind explicit M3 adapters: versioned requests/results, source/model provenance, bounded inputs, declared effects and separate evaluation receipts. Corpus writes, service startup, model training and network utilities need their own operational controls. A gRPC schema or summarizer interface is not an M3 proof or canonicalization system. No such integration is established by this pass.

## Coverage and backlog

The guide covers all 21 Maven projects, the separate Python example project/four modules and cloud evaluation tooling. The package ledger accounts for 74 production and 35 test Java package directories, including generated API bindings; one production type per package was inspected. Five directories have native package docs. These are partial semantic records, not a complete review of every API.

Remaining work includes full package dependency/state/error/test explanations, native package/method docs, consistency fixes for historical gRPC examples, implementation-specific lifecycle/security review and executable validation. No source/build/workflow files changed and no package is claimed fully verified.

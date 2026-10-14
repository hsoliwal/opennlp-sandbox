<!-- SPDX-License-Identifier: Apache-2.0 -->

# Java package evidence and documentation gaps

[Repository guide](FORK_GUIDE.md) · [Source snapshot b49147a2df6e](https://github.com/hsoliwal/opennlp-sandbox/tree/b49147a2df6e26ed1e52b17ed192e59afabb9119) · Inspected 2026-10-14

This inventory accounts for 74 production-source package directories and 35 test-source package directories. The same namespace can appear in multiple Maven modules and is counted separately by owning source root. One representative source file per production package was read and its package declaration checked; 5 directories have a package-info.java or package.html. The presence of a file is not a review of its completeness.

Short quoted excerpts below come from the linked Apache OpenNLP type Javadocs. [LICENSE](LICENSE) and [NOTICE](NOTICE) apply to that source material. A representative type describes only its own contract, not all types in its package. Missing excerpts and missing native package docs are explicit backlog. These rows are structural/entry-point coverage, not a claim of complete semantic documentation. Test filenames establish test location, never passing tests.

## caseditor-corpus-server-plugin

[Build manifest](caseditor-corpus-server-plugin/pom.xml)

| Declared namespace / source directory | Representative type and existing description | Native package documentation | Matching test directory |
| --- | --- | --- | --- |
| [`org.apache.opennlp.corpus_server.caseditor`](caseditor-corpus-server-plugin/src/main/java/org/apache/opennlp/corpus_server/caseditor) | [CorpusExplorerView](caseditor-corpus-server-plugin/src/main/java/org/apache/opennlp/corpus_server/caseditor/CorpusExplorerView.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |

## caseditor-opennlp-plugin

[Build manifest](caseditor-opennlp-plugin/pom.xml)

| Declared namespace / source directory | Representative type and existing description | Native package documentation | Matching test directory |
| --- | --- | --- | --- |
| [`org.apache.opennlp.caseditor`](caseditor-opennlp-plugin/src/main/java/org/apache/opennlp/caseditor) | [ConfirmAnnotationAction](caseditor-opennlp-plugin/src/main/java/org/apache/opennlp/caseditor/ConfirmAnnotationAction.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`org.apache.opennlp.caseditor.namefinder`](caseditor-opennlp-plugin/src/main/java/org/apache/opennlp/caseditor/namefinder) | [ConfidenceSpan](caseditor-opennlp-plugin/src/main/java/org/apache/opennlp/caseditor/namefinder/ConfidenceSpan.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`org.apache.opennlp.caseditor.sentdetect`](caseditor-opennlp-plugin/src/main/java/org/apache/opennlp/caseditor/sentdetect) | [SentenceContentProvider](caseditor-opennlp-plugin/src/main/java/org/apache/opennlp/caseditor/sentdetect/SentenceContentProvider.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`org.apache.opennlp.caseditor.tokenize`](caseditor-opennlp-plugin/src/main/java/org/apache/opennlp/caseditor/tokenize) | [TokenizerJob](caseditor-opennlp-plugin/src/main/java/org/apache/opennlp/caseditor/tokenize/TokenizerJob.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`org.apache.opennlp.caseditor.util`](caseditor-opennlp-plugin/src/main/java/org/apache/opennlp/caseditor/util) | [ContainingConstraint](caseditor-opennlp-plugin/src/main/java/org/apache/opennlp/caseditor/util/ContainingConstraint.java): “Checks if an AnnotationFS is contained by the given AnnotationFS.” | Missing native package doc | No same-path test directory; tests may be elsewhere |

## corpus-server/corpus-server-connector

[Build manifest](corpus-server/corpus-server-connector/pom.xml)

| Declared namespace / source directory | Representative type and existing description | Native package documentation | Matching test directory |
| --- | --- | --- | --- |
| [`org.apache.opennlp.corpus_server.connector`](corpus-server/corpus-server-connector/src/main/java/org/apache/opennlp/corpus_server/connector) | [CSCasWriter](corpus-server/corpus-server-connector/src/main/java/org/apache/opennlp/corpus_server/connector/CSCasWriter.java): “The CSCasWriter writes a CAS into a Corpus Server.” | Missing native package doc | [Tests](corpus-server/corpus-server-connector/src/test/java/org/apache/opennlp/corpus_server/connector) |

## corpus-server/corpus-server-core

[Build manifest](corpus-server/corpus-server-core/pom.xml)

| Declared namespace / source directory | Representative type and existing description | Native package documentation | Matching test directory |
| --- | --- | --- | --- |
| [`org.apache.opennlp.corpus_server`](corpus-server/corpus-server-core/src/main/java/org/apache/opennlp/corpus_server) | [CorpusServer](corpus-server/corpus-server-core/src/main/java/org/apache/opennlp/corpus_server/CorpusServer.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | [Tests](corpus-server/corpus-server-core/src/test/java/org/apache/opennlp/corpus_server) |
| [`org.apache.opennlp.corpus_server.search`](corpus-server/corpus-server-core/src/main/java/org/apache/opennlp/corpus_server/search) | [SearchService](corpus-server/corpus-server-core/src/main/java/org/apache/opennlp/corpus_server/search/SearchService.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`org.apache.opennlp.corpus_server.store`](corpus-server/corpus-server-core/src/main/java/org/apache/opennlp/corpus_server/store) | [CorporaStore](corpus-server/corpus-server-core/src/main/java/org/apache/opennlp/corpus_server/store/CorporaStore.java): “The Corpora Store is the central storage which manages the corpora.” | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`org.apache.opennlp.corpus_server.taskqueue`](corpus-server/corpus-server-core/src/main/java/org/apache/opennlp/corpus_server/taskqueue) | [MemoryTaskQueue](corpus-server/corpus-server-core/src/main/java/org/apache/opennlp/corpus_server/taskqueue/MemoryTaskQueue.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |

## corpus-server/corpus-server-impl

[Build manifest](corpus-server/corpus-server-impl/pom.xml)

| Declared namespace / source directory | Representative type and existing description | Native package documentation | Matching test directory |
| --- | --- | --- | --- |
| [`org.apache.opennlp.corpus_server.impl`](corpus-server/corpus-server-impl/src/main/java/org/apache/opennlp/corpus_server/impl) | [Activator](corpus-server/corpus-server-impl/src/main/java/org/apache/opennlp/corpus_server/impl/Activator.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |

## corpus-server/corpus-server-tools

[Build manifest](corpus-server/corpus-server-tools/pom.xml)

| Declared namespace / source directory | Representative type and existing description | Native package documentation | Matching test directory |
| --- | --- | --- | --- |
| [`org.apache.opennlp.corpus_server.tools`](corpus-server/corpus-server-tools/src/main/java/org/apache/opennlp/corpus_server/tools) | [CASImporter](corpus-server/corpus-server-tools/src/main/java/org/apache/opennlp/corpus_server/tools/CASImporter.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |

## mallet-addon

[Build manifest](mallet-addon/pom.xml)

| Declared namespace / source directory | Representative type and existing description | Native package documentation | Matching test directory |
| --- | --- | --- | --- |
| [`opennlp.addons.mallet`](mallet-addon/src/main/java/opennlp/addons/mallet) | [CRFTrainer](mallet-addon/src/main/java/opennlp/addons/mallet/CRFTrainer.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |

## modelbuilder-addon

[Build manifest](modelbuilder-addon/pom.xml)

| Declared namespace / source directory | Representative type and existing description | Native package documentation | Matching test directory |
| --- | --- | --- | --- |
| [`opennlp.addons.modelbuilder`](modelbuilder-addon/src/main/java/opennlp/addons/modelbuilder) | [DefaultModelBuilderUtil](modelbuilder-addon/src/main/java/opennlp/addons/modelbuilder/DefaultModelBuilderUtil.java): “Utilizes the file-based implementations to produce an NER model from user. The basic processing is such read in the list…” | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`opennlp.addons.modelbuilder.impls`](modelbuilder-addon/src/main/java/opennlp/addons/modelbuilder/impls) | [BaseModelBuilderParams](modelbuilder-addon/src/main/java/opennlp/addons/modelbuilder/impls/BaseModelBuilderParams.java): “Used to pass params through the processing.” | Missing native package doc | No same-path test directory; tests may be elsewhere |

## nlp-utils

[Build manifest](nlp-utils/pom.xml)

| Declared namespace / source directory | Representative type and existing description | Native package documentation | Matching test directory |
| --- | --- | --- | --- |
| [`org.apache.opennlp.utils`](nlp-utils/src/main/java/org/apache/opennlp/utils) | [TrainingExample](nlp-utils/src/main/java/org/apache/opennlp/utils/TrainingExample.java): “A TrainingExample holds some inputs and a corresponding output” | Missing native package doc | [Tests](nlp-utils/src/test/java/org/apache/opennlp/utils) |
| [`org.apache.opennlp.utils.anomalydetection`](nlp-utils/src/main/java/org/apache/opennlp/utils/anomalydetection) | [AnomalyDetectionUtils](nlp-utils/src/main/java/org/apache/opennlp/utils/anomalydetection/AnomalyDetectionUtils.java): “Utility class for anomaly detection” | Missing native package doc | [Tests](nlp-utils/src/test/java/org/apache/opennlp/utils/anomalydetection) |
| [`org.apache.opennlp.utils.cfg`](nlp-utils/src/main/java/org/apache/opennlp/utils/cfg) | [CFGBuilder](nlp-utils/src/main/java/org/apache/opennlp/utils/cfg/CFGBuilder.java): “A builder for ContextFreeGrammars” | Missing native package doc | [Tests](nlp-utils/src/test/java/org/apache/opennlp/utils/cfg) |
| [`org.apache.opennlp.utils.classification`](nlp-utils/src/main/java/org/apache/opennlp/utils/classification) | [NaiveBayesClassifier](nlp-utils/src/main/java/org/apache/opennlp/utils/classification/NaiveBayesClassifier.java): “A Naive Bayes Classifier for classifying objects of type I assigning classes of type O” | Missing native package doc | [Tests](nlp-utils/src/test/java/org/apache/opennlp/utils/classification) |
| [`org.apache.opennlp.utils.languagemodel`](nlp-utils/src/main/java/org/apache/opennlp/utils/languagemodel) | [LanguageModel](nlp-utils/src/main/java/org/apache/opennlp/utils/languagemodel/LanguageModel.java): “A language model can calculate the probability p (between 0 and 1) of a certain set of T objects, given…” | Missing native package doc | [Tests](nlp-utils/src/test/java/org/apache/opennlp/utils/languagemodel) |
| [`org.apache.opennlp.utils.ngram`](nlp-utils/src/main/java/org/apache/opennlp/utils/ngram) | [NGramUtils](nlp-utils/src/main/java/org/apache/opennlp/utils/ngram/NGramUtils.java): “A utility class for calculating probabilities of tri/bi/uni-grams.” | Missing native package doc | [Tests](nlp-utils/src/test/java/org/apache/opennlp/utils/ngram) |
| [`org.apache.opennlp.utils.regression`](nlp-utils/src/main/java/org/apache/opennlp/utils/regression) | [GradientDescentUtils](nlp-utils/src/main/java/org/apache/opennlp/utils/regression/GradientDescentUtils.java): “A utility class for calculating gradient descent.” | Missing native package doc | [Tests](nlp-utils/src/test/java/org/apache/opennlp/utils/regression) |

## opennlp-brat-annotator

[Build manifest](opennlp-brat-annotator/pom.xml)

| Declared namespace / source directory | Representative type and existing description | Native package documentation | Matching test directory |
| --- | --- | --- | --- |
| [`opennlp.bratann`](opennlp-brat-annotator/src/main/java/opennlp/bratann) | [NameFinderAnnService](opennlp-brat-annotator/src/main/java/opennlp/bratann/NameFinderAnnService.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |

## opennlp-coref

[Build manifest](opennlp-coref/pom.xml)

| Declared namespace / source directory | Representative type and existing description | Native package documentation | Matching test directory |
| --- | --- | --- | --- |
| [`opennlp.tools.cmdline.coref`](opennlp-coref/src/main/java/opennlp/tools/cmdline/coref) | [CoreferenceConverterTool](opennlp-coref/src/main/java/opennlp/tools/cmdline/coref/CoreferenceConverterTool.java): “Tool to convert multiple data formats into native OpenNLP Coref training format.” | Missing native package doc | [Tests](opennlp-coref/src/test/java/opennlp/tools/cmdline/coref) |
| [`opennlp.tools.coref`](opennlp-coref/src/main/java/opennlp/tools/coref) | [CorefModel](opennlp-coref/src/main/java/opennlp/tools/coref/CorefModel.java): “This is the default CorefModel implementation.” | [Existing package doc](opennlp-coref/src/main/java/opennlp/tools/coref/package-info.java); completeness not established | [Tests](opennlp-coref/src/test/java/opennlp/tools/coref) |
| [`opennlp.tools.coref.dictionary`](opennlp-coref/src/main/java/opennlp/tools/coref/dictionary) | [Dictionary](opennlp-coref/src/main/java/opennlp/tools/coref/dictionary/Dictionary.java): “Interface to provide dictionary information to the coreference module assuming a hierarchically structured dictionary (such as WordNet) is available.” | [Existing package doc](opennlp-coref/src/main/java/opennlp/tools/coref/dictionary/package-info.java); completeness not established | No same-path test directory; tests may be elsewhere |
| [`opennlp.tools.coref.linker`](opennlp-coref/src/main/java/opennlp/tools/coref/linker) | [Linker](opennlp-coref/src/main/java/opennlp/tools/coref/linker/Linker.java): “A linker provides an interface for finding mentions, #getMentionFinder getMentionFinder, and creating entities out of those mentions, #getEntities getEntities. This…” | Missing native package doc | [Tests](opennlp-coref/src/test/java/opennlp/tools/coref/linker) |
| [`opennlp.tools.coref.mention`](opennlp-coref/src/main/java/opennlp/tools/coref/mention) | [HeadFinder](opennlp-coref/src/main/java/opennlp/tools/coref/mention/HeadFinder.java): “Interface for finding head words in noun phrases and head noun-phrases in parses.” | [Existing package doc](opennlp-coref/src/main/java/opennlp/tools/coref/mention/package-info.java); completeness not established | [Tests](opennlp-coref/src/test/java/opennlp/tools/coref/mention) |
| [`opennlp.tools.coref.resolver`](opennlp-coref/src/main/java/opennlp/tools/coref/resolver) | [CommonNounResolver](opennlp-coref/src/main/java/opennlp/tools/coref/resolver/CommonNounResolver.java): “Resolves coreference between common nouns.” | [Existing package doc](opennlp-coref/src/main/java/opennlp/tools/coref/resolver/package-info.java); completeness not established | No same-path test directory; tests may be elsewhere |
| [`opennlp.tools.coref.sim`](opennlp-coref/src/main/java/opennlp/tools/coref/sim) | [Context](opennlp-coref/src/main/java/opennlp/tools/coref/sim/Context.java): “Specifies the context of a mention for computing gender, number, and semantic compatibility.” | [Existing package doc](opennlp-coref/src/main/java/opennlp/tools/coref/sim/package-info.java); completeness not established | No same-path test directory; tests may be elsewhere |
| [`opennlp.tools.formats.muc`](opennlp-coref/src/main/java/opennlp/tools/formats/muc) | [FullParseCorefEnhancerStream](opennlp-coref/src/main/java/opennlp/tools/formats/muc/FullParseCorefEnhancerStream.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | [Tests](opennlp-coref/src/test/java/opennlp/tools/formats/muc) |
| [`opennlp.tools.lang.english`](opennlp-coref/src/main/java/opennlp/tools/lang/english) | [TreebankNameFinder](opennlp-coref/src/main/java/opennlp/tools/lang/english/TreebankNameFinder.java): “Class is used to create a name finder for English. @deprecated will be removed soon!” | Missing native package doc | No same-path test directory; tests may be elsewhere |

## opennlp-dl

[Build manifest](opennlp-dl/pom.xml)

| Declared namespace / source directory | Representative type and existing description | Native package documentation | Matching test directory |
| --- | --- | --- | --- |
| [`opennlp.tools.dl`](opennlp-dl/src/main/java/opennlp/tools/dl) | [DataReader](opennlp-dl/src/main/java/opennlp/tools/dl/DataReader.java): “This class provides a reader capable of reading training and test datasets from file system for text classifiers. In addition…” | Missing native package doc | [Tests](opennlp-dl/src/test/java/opennlp/tools/dl) |

## opennlp-grpc/opennlp-grpc-api

[Build manifest](opennlp-grpc/opennlp-grpc-api/pom.xml)

| Declared namespace / source directory | Representative type and existing description | Native package documentation | Matching test directory |
| --- | --- | --- | --- |
| [`opennlp`](opennlp-grpc/opennlp-grpc-api/src/main/java/opennlp) | [OpenNLPService](opennlp-grpc/opennlp-grpc-api/src/main/java/opennlp/OpenNLPService.java): “Protobuf enum opennlp.POSTagFormat” | Missing native package doc | No same-path test directory; tests may be elsewhere |

## opennlp-grpc/opennlp-grpc-service

[Build manifest](opennlp-grpc/opennlp-grpc-service/pom.xml)

| Declared namespace / source directory | Representative type and existing description | Native package documentation | Matching test directory |
| --- | --- | --- | --- |
| [`opennlp`](opennlp-grpc/opennlp-grpc-service/src/main/java/opennlp) | [OpenNLPServer](opennlp-grpc/opennlp-grpc-service/src/main/java/opennlp/OpenNLPServer.java): “The OpenNLPServer class implements a gRPC server for providing OpenNLP-based services. It is a command-line application that allows configuration through…” | Missing native package doc | [Tests](opennlp-grpc/opennlp-grpc-service/src/test/java/opennlp) |
| [`opennlp.service`](opennlp-grpc/opennlp-grpc-service/src/main/java/opennlp/service) | [CacheAware](opennlp-grpc/opennlp-grpc-service/src/main/java/opennlp/service/CacheAware.java): “Interface representing a cache-aware component for managing service and model caches. The CacheAware interface defines methods to retrieve and manage…” | Missing native package doc | [Tests](opennlp-grpc/opennlp-grpc-service/src/test/java/opennlp/service) |
| [`opennlp.service.exception`](opennlp-grpc/opennlp-grpc-service/src/main/java/opennlp/service/exception) | [ServiceException](opennlp-grpc/opennlp-grpc-service/src/main/java/opennlp/service/exception/ServiceException.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |

## opennlp-similarity

[Build manifest](opennlp-similarity/pom.xml)

| Declared namespace / source directory | Representative type and existing description | Native package documentation | Matching test directory |
| --- | --- | --- | --- |
| [`opennlp.tools`](opennlp-similarity/src/main/java/opennlp/tools) | [ProfileReaderWriter](opennlp-similarity/src/main/java/opennlp/tools/ProfileReaderWriter.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | [Tests](opennlp-similarity/src/test/java/opennlp/tools) |
| [`opennlp.tools.apps.contentgen.multithreaded`](opennlp-similarity/src/main/java/opennlp/tools/apps/contentgen/multithreaded) | [Fragment](opennlp-similarity/src/main/java/opennlp/tools/apps/contentgen/multithreaded/Fragment.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`opennlp.tools.apps.relevanceVocabs`](opennlp-similarity/src/main/java/opennlp/tools/apps/relevanceVocabs) | [POStags](opennlp-similarity/src/main/java/opennlp/tools/apps/relevanceVocabs/POStags.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`opennlp.tools.apps.review_builder`](opennlp-similarity/src/main/java/opennlp/tools/apps/review_builder) | [MachineTranslationWrapper](opennlp-similarity/src/main/java/opennlp/tools/apps/review_builder/MachineTranslationWrapper.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`opennlp.tools.apps.utils.email`](opennlp-similarity/src/main/java/opennlp/tools/apps/utils/email) | [EmailSender](opennlp-similarity/src/main/java/opennlp/tools/apps/utils/email/EmailSender.java): “Responsible to sending e-mails through a gmail smtp server. It will be extended to handle arbitrary smtp servers.” | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`opennlp.tools.doc_classifier`](opennlp-similarity/src/main/java/opennlp/tools/doc_classifier) | [ClassifierTrainingSetIndexer](opennlp-similarity/src/main/java/opennlp/tools/doc_classifier/ClassifierTrainingSetIndexer.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`opennlp.tools.enron_email_recognizer`](opennlp-similarity/src/main/java/opennlp/tools/enron_email_recognizer) | [EmailNormalizer](opennlp-similarity/src/main/java/opennlp/tools/enron_email_recognizer/EmailNormalizer.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`opennlp.tools.fca`](opennlp-similarity/src/main/java/opennlp/tools/fca) | [BasicLevelMetrics](opennlp-similarity/src/main/java/opennlp/tools/fca/BasicLevelMetrics.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`opennlp.tools.jsmlearning`](opennlp-similarity/src/main/java/opennlp/tools/jsmlearning) | [FeatureSpaceCoverageProcessor](opennlp-similarity/src/main/java/opennlp/tools/jsmlearning/FeatureSpaceCoverageProcessor.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`opennlp.tools.nl2code`](opennlp-similarity/src/main/java/opennlp/tools/nl2code) | [NL2Obj](opennlp-similarity/src/main/java/opennlp/tools/nl2code/NL2Obj.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`opennlp.tools.parse_thicket`](opennlp-similarity/src/main/java/opennlp/tools/parse_thicket) | [ArcType](opennlp-similarity/src/main/java/opennlp/tools/parse_thicket/ArcType.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | [Tests](opennlp-similarity/src/test/java/opennlp/tools/parse_thicket) |
| [`opennlp.tools.parse_thicket.apps`](opennlp-similarity/src/main/java/opennlp/tools/parse_thicket/apps) | [MostFrequentWordsFromPageGetter](opennlp-similarity/src/main/java/opennlp/tools/parse_thicket/apps/MostFrequentWordsFromPageGetter.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | [Tests](opennlp-similarity/src/test/java/opennlp/tools/parse_thicket/apps) |
| [`opennlp.tools.parse_thicket.communicative_actions`](opennlp-similarity/src/main/java/opennlp/tools/parse_thicket/communicative_actions) | [CommunicativeActionsArcBuilder](opennlp-similarity/src/main/java/opennlp/tools/parse_thicket/communicative_actions/CommunicativeActionsArcBuilder.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`opennlp.tools.parse_thicket.matching`](opennlp-similarity/src/main/java/opennlp/tools/parse_thicket/matching) | [GeneralizationResult](opennlp-similarity/src/main/java/opennlp/tools/parse_thicket/matching/GeneralizationResult.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`opennlp.tools.parse_thicket.pattern_structure`](opennlp-similarity/src/main/java/opennlp/tools/parse_thicket/pattern_structure) | [LinguisticPatternStructure](opennlp-similarity/src/main/java/opennlp/tools/parse_thicket/pattern_structure/LinguisticPatternStructure.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | [Tests](opennlp-similarity/src/test/java/opennlp/tools/parse_thicket/pattern_structure) |
| [`opennlp.tools.similarity.apps`](opennlp-similarity/src/main/java/opennlp/tools/similarity/apps) | [BingResponse](opennlp-similarity/src/main/java/opennlp/tools/similarity/apps/BingResponse.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | [Tests](opennlp-similarity/src/test/java/opennlp/tools/similarity/apps) |
| [`opennlp.tools.similarity.apps.solr`](opennlp-similarity/src/main/java/opennlp/tools/similarity/apps/solr) | [Comment](opennlp-similarity/src/main/java/opennlp/tools/similarity/apps/solr/Comment.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`opennlp.tools.similarity.apps.taxo_builder`](opennlp-similarity/src/main/java/opennlp/tools/similarity/apps/taxo_builder) | [AriAdapter](opennlp-similarity/src/main/java/opennlp/tools/similarity/apps/taxo_builder/AriAdapter.java): “This class makes it possible to use old prolog-files as the bases for taxonomy-learner. It cleans the prolog files and…” | Missing native package doc | [Tests](opennlp-similarity/src/test/java/opennlp/tools/similarity/apps/taxo_builder) |
| [`opennlp.tools.similarity.apps.utils`](opennlp-similarity/src/main/java/opennlp/tools/similarity/apps/utils) | [CountItemsList](opennlp-similarity/src/main/java/opennlp/tools/similarity/apps/utils/CountItemsList.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | [Tests](opennlp-similarity/src/test/java/opennlp/tools/similarity/apps/utils) |
| [`opennlp.tools.textsimilarity`](opennlp-similarity/src/main/java/opennlp/tools/textsimilarity) | [EpistemicStatesTrainingSet](opennlp-similarity/src/main/java/opennlp/tools/textsimilarity/EpistemicStatesTrainingSet.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | [Tests](opennlp-similarity/src/test/java/opennlp/tools/textsimilarity) |
| [`opennlp.tools.textsimilarity.chunker2matcher`](opennlp-similarity/src/main/java/opennlp/tools/textsimilarity/chunker2matcher) | [ParserCacheSerializer](opennlp-similarity/src/main/java/opennlp/tools/textsimilarity/chunker2matcher/ParserCacheSerializer.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | [Tests](opennlp-similarity/src/test/java/opennlp/tools/textsimilarity/chunker2matcher) |
| [`opennlp.tools.word2vec`](opennlp-similarity/src/main/java/opennlp/tools/word2vec) | [W2VDistanceMeasurer](opennlp-similarity/src/main/java/opennlp/tools/word2vec/W2VDistanceMeasurer.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |

## opennlp-wsd

[Build manifest](opennlp-wsd/pom.xml)

| Declared namespace / source directory | Representative type and existing description | Native package documentation | Matching test directory |
| --- | --- | --- | --- |
| [`opennlp.tools.cmdline.disambiguator`](opennlp-wsd/src/main/java/opennlp/tools/cmdline/disambiguator) | [DisambiguatorEvaluatorParams](opennlp-wsd/src/main/java/opennlp/tools/cmdline/disambiguator/DisambiguatorEvaluatorParams.java): “Common evaluation parameters. Note: Do not use this class, internal use only!” | Missing native package doc | [Tests](opennlp-wsd/src/test/java/opennlp/tools/cmdline/disambiguator) |
| [`opennlp.tools.cmdline.wsd`](opennlp-wsd/src/main/java/opennlp/tools/cmdline/wsd) | [WSDModelLoader](opennlp-wsd/src/main/java/opennlp/tools/cmdline/wsd/WSDModelLoader.java): “Loads a WSDModel for the command line tools. Note: Do not use this class, internal use only!” | Missing native package doc | [Tests](opennlp-wsd/src/test/java/opennlp/tools/cmdline/wsd) |
| [`opennlp.tools.disambiguator`](opennlp-wsd/src/main/java/opennlp/tools/disambiguator) | [Disambiguator](opennlp-wsd/src/main/java/opennlp/tools/disambiguator/Disambiguator.java): “Describes a word sense disambiguator that determines which sense of a word is meant in a particular context. It is…” | Missing native package doc | [Tests](opennlp-wsd/src/test/java/opennlp/tools/disambiguator) |
| [`opennlp.tools.disambiguator.datareader`](opennlp-wsd/src/main/java/opennlp/tools/disambiguator/datareader) | [Paragraph](opennlp-wsd/src/main/java/opennlp/tools/disambiguator/datareader/Paragraph.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | [Tests](opennlp-wsd/src/test/java/opennlp/tools/disambiguator/datareader) |

## summarizer

[Build manifest](summarizer/pom.xml)

| Declared namespace / source directory | Representative type and existing description | Native package documentation | Matching test directory |
| --- | --- | --- | --- |
| [`opennlp.summarization`](summarizer/src/main/java/opennlp/summarization) | [Summarizer](summarizer/src/main/java/opennlp/summarization/Summarizer.java): “Describes the API of a component which summarizes the content of news, articles or books.” | Missing native package doc | [Tests](summarizer/src/test/java/opennlp/summarization) |
| [`opennlp.summarization.lexicalchaining`](summarizer/src/main/java/opennlp/summarization/lexicalchaining) | [LexicalChain](summarizer/src/main/java/opennlp/summarization/lexicalchaining/LexicalChain.java): “Represents a lexical chain.” | Missing native package doc | [Tests](summarizer/src/test/java/opennlp/summarization/lexicalchaining) |
| [`opennlp.summarization.meta`](summarizer/src/main/java/opennlp/summarization/meta) | [MetaSummarizer](summarizer/src/main/java/opennlp/summarization/meta/MetaSummarizer.java): “A summarizer that combines results from the text rank algorithm and the lexical chaining algorithm. It runs both algorithms and…” | Missing native package doc | [Tests](summarizer/src/test/java/opennlp/summarization/meta) |
| [`opennlp.summarization.preprocess`](summarizer/src/main/java/opennlp/summarization/preprocess) | [DefaultDocProcessor](summarizer/src/main/java/opennlp/summarization/preprocess/DefaultDocProcessor.java): “Parses a document to sentences.” | Missing native package doc | [Tests](summarizer/src/test/java/opennlp/summarization/preprocess) |
| [`opennlp.summarization.textrank`](summarizer/src/main/java/opennlp/summarization/textrank) | [TextRank](summarizer/src/main/java/opennlp/summarization/textrank/TextRank.java): “Implements the TextRank algorithm by Rada Mihalcea and Paul Tarau: TextRank: Bringing Order into Text This basically applies the page…” | Missing native package doc | [Tests](summarizer/src/test/java/opennlp/summarization/textrank) |

## tagging-server

[Build manifest](tagging-server/pom.xml)

| Declared namespace / source directory | Representative type and existing description | Native package documentation | Matching test directory |
| --- | --- | --- | --- |
| [`org.apache.opennlp.tagging_server`](tagging-server/src/main/java/org/apache/opennlp/tagging_server) | [ModelServiceKeys](tagging-server/src/main/java/org/apache/opennlp/tagging_server/ModelServiceKeys.java): “Keys for model services to expose further information about the model. This information will be used to select a suitable…” | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`org.apache.opennlp.tagging_server.namefind`](tagging-server/src/main/java/org/apache/opennlp/tagging_server/namefind) | [BratNameFinderResource](tagging-server/src/main/java/org/apache/opennlp/tagging_server/namefind/BratNameFinderResource.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`org.apache.opennlp.tagging_server.postag`](tagging-server/src/main/java/org/apache/opennlp/tagging_server/postag) | [POSTaggerResource](tagging-server/src/main/java/org/apache/opennlp/tagging_server/postag/POSTaggerResource.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`org.apache.opennlp.tagging_server.sentdetect`](tagging-server/src/main/java/org/apache/opennlp/tagging_server/sentdetect) | [SentenceDetectorResource](tagging-server/src/main/java/org/apache/opennlp/tagging_server/sentdetect/SentenceDetectorResource.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |
| [`org.apache.opennlp.tagging_server.tokenize`](tagging-server/src/main/java/org/apache/opennlp/tagging_server/tokenize) | [TokenizerResource](tagging-server/src/main/java/org/apache/opennlp/tagging_server/tokenize/TokenizerResource.java): No type-level Javadoc summary found; semantic review remains | Missing native package doc | No same-path test directory; tests may be elsewhere |

## Test-only package accounting

The following source-root-relative test packages are indexed independently; no test suite was executed or fully reviewed in this editorial pass. Test classes may exercise multiple packages and model/data dependencies. All remain partial semantic coverage until their fixtures, assertions and execution outcomes are documented.

| Test package directory | Java files |
| --- | --- |
| [corpus-server/corpus-server-connector/src/test/java/org/apache/opennlp/corpus_server/connector](corpus-server/corpus-server-connector/src/test/java/org/apache/opennlp/corpus_server/connector) | 3 |
| [corpus-server/corpus-server-core/src/test/java/org/apache/opennlp/corpus_server/util](corpus-server/corpus-server-core/src/test/java/org/apache/opennlp/corpus_server/util) | 1 |
| [nlp-utils/src/test/java/org/apache/opennlp/utils](nlp-utils/src/test/java/org/apache/opennlp/utils) | 1 |
| [nlp-utils/src/test/java/org/apache/opennlp/utils/anomalydetection](nlp-utils/src/test/java/org/apache/opennlp/utils/anomalydetection) | 1 |
| [nlp-utils/src/test/java/org/apache/opennlp/utils/cfg](nlp-utils/src/test/java/org/apache/opennlp/utils/cfg) | 5 |
| [nlp-utils/src/test/java/org/apache/opennlp/utils/classification](nlp-utils/src/test/java/org/apache/opennlp/utils/classification) | 1 |
| [nlp-utils/src/test/java/org/apache/opennlp/utils/languagemodel](nlp-utils/src/test/java/org/apache/opennlp/utils/languagemodel) | 2 |
| [nlp-utils/src/test/java/org/apache/opennlp/utils/ngram](nlp-utils/src/test/java/org/apache/opennlp/utils/ngram) | 1 |
| [nlp-utils/src/test/java/org/apache/opennlp/utils/regression](nlp-utils/src/test/java/org/apache/opennlp/utils/regression) | 2 |
| [opennlp-coref/src/test/java/opennlp/tools/cmdline/coref](opennlp-coref/src/test/java/opennlp/tools/cmdline/coref) | 3 |
| [opennlp-coref/src/test/java/opennlp/tools/coref](opennlp-coref/src/test/java/opennlp/tools/coref) | 8 |
| [opennlp-coref/src/test/java/opennlp/tools/coref/linker](opennlp-coref/src/test/java/opennlp/tools/coref/linker) | 4 |
| [opennlp-coref/src/test/java/opennlp/tools/coref/mention](opennlp-coref/src/test/java/opennlp/tools/coref/mention) | 5 |
| [opennlp-coref/src/test/java/opennlp/tools/formats/muc](opennlp-coref/src/test/java/opennlp/tools/formats/muc) | 1 |
| [opennlp-dl/src/test/java/opennlp/tools/dl](opennlp-dl/src/test/java/opennlp/tools/dl) | 3 |
| [opennlp-grpc/opennlp-grpc-service/src/test/java/opennlp](opennlp-grpc/opennlp-grpc-service/src/test/java/opennlp) | 1 |
| [opennlp-grpc/opennlp-grpc-service/src/test/java/opennlp/service](opennlp-grpc/opennlp-grpc-service/src/test/java/opennlp/service) | 4 |
| [opennlp-grpc/opennlp-grpc-service/src/test/java/opennlp/service/stubs](opennlp-grpc/opennlp-grpc-service/src/test/java/opennlp/service/stubs) | 1 |
| [opennlp-similarity/src/test/java/opennlp/tools/parse_thicket/apps](opennlp-similarity/src/test/java/opennlp/tools/parse_thicket/apps) | 1 |
| [opennlp-similarity/src/test/java/opennlp/tools/parse_thicket/pattern_structure](opennlp-similarity/src/test/java/opennlp/tools/parse_thicket/pattern_structure) | 1 |
| [opennlp-similarity/src/test/java/opennlp/tools/similarity/apps](opennlp-similarity/src/test/java/opennlp/tools/similarity/apps) | 2 |
| [opennlp-similarity/src/test/java/opennlp/tools/similarity/apps/taxo_builder](opennlp-similarity/src/test/java/opennlp/tools/similarity/apps/taxo_builder) | 3 |
| [opennlp-similarity/src/test/java/opennlp/tools/similarity/apps/utils](opennlp-similarity/src/test/java/opennlp/tools/similarity/apps/utils) | 1 |
| [opennlp-similarity/src/test/java/opennlp/tools/textsimilarity](opennlp-similarity/src/test/java/opennlp/tools/textsimilarity) | 5 |
| [opennlp-similarity/src/test/java/opennlp/tools/textsimilarity/chunker2matcher](opennlp-similarity/src/test/java/opennlp/tools/textsimilarity/chunker2matcher) | 2 |
| [opennlp-wsd/src/test/java/opennlp/tools](opennlp-wsd/src/test/java/opennlp/tools) | 1 |
| [opennlp-wsd/src/test/java/opennlp/tools/cmdline/disambiguator](opennlp-wsd/src/test/java/opennlp/tools/cmdline/disambiguator) | 2 |
| [opennlp-wsd/src/test/java/opennlp/tools/cmdline/wsd](opennlp-wsd/src/test/java/opennlp/tools/cmdline/wsd) | 1 |
| [opennlp-wsd/src/test/java/opennlp/tools/disambiguator](opennlp-wsd/src/test/java/opennlp/tools/disambiguator) | 21 |
| [opennlp-wsd/src/test/java/opennlp/tools/disambiguator/datareader](opennlp-wsd/src/test/java/opennlp/tools/disambiguator/datareader) | 5 |
| [summarizer/src/test/java/opennlp/summarization](summarizer/src/test/java/opennlp/summarization) | 2 |
| [summarizer/src/test/java/opennlp/summarization/lexicalchaining](summarizer/src/test/java/opennlp/summarization/lexicalchaining) | 7 |
| [summarizer/src/test/java/opennlp/summarization/meta](summarizer/src/test/java/opennlp/summarization/meta) | 1 |
| [summarizer/src/test/java/opennlp/summarization/preprocess](summarizer/src/test/java/opennlp/summarization/preprocess) | 1 |
| [summarizer/src/test/java/opennlp/summarization/textrank](summarizer/src/test/java/opennlp/summarization/textrank) | 1 |

## Other source sets and completion gate

No other checked-in Java source set was found in the inspected tree.

The gRPC schema and Python examples are accounted for in the repository guide. Generated bindings are governed by the schema, not by independent hand edits.

To complete a package record, explain purpose, public surface, inputs/outputs/errors, dependencies, state/resource/concurrency constraints and tests for that package. Review all relevant types, reconcile native docs, and execute applicable checks through the approved engineering workflow. This Markdown-only pass does not add package-info.java or change source comments. All 74 production package records remain partial at this semantic completion gate; none is claimed fully verified.

<!-- SPDX-License-Identifier: Apache-2.0 -->

# OpenNLP Sandbox fork: practical workflows

This page is for `hsoliwal/opennlp-sandbox`, a fork of
[apache/opennlp-sandbox](https://github.com/apache/opennlp-sandbox).
Read the root README's [introduction and security disclaimer](../README.md) first:
these components are experimental, not production-ready or official ASF releases.
The [getting-started section](../README.md#getting-started) explains why to select
a component instead of treating the parent POM as one runtime application.

## Navigate by task

| Interest | Starting point |
| --- | --- |
| N-grams and other NLP utilities | [nlp-utils README](../nlp-utils/README.md), [sources](../nlp-utils/src) |
| gRPC proof of concept | [service overview](../opennlp-grpc/README.md), [API schema](../opennlp-grpc/opennlp-grpc-api/README.md), [client examples](../opennlp-grpc/examples/README.md) |
| Text similarity and search experiments | [opennlp-similarity README](../opennlp-similarity/README.md) |
| Coreference and word-sense disambiguation | [opennlp-coref](../opennlp-coref), [opennlp-wsd](../opennlp-wsd) |
| Corpus storage and editor integrations | [corpus-server](../corpus-server), [caseditor-corpus-server-plugin](../caseditor-corpus-server-plugin), [caseditor-opennlp-plugin](../caseditor-opennlp-plugin) |
| Full reactor inventory | [Root POM](../pom.xml) |

Module READMEs provide task-specific context, but the root POM supplies the current
Java/build baseline. Check both before following an older module example.

## Focused command cheat sheet

Use the prerequisites in [Building OpenNLP](../README.md#building-opennlp).
The repository has no Maven wrapper. In a new checkout:

```sh
git clone https://github.com/hsoliwal/opennlp-sandbox.git
cd opennlp-sandbox
git rev-parse HEAD
java -version
mvn -version

# Start with the utility module and its required reactor projects
mvn -pl nlp-utils -am test
```

Other useful selections, also from the repository root:

```sh
# Verify the gRPC service and required reactor projects
mvn -pl opennlp-grpc/opennlp-grpc-service -am verify

# Verify the similarity component and required reactor projects
mvn -pl opennlp-similarity -am verify

# Check a local patch for whitespace mistakes
git diff --check
```

These are alternative scopes, not a mandatory sequence. `-pl` selects the project;
`-am` adds required reactor projects. Builds need dependency downloads, and a
successful focused build does not validate the other sandbox components.
Use the root README for the full build and [Java CI](../.github/workflows/maven.yml)
for the current platform matrix and coverage command.

## gRPC example: inspect the actual executable's help

After successful service packaging, the
[service POM](../opennlp-grpc/opennlp-grpc-service/pom.xml) produces a shaded executable
inside that module's `target` directory. From the repository root:

```sh
java -jar opennlp-grpc/opennlp-grpc-service/target/opennlp-grpc-server-3.0.0-SNAPSHOT.jar --help
```

The filename follows this checkout's project version. The
[server source](../opennlp-grpc/opennlp-grpc-service/src/main/java/opennlp/OpenNLPServer.java)
defines standard help, `-p`/`--port`, and `-c`/`--config`. Its short `-h` option is
help, not a host-binding option: do not copy an older example's `-h 127.0.0.1`
as a way to restrict network exposure.

The module README describes model search settings and client examples. Inspect
the configuration and environment before starting the listener; the help command
above does not start the server. Model setup and a successful client request are
separate steps, and neither turns this proof of concept into a production service.

## Troubleshooting by symptom

- **Java version disagreement:** use the root POM's `java.version=21`. An older
  module README or enforcer message saying Java 17 does not change that configured
  requirement. Check the Java home printed by `mvn -version`.
- **Maven cannot find a project or sibling artifact:** run from the root, use the
  complete module path, and include `-am`. Building a child in isolation may require
  its sibling dependencies to have been installed locally first.
- **Executable JAR not found:** check the service module's `target`, successful
  `package` phase, and current project version rather than the repository root's `target`.
- **gRPC cannot discover models:** review `model.location`, recursive lookup, and
  task-specific wildcard patterns in the module README. Model paths refer to the
  server's working environment.
- **One component builds but another fails:** modules differ in dependencies and
  maturity. Record the component, commit, Java/Maven versions, command, and first
  failing goal so the report can be reproduced at the same scope.

Follow the [contribution guide](../.github/CONTRIBUTING.md) and
[PR checklist](../.github/PULL_REQUEST_TEMPLATE.md).
Commands and paths here were checked against source; Maven tests, coverage, and
server/client execution were not run for this documentation.

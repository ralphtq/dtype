# DTYPE — Datatype Ontology

DTYPE defines datatypes and related constructs that other ontologies reuse:
unions of XSD datatypes (such as `dtype:dateUnion` and `dtype:numericUnion`),
code lists and enumerations, and properties such as `dtype:value`,
`dtype:order` and `dtype:isInvalid`. It imports
[VAEM](https://github.com/ralphtq/vaem) and is imported by
[VOAG](http://voag.linkedmodel.org/schema/voag). QUDT also uses it.

## IRIs

|        What         |                             IRI                              |                       File                       |
|---------------------|--------------------------------------------------------------|--------------------------------------------------|
| Ontology (current)  | `http://www.linkedmodel.org/schema/dtype`                    | `schema/dtype` (RDF/XML, v2.1 content)           |
| Namespace           | `http://www.linkedmodel.org/schema/dtype#` (prefix `dtype:`) |                                                  |
| v1.1                | `http://www.linkedmodel.org/1.1/schema/dtype`                | `1.1/SCHEMA_dtype-v1.1.ttl`                      |
| v1.2                | `http://www.linkedmodel.org/1.2/schema/dtype`                | `1.2/schema/SCHEMA_dtype-v1.2.ttl`               |
| v2.0                | `http://www.linkedmodel.org/2.0/schema/dtype`                | `2.0/schema/SCHEMA_dtype_v2.0.ttlx`              |
| v2.0 SHACL (no OWL) | `http://www.linkedmodel.org/2.0.0/schema/shacl/dtype`        | `2.0/schema/shacl/SCHEMA_dtype_noOWL_v2.0.0.ttl` |

The IRIs are unchanged by the move out of `linkedmodels`.

Two files currently declare the unversioned ontology IRI:

- `schema/dtype` (identical to `2.1/schema/dtype`): RDF/XML, 253 triples, the
  newest content.
- `2.0/schema/dtype.ttl`: Turtle, 242 triples, older content with
  `owl:versionIRI` pointing at v1.2.

## Layout

```
schema/        current (unversioned) DTYPE, RDF/XML
1.1/ 1.2/      earlier versions
2.0/ 2.1/      later versions (see the note on the unversioned IRI above)
2.0/schema/shacl/  SHACL-only version of v2.0
scripts/       parse check
images/        logo
```

## SHACL schema

`2.0/schema/shacl/SCHEMA_dtype_noOWL_v2.0.0.ttl` is a SHACL-only version of
DTYPE 2.0. It imports the VAEM SHACL schema
(`http://www.linkedmodel.org/3.0.0/schema/shacl/vaem`) rather than the OWL
VAEM. It does not yet include `dtype:objectValue` and
`dtype:defaultObjectValue`, which `schema/dtype` (2.1) adds.

## Work in progress

These branches carry DTYPE work that has not yet been merged into `main`:

- `qudt-fixes-rh`: v2.1 as Turtle (`2.1/schema/SCHEMA_dtype_v2.1.ttl` and the
  unversioned `2.1/schema/SCHEMA_dtype.ttl`, which has the same triples as
  `schema/dtype`). Merging it also deletes `2.0/schema/dtype.ttl`.

## Build

DTYPE has no build: the current schema is the RDF/XML file `schema/dtype`, and
the version folders are frozen, so there are no `target/dist` graphs to make.
To check that every RDF file in the repository parses (needs Python 3 with
`rdflib`; a virtual environment in `.venv/` is git-ignored):

```
python3 -m venv .venv
source .venv/bin/activate
python -m pip install rdflib
python3 scripts/check_rdf.py
```

## Formatting

`README.md` and `CHANGELOG.md` are formatted with
[Spotless](https://github.com/diffplug/spotless), using the settings QUDT
uses (`pom.xml`). DTYPE has no Turtle sources to format: the current schema
is RDF/XML and the version folders are frozen.

You need Java 25 and Maven 3.6.3 or later. From the top of the repository,
`mvn spotless:check` lists the files that need formatting and
`mvn spotless:apply` formats them in place.

The **Format** workflow on GitHub runs `spotless:check` on every push and
pull request, and fails if a file is not formatted. To format on GitHub
instead, run it from the Actions tab with "apply" ticked: it formats the
files and commits the result to the branch.

## History

DTYPE was previously maintained in
[ralphtq/linkedmodels](https://github.com/ralphtq/linkedmodels) under
`dtype/`. Its full commit history was carried over when it moved here.

## License

The ontology metadata declares DTYPE to be issued under the Creative Commons
Attribution-ShareAlike 3.0 United States license. The license for this
repository is under review.

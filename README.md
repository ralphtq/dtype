# DTYPE — Datatype Ontology

DTYPE defines datatypes and related constructs that other ontologies reuse:
unions of XSD datatypes (such as `dtype:dateUnion` and `dtype:numericUnion`),
code lists and enumerations, and properties such as `dtype:value`,
`dtype:order` and `dtype:isInvalid`. It imports
[VAEM](https://github.com/ralphtq/vaem) and is imported by
[VOAG](http://voag.linkedmodel.org/schema/voag). QUDT also uses it.

## IRIs

| What | IRI | File |
|---|---|---|
| Ontology (current) | `http://www.linkedmodel.org/schema/dtype` | `schema/dtype` (RDF/XML, v2.1 content) |
| Namespace | `http://www.linkedmodel.org/schema/dtype#` (prefix `dtype:`) | |
| v1.1 | `http://www.linkedmodel.org/1.1/schema/dtype` | `1.1/SCHEMA_dtype-v1.1.ttl` |
| v1.2 | `http://www.linkedmodel.org/1.2/schema/dtype` | `1.2/schema/SCHEMA_dtype-v1.2.ttl` |
| v2.0 | `http://www.linkedmodel.org/2.0/schema/dtype` | `2.0/schema/SCHEMA_dtype_v2.0.ttlx` |

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
doc/           generated HTML documentation (2015, for v1.2)
images/        logo
```

## Work in progress

These branches carry DTYPE work that has not yet been merged into `main`:

- `qudt-fixes-rh`: v2.1 as Turtle (`2.1/schema/SCHEMA_dtype_v2.1.ttl` and the
  unversioned `2.1/schema/SCHEMA_dtype.ttl`, which has the same triples as
  `schema/dtype`). Merging it also deletes `2.0/schema/dtype.ttl`.
- `shacl-schemas`: SHACL-only (no OWL) version,
  `2.0/schema/shacl/SCHEMA_dtype_noOWL_v2.0.0.ttl`

## History

DTYPE was previously maintained in
[ralphtq/linkedmodels](https://github.com/ralphtq/linkedmodels) under
`dtype/`. Its full commit history was carried over when it moved here.

## License

The ontology metadata declares DTYPE to be issued under the Creative Commons
Attribution-ShareAlike 3.0 United States license. The license for this
repository is under review.

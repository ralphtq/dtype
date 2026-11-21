# Changelog

## Unreleased

- Moved DTYPE out of `ralphtq/linkedmodels` into its own repository, with its
  full commit history. IRIs are unchanged.
- Removed the generated HTML documentation (`doc/2015`). It remains in the
  history.
- Linkedmodels is now the owner and steward (`vaem:LinkedModels`), replacing
  TopQuadrant.
- 1.1: every construct has a single `rdfs:isDefinedBy`.
- Added the SHACL-only schema `2.0/schema/shacl/SCHEMA_dtype_noOWL_v2.0.0.ttl`,
  which imports the VAEM SHACL schema.
- Added a GitHub Action that checks every Turtle and RDF/XML file parses.


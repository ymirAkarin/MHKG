# Metal Exposure Health Knowledge Graph (MHKG)

This repository contains the graph data and RDF/XML ontology accompanying the MHKG manuscript. The graph is the `connectivity_20260916` publication export, with 46,384 nodes and 60,663 relationships. The files are UTF-8 encoded.

| File | Contents | Records |
| --- | --- | ---: |
| `nodes.csv` | Canonical entity identifiers, labels, ontology classes, and entity properties | 46,384 |
| `relationships.csv` | Directed relationships between canonical entities | 60,663 |
| `relation_provenance.csv` | Source and evidence records for the relationships | 76,041 |
| `Metal Exposure Health Ontology.rdf` | RDF/XML ontology for the graph schema | 26 classes; 16 object properties |

## How the files connect

- `nodes.csv`: `canonical_id:ID` uniquely identifies a node; `:LABEL` contains its most specific ontology class.
- `relationships.csv`: `:START_ID` and `:END_ID` refer to `nodes.csv`; `:TYPE` is a predicate declared in the RDF ontology; `relation_id` identifies a relationship.
- `relation_provenance.csv`: `relation_id` refers to `relationships.csv`. A relationship may have multiple provenance records. `evidence_text` is the supporting excerpt, while `source_json` contains source metadata.
- The ontology namespace is `http://www.metal_exposure_health.com/ontology#`. Subclasses in the RDF ontology roll up to their parent classes.

The source articles remain with their original publishers. The repository contains graph data and evidence excerpts, rather than source documents or extraction prompts.

## Integrity

The graph export was checked for unique node and relationship identifiers, valid relationship endpoints, complete provenance links, and correspondence between the CSV class and predicate names and the RDF ontology.

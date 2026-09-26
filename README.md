# Metal Exposure Health Knowledge Graph (MHKG)

## What is MHKG

The Metal-Health Knowledge Graph (MHKG) is a structured and auditable dataset designed to organize literature extraction results on metal exposure and related health effects into a queryable knowledge resource. It links exposure factors with biological responses, health outcomes, and intervention measures, while retaining links between relationships and their original articles and supporting paragraphs.

MHKG addresses these challenges by using a unified schema to organize heterogeneous entities and relationships, with cross-document entity standardization and evidence verification making the graph more coherent and the content more accessible for auditing. MHKG support evidence-oriented retrieval, knowledge exploration, as well as future knowledge-enhanced applications.

This repository contains the graph data and RDF/XML ontology accompanying the MHKG manuscript, with 46,384 nodes and 60,663 relationships. The files are UTF-8 encoded.

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
- The ontology namespace is `http://www.metal_exposure_health.com/ontology#`.

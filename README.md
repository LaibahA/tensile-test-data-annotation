# Tensile Testing Data Annotation

This project uses ontologies to annotate tensile testing data and create machine-readable RDF knowledge graphs. The data comes from the [Tensile Test Project on Zenodo](https://zenodo.org/records/19007867) and is mapped to terms from the Tensile Test Ontology (TTO), PMD Core Ontology, and other vocabularies.

**Acknowledgment:** Based on the tensile testing ontology and annotation script developed by Markus Schilling (BAM, Germany).

## Scripts

- **Demo:** Uses the sample data included in the demo folder. No manual dataset download is needed.
- **Standalone:** Downloads and extracts the dataset from Zenodo automatically if it is not already available locally.

Both scripts validate JSON input files, annotate the data using ontology terms, and generate an RDF knowledge graph and CSV files containing force–elongation measurements.

## Requirements

Python 3 and the packages `requests`, `rdflib`, and `jsonschema`.

Install dependencies from the repository directory:

```bash
python -m pip install -r requirements.txt
```

## How to Run

Run the desired script from its respective project directory:

- **Demo:** `python demo.py`
- **Standalone:** `python ontology_based_knowledge_graph_generation.py`

The standalone script requires an internet connection to download the dataset from Zenodo if it is not already available locally.

## Outputs

Generated files are saved under `annotatedOutputs/`:

- **Turtle (`.ttl`)** — RDF knowledge graph
- **JSON-LD (`.jsonld`)** — RDF knowledge graph in JSON-LD format
- **CSV (`.csv`)** — Force and elongation measurements for individual tests

The knowledge graph files are named `annotated_all_tests.ttl` and `annotated_all_tests.jsonld`.

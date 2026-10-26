# Cybersecurity Mini RAG Project

A small retrieval-augmented generation (RAG) system built for **IT7075C: Applied Artificial Intelligence for Cybersecurity**. The project indexes a custom cybersecurity knowledge base, retrieves relevant passages for a question, and either answers with supporting context or refuses when the corpus does not contain enough evidence.

The full implementation, experiments, outputs, and visualizations are contained in [`rag_notebook.ipynb`](rag_notebook.ipynb).

## What the project does

The notebook implements the complete RAG workflow:

1. Loads Markdown and text documents from the project knowledge base.
2. Splits documents into overlapping chunks.
3. Creates normalized embeddings with `sentence-transformers`.
4. Stores and searches vectors in ChromaDB using cosine distance.
5. Filters weak retrievals with a configurable distance threshold.
6. Builds a grounded prompt from the retrieved passages.
7. Generates an answer with OpenAI when `OPENAI_API_KEY` is available, or runs in offline mode without an API key.
8. Evaluates retrieval quality against answerable and unanswerable gold-set questions.

## Knowledge base

The custom corpus covers six cybersecurity areas:

- Network security and cryptography
- Identity, access control, and zero trust
- Malware and social engineering
- Detection and incident response
- Cloud security
- General cybersecurity concepts

The files in [`my_kb/`](my_kb/) are the primary custom documents. [`my_kb/SOURCES.md`](my_kb/SOURCES.md) records source metadata and is intentionally excluded from indexing.

## Experiment summary

The notebook compares 11 configurations by varying chunk size, top-k retrieval, and maximum cosine distance. Each configuration is scored on:

- **Hit rate:** answerable questions whose exact evidence was retrieved.
- **Refusal rate:** unanswerable questions that correctly returned no context.
- **Balanced score:** the average of hit rate and refusal rate.

The baseline configuration uses a 600-character chunk size, 100-character overlap, `k=4`, and a maximum distance of `0.75`. Its saved notebook run retrieved all 6 answerable questions and correctly refused both unanswerable questions, producing a balanced score of `1.0`.

## Project structure

```text
.
├── rag_notebook.ipynb          # RAG implementation, evaluation, and charts
├── my_kb/                      # Custom cybersecurity knowledge base
│   ├── 01_network_and_cryptography.md
│   ├── 02_identity_and_zero_trust.md
│   ├── 03_malware_and_social_engineering.md
│   ├── 04_detection_and_incident_response.md
│   ├── 05_cloud_security.md
│   └── SOURCES.md
├── goldset.json                # Custom evaluation questions and evidence
├── baseline_goldset.json       # Course-pipeline evaluation set
├── goldset_template.json       # Gold-set authoring template
├── cybersecurity_kb.md         # General cybersecurity reference document
└── ssrf.txt                    # Course SSRF reference document
```

Running the experiment cells also creates `results.csv` and `rag_experiment_chart.png`.

## Requirements

- Python 3.10 or newer
- Jupyter Notebook or JupyterLab
- `chromadb`
- `sentence-transformers`
- `pandas`
- `matplotlib`
- `openai` (optional, only for API-backed answer generation)

## Run the project

1. Clone the repository and enter the project directory.
2. Create and activate a virtual environment.
3. Install the dependencies:

   ```bash
   python -m pip install jupyter chromadb sentence-transformers pandas matplotlib openai
   ```

4. Start Jupyter:

   ```bash
   jupyter notebook rag_notebook.ipynb
   ```

5. Run the notebook from top to bottom.

The embedding and retrieval stages run locally. To enable OpenAI-backed generation, set an API key in your shell before starting Jupyter:

```bash
export OPENAI_API_KEY="your-api-key"
```

Do not place API keys directly in the notebook or commit them to the repository.

## Evaluation data format

Each entry in `goldset.json` contains a question, whether it is answerable from the corpus, and an exact evidence phrase for answerable questions. The notebook verifies that each evidence phrase exists in the source documents before scoring retrieval results.

## Reproducibility note

Embedding-model versions and platform differences can cause small changes in cosine distances. Use the same model and notebook configuration when comparing experiment results.

# RAG Assignment: Baseline vs. Re-Ranking

Comparison of two retrieval pipelines over the FIDE Laws of Chess (`LawsOfChess.pdf`):

1. **Baseline** – Bi-Encoder (`all-MiniLM-L6-v2`) + FAISS retrieves the Top 10 chunks; the Top 3 go to the LLM → *Answer 1*
2. **Re-Ranking** – Cross-Encoder (`ms-marco-MiniLM-L-6-v2`) re-scores the same 10; the new Top 3 go to the LLM → *Answer 2*

The LLM is `llama3` running locally through Ollama.

## Files

| File | Description |
|---|---|
| `rag_reranking.ipynb` | All code: chunking, indexing, both pipelines, failure-mode analysis, latency profiling |
| `report.tex` | Report (compile on Overleaf) |
| `LawsOfChess.pdf` | Source document |

## How to run

```bash
# 1. Install and start Ollama, then pull the LLM
ollama pull llama3

# 2. Open the notebook and run all cells (the first cell installs the Python packages)
jupyter notebook rag_reranking.ipynb
```

**Author:** Kushal Mukherjee (2025201072)

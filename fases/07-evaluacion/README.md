# Fase 7 — Evaluación

Evaluación del sistema RAG completo, en cinco bloques independientes:

- `01-metricas-retrieval/` — Precision@K, Recall@K, F1, MRR, NDCG@K sobre el índice de Pinecone.
- `02-metricas-sentimiento/` — evaluación del análisis de sentimiento financiero (Claude Sonnet
  vs. Gemma), con generación de predicciones, checkpoints y resultados por modelo.
- `03-metricas-financieras/` — métricas de impacto financiero del sistema.
- `04-embeddings-espacio-latente/` — evaluación de embeddings y proyección del espacio latente.
- `05-validacion-temporal-robustez/` — validación temporal (walk-forward) y robustez.

Cada notebook requiere `PINECONE_API_KEY` y, según el bloque, `ANTHROPIC_API_KEY`/
`GEMINI_API_KEY` (ver `.env.example` en la raíz del repo).

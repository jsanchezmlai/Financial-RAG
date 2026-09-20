# 7.4 — Evaluación de embeddings y espacio latente

**Entrada**: vectores e IDs reales del índice de Pinecone (leídos directamente vía
`index.list()`/`fetch()`, no dependen del CSV local de metadatos).
**Proceso**: `evaluacion_embeddings_RAG.ipynb` — proyección del espacio latente (UMAP) y
métricas de calidad de embeddings, agrupadas por periodo/sector/régimen de mercado.
**Salida**: `resultados_embeddings.xlsx`, `proyeccion_embeddings.png`.

Nota: el `embeddings_metadata.csv` original (~1.8 MB) no está versionado aquí por peso; se
regenera desde la Fase 6.

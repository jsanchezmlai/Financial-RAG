# 7.1 — Métricas de evaluación del sistema RAG (Recuperación)

**Entrada**: `golden_dataset.json` (63 consultas con ground truth de relevancia graduada 0–3),
índice de Pinecone poblado en la Fase 6.
**Proceso**: `evaluacion_retrieval_RAG.ipynb` — recupera los top-K nodos por consulta y calcula
Precision@K, Recall@K, F1, MRR y NDCG@K para K=5 y K=10.
**Salida**: `resultados_retrieval_resumen.csv`, `resultados_retrieval_detalle.csv`,
`metricas_retrieval.png`.

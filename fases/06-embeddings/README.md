# Fase 6 — Generación de embeddings

**Entrada**: nodos segmentados de la Fase 5.
**Proceso**: generación de embeddings con BGE-M3 e indexación en Pinecone
(`fase6_bge_m3_pinecone_v2.ipynb`). Requiere `PINECONE_API_KEY` (ver `.env.example` en la raíz).
**Salida**: índice de Pinecone cargado con los vectores. El backup local de embeddings no está
versionado aquí por peso.

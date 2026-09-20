# 7.2 — Métricas de análisis del sentimiento financiero

**Entrada**: `sentiment_ground_truth.csv`.
**Proceso**:
- `generaciones-predicciones/` genera predicciones de sentimiento con Claude Sonnet 5 y Gemma.
- `checkpoints-gemma/` son checkpoints intermedios de esa generación (Gemma).
- `predicciones-generadas/` son las predicciones finales por modelo.
- `evaluacion_sentimiento_RAG.ipynb` compara predicciones contra el ground truth.

**Salida**: `resultados-evaluacion/` — matriz de confusión y resultados detallados/resumen por
modelo (Gemma, Sonnet).

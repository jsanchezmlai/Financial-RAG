# RAG Financiero sobre Noticias

Pipeline RAG (Retrieval-Augmented Generation) sobre noticias financieras: scraping de noticias vía
Exa, limpieza, enriquecimiento de metadatos, segmentación, generación de embeddings, indexación en
Pinecone y evaluación del sistema (recuperación, sentimiento, impacto financiero, embeddings y
robustez temporal). Trabajo Fin de Máster (TFM).

## Stack

- **Scraping**: [Exa](https://exa.ai/) (`exa_py`)
- **Vector store**: [Pinecone](https://www.pinecone.io/)
- **Embeddings**: `BAAI/bge-m3` (vía `sentence-transformers` / `FlagEmbedding`)
- **Segmentación**: LlamaIndex (`llama-index-core`)
- **Generación / predicciones**: Claude (Sonnet), Gemini, Gemma
- **Evaluación**: pandas, scikit-learn, matplotlib, seaborn, UMAP

## Estructura del pipeline

```
fases/
├── 00-scrapeo-noticias/               Scraping de noticias financieras vía Exa
├── 01-limpieza-estructural/          Limpieza inicial del scraping
├── 02-eliminacion-noticias-vacias/   Filtrado de noticias vacías/inválidas
├── 03-enriquecimiento-metadatos/     Enriquecimiento de metadatos (ticker, sector, periodo...)
├── 04-formateo-splitter/             Limpieza/formateo previo a la segmentación
├── 05-segmentacion/                  Chunking con LlamaIndex + BGE-M3
├── 06-embeddings/                    Generación de embeddings e indexación en Pinecone
└── 07-evaluacion/
    ├── 01-metricas-retrieval/            Precision@K, Recall@K, F1, MRR, NDCG@K
    ├── 02-metricas-sentimiento/          Evaluación del análisis de sentimiento financiero
    ├── 03-metricas-financieras/          Métricas de impacto financiero del sistema
    ├── 04-embeddings-espacio-latente/    Evaluación de embeddings y espacio latente
    └── 05-validacion-temporal-robustez/  Validación temporal (walk-forward) y robustez
```

Cada carpeta de fase tiene su propio `README.md` con entrada → proceso → salida.

## Cómo reproducir

Los notebooks fueron desarrollados en Google Colab pero funcionan también en local:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
cp .env.example .env   # y rellena tus claves
```

Cada notebook intenta primero leer credenciales desde `google.colab.userdata`; si no está
disponible (entorno local), pide la clave por `getpass`/variable de entorno. Variables usadas
(ver `.env.example`): `EXA_API_KEY`, `PINECONE_API_KEY`, `PINECONE_INDEX_NAME`,
`ANTHROPIC_API_KEY`, `GEMINI_API_KEY`.

## Datos

Los datasets intermedios grandes (noticias scrapeadas, nodos segmentados, backup de embeddings)
no están versionados aquí por peso: son regenerables ejecutando los notebooks de cada fase en
orden. Se conservan como muestra/ground truth los datasets pequeños necesarios para reproducir
la evaluación (`golden_dataset.json`, `sentiment_ground_truth.csv`, `financial_ground_truth.csv`,
etc.).

## Resultados clave (Fase 7 — Evaluación)

Ver el `README.md` de cada subcarpeta de `fases/07-evaluacion/` y los `.csv`/`.xlsx`/`.png` con
resultados detallados de retrieval, sentimiento, impacto financiero, embeddings y robustez
temporal.

## Memoria y defensa

La memoria completa del TFM y las diapositivas de defensa no están en este repositorio.

## Licencia

MIT — ver [LICENSE](LICENSE). Las noticias scrapeadas usadas como fuente de datos pertenecen a
sus medios de origen; revisa restricciones de reutilización antes de redistribuir el dataset
completo.

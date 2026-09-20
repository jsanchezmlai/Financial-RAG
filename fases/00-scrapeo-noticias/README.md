# Fase 0 — Scrapeo de noticias

**Entrada**: consultas a la API de [Exa](https://exa.ai/) (`exa_py`), definidas por índice/sector y
periodo de mercado.
**Proceso**: `scraping_noticias.ipynb` recupera noticias financieras vía Exa para varios universos
y regímenes de mercado:

- Índices: S&P 500, NASDAQ 100, Euro Stoxx 50
- Sectores: Turismo y aerolíneas, Defensa, Energía, Semiconductores
- Régimen de mercado: periodos de subidas y periodos de lateralización, por cada índice/sector

Requiere `EXA_API_KEY` (ver `.env.example` en la raíz del repo).

**Salida**: `noticias.json` — documentos scrapeados en bruto, usados como entrada de la
[Fase 1](../01-limpieza-estructural/). No versionado aquí por peso; se regenera ejecutando este
notebook.

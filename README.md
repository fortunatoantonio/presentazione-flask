# Dashboard ARIMA — Presentazione Architettura Flask

Presentazione interattiva in HTML che documenta l'architettura del progetto **Dashboard ARIMA**: un'applicazione web Flask per l'analisi automatica di serie temporali con modelli ARIMA/SARIMA.

Il repository contiene un unico file autonomo, senza dipendenze da installare: apri il file nel browser e la presentazione è pronta.

## Contenuto

La presentazione copre **30 slide** organizzate in 12 sezioni principali:

| # | Sezione | Argomento |
|---|---------|-----------|
| 01 | Panoramica | Cos'è Dashboard ARIMA e funzionalità principali |
| 02 | Stack tecnologico | Flask, SQLAlchemy, statsmodels, matplotlib, ecc. |
| 03 | Struttura directory | Organizzazione `backend/`, `frontend/`, `data/` |
| 04 | Monolite ben strutturato | Separazione layer, service layer, ORM, config, utilities |
| 05 | `app.py` | Application Factory pattern |
| 06 | `routes.py` | Blueprint e API REST |
| 07 | `models.py` | Modelli ORM SQLAlchemy |
| 08 | `services.py` | Logica di business |
| 09 | `ai_service.py` | Analisi ACF/PACF e suggerimenti modello |
| 10 | `database.py` | Configurazione SQLite |
| 11 | Flusso dati | Percorso richiesta → risposta |
| 12 | Principi e produzione | Best practice, miglioramenti, evoluzione, glossario |

### Cosa documenta Dashboard ARIMA

L'applicazione descritta nella presentazione (non inclusa in questo repo) offre:

- Upload file CSV/XLSX con colonne `data` e `y`
- Visualizzazione interattiva della serie temporale
- Trasformazioni (smoothing, logaritmo, differenziazione)
- Analisi ACF/PACF con suggerimenti automatici del modello
- Split training/test configurabile
- Selezione automatica del miglior modello (R², MAPE)
- Output completo (coefficienti, p-values, intervalli di confidenza)
- Export in PDF, Excel, JSON e paper HTML

### Stack tecnologico documentato

| Componente | Tecnologia |
|------------|------------|
| Backend | Flask 3.x |
| Database | SQLite + SQLAlchemy |
| Autenticazione | Flask-Login + Werkzeug |
| Analisi statistica | statsmodels, pandas, numpy |
| Visualizzazione | matplotlib |
| Frontend | Jinja2 + JavaScript |
| Configurazione | python-dotenv |

## Avvio rapido

```bash
# Clona il repository
git clone https://github.com/fortunatoantonio/presentazione-flask.git
cd presentazione-flask

# Apri la presentazione nel browser (macOS)
open PRESENTAZIONE_DASHBOARD_FLASK.html
```

In alternativa, fai doppio clic sul file oppure trascinalo nella finestra del browser.

Non serve un server web: il file è completamente standalone (HTML, CSS e JavaScript incorporati). I font Google (Outfit, JetBrains Mono) vengono caricati da CDN.

## Navigazione

| Azione | Controllo |
|--------|-----------|
| Slide successiva | `↓` · `Spazio` · scroll |
| Slide precedente | `↑` |
| Prima slide | `Home` |
| Ultima slide | `End` |
| Schermo intero | `F11` o pulsante in basso a destra |
| Salto a sezione | Link nell'indice (slide 02) |

Le slide usano **scroll snap** per un effetto tipo presentazione. Su mobile lo snap è meno rigido per una navigazione più fluida.

## Struttura del repository

```
presentazione-flask/
└── PRESENTAZIONE_DASHBOARD_FLASK.html   # Presentazione completa (30 slide)
```

## Architettura del progetto documentato

La presentazione illustra la struttura di un monolite Flask ben organizzato:

```
dash/
├── backend/          # app.py, routes.py, models.py, services.py, ...
├── frontend/         # templates/ e static/
├── data/             # uploads/ e exports/
├── automation/       # scheduler
├── instance/         # dash.db (SQLite)
├── requirements.txt
└── .gitignore
```

Principi architetturali evidenziati: Application Factory, Blueprint, Service Layer, ORM, config centralizzata da `.env`, utilities DRY e separazione backend/frontend.
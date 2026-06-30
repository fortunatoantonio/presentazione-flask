# Dashboard ARIMA — Flask Architecture Presentation


Interactive HTML presentation documenting the architecture of **Dashboard ARIMA**: a Flask web application for automatic time series analysis with ARIMA/SARIMA models.

This repository contains a single self-contained file with no dependencies to install—open it in your browser and the presentation is ready.

## Contents

The presentation includes **30 slides** organized into 12 main sections:

| # | Section | Topic |
|---|---------|-------|
| 01 | Overview | What Dashboard ARIMA is and its main features |
| 02 | Tech stack | Flask, SQLAlchemy, statsmodels, matplotlib, etc. |
| 03 | Directory structure | `backend/`, `frontend/`, `data/` layout |
| 04 | Well-structured monolith | Layer separation, service layer, ORM, config, utilities |
| 05 | `app.py` | Application Factory pattern |
| 06 | `routes.py` | Blueprint and REST API |
| 07 | `models.py` | SQLAlchemy ORM models |
| 08 | `services.py` | Business logic |
| 09 | `ai_service.py` | ACF/PACF analysis and model suggestions |
| 10 | `database.py` | SQLite configuration |
| 11 | Data flow | Request → response path |
| 12 | Principles & production | Best practices, improvements, evolution, glossary |

### What Dashboard ARIMA documents

The application described in the presentation (not included in this repo) provides:

- CSV/XLSX upload with `data` and `y` columns
- Interactive time series visualization
- Transformations (smoothing, log, differencing)
- ACF/PACF analysis with automatic model suggestions
- Configurable training/test split
- Automatic best-model selection (R², MAPE)
- Full output (coefficients, p-values, confidence intervals)
- Export to PDF, Excel, JSON, and HTML paper

### Documented tech stack

| Component | Technology |
|-----------|------------|
| Backend | Flask 3.x |
| Database | SQLite + SQLAlchemy |
| Authentication | Flask-Login + Werkzeug |
| Statistical analysis | statsmodels, pandas, numpy |
| Visualization | matplotlib |
| Frontend | Jinja2 + JavaScript |
| Configuration | python-dotenv |

## Quick start

```bash
# Clone the repository
git clone https://github.com/fortunatoantonio/presentazione-flask.git
cd presentazione-flask

# Open the presentation in your browser (macOS)
open PRESENTAZIONE_DASHBOARD_FLASK.html
```

Alternatively, double-click the file or drag it into your browser window.

No web server is required—the file is fully standalone (embedded HTML, CSS, and JavaScript). Google fonts (Outfit, JetBrains Mono) are loaded from a CDN.

## Navigation

| Action | Control |
|--------|---------|
| Next slide | `↓` · `Space` · scroll |
| Previous slide | `↑` |
| First slide | `Home` |
| Last slide | `End` |
| Full screen | `F11` or button at bottom right |
| Jump to section | Links in the table of contents (slide 02) |

Slides use **scroll snap** for a presentation-like experience. On mobile, snap is less strict for smoother navigation.

## Repository structure

```
presentazione-flask/
└── PRESENTAZIONE_DASHBOARD_FLASK.html   # Full presentation (30 slides)
```

## Documented project architecture

The presentation illustrates the structure of a well-organized Flask monolith:

```
dash/
├── backend/          # app.py, routes.py, models.py, services.py, ...
├── frontend/         # templates/ and static/
├── data/             # uploads/ and exports/
├── automation/       # scheduler
├── instance/         # dash.db (SQLite)
├── requirements.txt
└── .gitignore
```

Highlighted architectural principles: Application Factory, Blueprint, Service Layer, ORM, centralized `.env` config, DRY utilities, and backend/frontend separation.

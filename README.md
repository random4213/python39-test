# pyco — Basic FastAPI app

A small, clean FastAPI starter project that demonstrates a maintainable structure (settings + routers) while staying minimal.

## What’s included

- FastAPI application factory
- Versioned API router (`/api/v1`)
- Health endpoint (`/api/v1/health`)
- Example "items" endpoints
- Settings via environment variables (Pydantic Settings)

## Project layout

```
.
├── app/
│   ├── __init__.py
│   ├── main.py
│   ├── core/
│   │   ├── __init__.py
│   │   └── config.py
│   └── api/
│       ├── __init__.py
│       └── v1/
│           ├── __init__.py
│           ├── router.py
│           └── endpoints/
│               ├── __init__.py
│               ├── health.py
│               └── items.py
└── requirements.txt
```

## Requirements

- Python 3.9+ (works on 3.9; newer versions recommended)

## Install

```bash
python -m venv .venv
# macOS/Linux
source .venv/bin/activate
# Windows
# .venv\\Scripts\\activate

pip install -r requirements.txt
```

## Run locally

```bash
uvicorn app.main:app --reload --host 127.0.0.1 --port 8000
```

Open:
- http://127.0.0.1:8000/docs (Swagger UI)
- http://127.0.0.1:8000/redoc

## API

- `GET /api/v1/health` → `{ "status": "ok" }`
- `GET /api/v1/items/{item_id}?q=...` → example response

## Configuration

Settings are read from environment variables.

- `APP_NAME` (default: `pyco`)
- `API_V1_PREFIX` (default: `/api/v1`)

Example:

```bash
export APP_NAME="pyco"
export API_V1_PREFIX="/api/v1"
```

## Notes

This repo intentionally stays minimal; add database, auth, background jobs, etc. only when needed.
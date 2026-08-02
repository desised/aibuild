# aibuild

A lightweight FastAPI backend that wraps OpenAI's chat completions API behind a REST endpoint.

## Setup

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

Copy `.env.example` to `.env` and add your OpenAI API key:

```bash
cp .env.example .env
```

## Run

```bash
uvicorn main:app --reload
```

The server starts at `http://localhost:8000`.

## Endpoints

### `GET /health`

Returns server status.

```bash
curl http://localhost:8000/health
```

```json
{"status": "ok"}
```

### `POST /ask`

Send a question to OpenAI's `gpt-4o-mini` model.

```bash
curl -X POST http://localhost:8000/ask \
  -H "Content-Type: application/json" \
  -d '{"question": "What is Python?"}'
```

```json
{"answer": "...", "model": "gpt-4o-mini"}
```

Interactive API docs are available at `http://localhost:8000/docs`.
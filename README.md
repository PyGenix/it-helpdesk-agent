# IT Helpdesk Agent

Python FastAPI agent that answers common enterprise IT support questions using LangGraph and Azure OpenAI.

Covers password resets, VPN, laptop access, and general IT guidance without ever requesting credentials.

## Stack

- **Backend:** Python 3.11+, FastAPI, Uvicorn
- **Agent:** LangGraph + LangChain
- **LLM:** Azure OpenAI chat deployment
- **Runtime:** Docker

## Features

- `POST /chat` helpdesk Q&A endpoint
- `GET /health` readiness check
- Guardrailed system prompt for IT support
- Container-friendly Dockerfile

## Quick start

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
cp .env.example .env
# fill Azure OpenAI values
uvicorn app.main:app --reload --port 8000
```

API docs: http://localhost:8000/docs

```bash
docker build -t it-helpdesk-agent .
docker run --env-file .env -p 8000:8000 it-helpdesk-agent
```

## Author

Pooja Sharma — [Pooja101117](https://github.com/Pooja101117)

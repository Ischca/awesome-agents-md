# AGENTS.md – AI Agent Framework Example

## Overview

- Python-based AI agent using LangChain and OpenAI GPT-4.
- Multi-agent system with specialized roles: Researcher, Planner, Writer.
- Environment management with Poetry and Docker.

## Environment

- Python 3.11+ required.
- Install dependencies: `poetry install`.
- Set environment variables in `.env` file:
  ```
  OPENAI_API_KEY=your_key_here
  LANGCHAIN_API_KEY=your_key_here
  LANGCHAIN_TRACING_V2=true
  ```
- Start services: `docker compose up -d` (for vector database).

## Running the Agent

- Start the agent: `poetry run python main.py`.
- Interactive mode: `poetry run python main.py --interactive`.
- Batch processing: `poetry run python main.py --batch tasks.json`.

## Testing

- Unit tests: `poetry run pytest tests/`.
- Integration tests: `poetry run pytest tests/integration/` (requires Docker services).
- Agent behavior tests: `poetry run pytest tests/agents/`.
- All tests must pass before deployment.

## Agent Configuration

- Modify agent roles in `agents/config.yaml`.
- Adjust model parameters in `config/models.yaml`.
- Tool configurations in `tools/config/`.

## Safety & Limitations

- Never execute system commands without explicit approval.
- API rate limits: Max 100 requests/minute per agent.
- Memory limit: 4GB per agent instance.
- Timeout: 300 seconds per task.
- All external API calls must be logged and monitored.

## Deployment

- Build image: `docker build -t ai-agent .`.
- Deploy: `docker run -d --env-file .env ai-agent`.
- Health check endpoint: `http://localhost:8080/health`.

## Monitoring

- Metrics available at `http://localhost:8080/metrics`.
- Logs structured in JSON format.
- LangSmith integration for tracing.
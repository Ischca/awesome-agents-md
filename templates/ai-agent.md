# AGENTS.md – AI Agent Template

## Overview

- Brief description of your AI agent system.
- Tech stack: Python/Node.js, agent framework (LangChain/CrewAI), LLM provider.
- Agent roles and responsibilities.

## Environment

- Runtime requirements (Python 3.11+, Node 20+, etc.).
- API keys needed: `OPENAI_API_KEY`, `LANGCHAIN_API_KEY`.
- Installation: `pip install -r requirements.txt` or `npm install`.
- Services: `docker compose up -d` (if using databases/external services).

## Usage

- Start agent: `python main.py` or `npm start`.
- Configuration files location.
- Input/output formats.

## Testing

- Unit tests: `pytest` or `npm test`.
- Integration tests with external APIs.
- Agent behavior validation tests.

## Safety

- Rate limiting configuration.
- Prohibited actions (system commands, file operations, etc.).
- Timeout settings.
- Error handling and recovery.

## Monitoring

- Logging configuration.
- Metrics and observability.
- Debugging tools and traces.
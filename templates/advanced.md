# AGENTS.md – Advanced Template

## Overview
- Modular TypeScript monorepo driven by pnpm workspaces.
- Airbnb + Prettier code style; 2‑space indent.

## Environment
- Docker required; `docker compose up -d` starts Postgres and Redis.
- Local dev: `pnpm dev` boots all apps.

## Testing
- Unit: `pnpm test`.
- Integration: `pnpm test:integration` (requires Docker services).
- A commit must leave the test suite green.

## Coding Conventions
- Prefer functional programming; avoid mutating globals.
- File names are **kebab‑case**; React components live under `/src/components`.

## Safety
- Never execute shell commands that include user input.
- Never `sudo`; if root privilege is needed, ask a human.

## Example Tasks
- "Implement the `/auth/login` endpoint."
- "Refactor `UserService` to remove circular dependencies."
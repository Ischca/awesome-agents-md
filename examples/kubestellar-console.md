# AGENTS.md – KubeStellar Console

Multi-cluster Kubernetes dashboard with React+TypeScript frontend and Go backend.

- **Quick Start:** `./start-dev.sh` (mock user, no OAuth) or `./startup-oauth.sh` (GitHub OAuth).
- **Ports:** backend `8080`, frontend `5174`, kc-agent WebSocket `8585`.
- **Pre-PR gate:** `cd web && npm run build && npm run lint`.
- **Testing mandatory** for UI and API work — Playwright E2E, curl for REST, websocat for WebSocket.

## Key conventions

- No magic numbers — use named constants.
- Array safety — guard with `(data || [])` before `.map`/`.filter`/`.join`.
- All card data fetching through `useCache` / `useCached*` hooks.
- User-facing strings use `t()` from `react-i18next` — never raw strings.
- Use `DeduplicatedClusters()` when iterating clusters.

## Repository

[kubestellar/console](https://github.com/kubestellar/console) — CNCF Sandbox, Apache-2.0.

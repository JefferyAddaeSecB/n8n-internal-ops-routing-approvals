# n8n Internal Ops Routing and Approvals

Policy-first request routing with AI escalation risk review, SLA-aware approvals, and escalation notifications.

## Files
- `n8n/workflow.json` importable n8n workflow (AI-assisted + deterministic fallback)

## Architecture
- Webhook intake -> normalization -> deterministic routing policy engine
- AI risk review for escalation signal generation
- Merged risk decision -> escalation branch or standard approval flow
- Persistent request record + approver notification

## Runtime Requirements
- n8n (validated with containerized import on n8n latest)
- Set `OPENROUTER_API_KEY` in your n8n environment for AI nodes
- Replace placeholder webhook/API endpoints and credentials before activation

## Import
1. Open n8n UI.
2. Go to `Workflows -> Import from File`.
3. Select `n8n/workflow.json`.
4. Configure credentials and endpoint placeholders.
5. Run a manual execution test before enabling schedule/webhook traffic.

## Live Demo
- https://jefferyaddae.it.com/projects/internal-ops-request-routing-approvals

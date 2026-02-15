# n8n Internal Ops Routing and Approvals

Policy-first request routing with AI escalation risk review, SLA-aware approvals, and escalation notifications.

## Files
- `n8n/workflow.json` importable n8n workflow (AI Agent + deterministic fallback + native app nodes)

## Architecture
- Webhook intake -> normalization -> deterministic routing policy engine
- AI Agent + OpenAI Chat Model for escalation signal generation
- Merged risk decision -> escalation branch or standard approval flow
- Persistent request record in Notion + Slack + Gmail notifications

## Runtime Requirements
- n8n (validated with containerized import on n8n latest)
- Configure credentials for:
  - `OpenAI` (for `AI Agent` model connection)
  - `Slack`
  - `Notion`
  - `Gmail`
  - `HubSpot` (where used)
- Replace placeholder channel/database IDs and recipient addresses before activation

## Import
1. Open n8n UI.
2. Go to `Workflows -> Import from File`.
3. Select `n8n/workflow.json`.
4. Configure credentials and placeholder IDs.
5. Run a manual execution test before enabling schedule/webhook traffic.

## Live Demo
- https://jefferyaddae.it.com/projects/internal-ops-request-routing-approvals

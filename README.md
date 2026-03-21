# OpenAI Codex CLI - Bunnyshell Template

Bunnyshell environment template for [OpenAI Codex CLI](https://github.com/openai/codex), OpenAI's lightweight coding agent.

## What's Included

- **Codex CLI** pre-installed globally via npm
- **ttyd** web terminal for browser-based access
- Persistent `/workspace` volume (5Gi)
- IP whitelisting via Bunnyshell security
- Basic HTTP authentication for the web terminal

## Access

- **Web Terminal**: `https://terminal-<env.base_domain>/` (requires basic auth)
- **Shell**: `bns exec <COMPONENT_ID> --tty --stdin`

## Environment Variables

| Variable | Description |
|----------|-------------|
| `OPENAI_API_KEY` | Your OpenAI API key |
| `TTYD_USER` | Web terminal username (default: `admin`) |
| `TTYD_PASS` | Web terminal password (default: `changeme`) |

## Deploy

```bash
bns environments create \
  --from-path bunnyshell.yaml \
  --name "openai-codex" \
  --project <PROJECT_ID> \
  --k8s <CLUSTER_ID>

bns environments deploy --id <ENV_ID>
```

# Getting started — stand up the gateway

~10 minutes on any machine with Docker. This is the POC path (shared subscriptions). For real
provider APIs later, see the swap section at the end.

## Prerequisites
- Docker + Docker Compose
- A Claude and/or Codex login, and optionally a MiniMax subscription key

## 1. Clone + configure
```bash
git clone https://github.com/Axonate/axonate.git
cd axonate
cp .env.example .env
echo "LITELLM_CONFIG=litellm_config.yaml" >> .env
```
Edit `.env`: set random `LITELLM_MASTER_KEY` / `LITELLM_SALT_KEY` / `ADAPTER_TOKEN`, and
`MINIMAX_API_KEY` if you have one. (Flag values with spaces must stay quoted.)

## 2. Bring it up
```bash
make up PROFILE=poc      # first boot runs LiteLLM DB migrations — a few minutes
```
Wait until `http://127.0.0.1:4000/health/liveliness` returns `200`.

## 3. Log the agents in (headless)
```bash
make login-claude        # prints an OAuth token
make set-claude-token TOKEN=sk-ant-oat01-... SLOT=A
make login-codex         # device-auth: open the URL, enter the code
```
> Tokens live in named Docker volumes — they survive restarts. Never `docker compose down -v`.

## 4. Smoke test
```bash
make smoke               # health, routing, and live model checks
```

## 5. Add your team
```bash
make add-user EMAIL=alice@yourco.com BUDGET=15    # $15 / 30 days, enforced
```
Paste the printed virtual key into `config/users.yaml`.

## Dashboards
- LiteLLM usage UI: `http://127.0.0.1:4000/ui`
- Trace view (route + latency + cost): `http://127.0.0.1:4100/trace/view`

## Going to production
- Turn on SSO: [sso.md](sso.md)
- Swap shared subscriptions for real provider APIs: see `SWAP.md` in the core repo. Model names
  stay identical, so clients don't change.

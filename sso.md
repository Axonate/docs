# SSO (production)

For local/POC use, the gateway runs in `AUTH_MODE=dev` (no login, localhost only). Before you
expose it to a team, turn on SSO so only your people can reach it and every request is attributed.

## How it works
```
user → Cloudflare Access (Google SSO) → Cloudflare Tunnel → axonate-router
       the router VERIFIES the signed Access JWT (signature + audience + expiry)
       → maps the email to that user's virtual key → enforces their budget
```
No open inbound ports — only the tunnel reaches the gateway. Headers are never trusted; the JWT
signature is checked against Cloudflare's team keys.

## Setup (summary)
The full step-by-step lives in the core repo: **[axonate/docs/SSO.md](https://github.com/Axonate/axonate/blob/main/docs/SSO.md)**.

1. Enable Cloudflare Zero Trust; add **Google** as a login method.
2. Create a **Tunnel** → public hostname `axonate.yourdomain.com` → `http://axonate-router:4100`.
3. Create an **Access application** for that hostname; copy the **AUD** tag.
4. Set in `.env`: `AUTH_MODE=cloudflare`, `CF_ACCESS_TEAM_DOMAIN`, `CF_ACCESS_AUD`,
   `CLOUDFLARE_TUNNEL_TOKEN`.
5. Provision users: `make add-user EMAIL=.. BUDGET=..`, paste keys into `config/users.yaml`.
6. `make up PROFILE=prod` then `make smoke` — unauthenticated requests are blocked.

## Verify
- No Access session → request rejected (401 at the origin, blocked at the edge).
- Valid Google login → request attributed to your email and metered to your budget.

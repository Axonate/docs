<div align="center">

# Axonate Docs

### One key, every model — AI that fits a small team's budget.

</div>

Axonate is a self-hosted, OpenAI-compatible AI gateway. Run it once, point your whole team at
it, and reach **every model** — real provider APIs (Anthropic, OpenAI, AWS Bedrock, Azure…) and
**free local models** — through a single endpoint with per-user budgets, smart routing, and
spend tracking.

## Who it's for

**Small companies and teams that need AI without a plan-per-person bill.** One gateway, one key,
every model — with the controls that keep it affordable:

- **No surprise bills** — a hard global spend ceiling + per-user budgets that actually block.
- **Spend cheap by default** — `auto` routing sends easy/bulk work to the cheapest model (or a
  **free local** one).
- **Use what you already pay for** — route through existing AWS/Azure commitments and credits.
- **Know who used what** — per-user trace, usage dashboard, daily Slack digest.

## Three ways to use it

| | |
|---|---|
| 🖥️ **CLI** | the `ax` command — [cli.md](cli.md) |
| 🌐 **Web / API** | any OpenAI-compatible client or SDK — [web.md](web.md) |
| 🧩 **IDE** | VS Code extension + generic OpenAI-compatible IDE config — [ide.md](ide.md) |

## Start here

1. **[getting-started.md](getting-started.md)** — stand up the gateway (Docker, ~10 min).
2. Pick your client: [CLI](cli.md) · [Web/API](web.md) · [IDE](ide.md).
3. **[cost-saving.md](cost-saving.md)** — how Axonate cuts your AI bill.
4. **[sso.md](sso.md)** — lock it down with Google SSO for production.

## Repos

- **[Axonate/axonate](https://github.com/Axonate/axonate)** — the gateway (core)
- **[Axonate/ax](https://github.com/Axonate/ax)** — the CLI (`pip install axonate-ax`)
- **[Axonate/vscode](https://github.com/Axonate/vscode)** — the VS Code extension
- **[Axonate/docs](https://github.com/Axonate/docs)** — you are here

---
MIT © CloudDrove

# How Axonate cuts your AI bill

Built for small companies and teams that can't justify a paid AI seat or API plan for everyone.

## 1. Share subscriptions instead of multiplying them
Most teams buy one AI plan per person. Axonate lets a few flat subscriptions serve everyone
through one gateway — each person gets their own identity and budget, but you pay for a handful
of plans, not headcount × plans.

## 2. Route cheap work to cheap models
The `auto` model uses a tunable policy (`routing.yaml`): short/bulk/transform tasks go to the
cheapest capable backend, and only deep reasoning hits the premium one. You stop paying premium
prices for "summarize this" and "rename these variables."

## 3. Hard ceilings, not surprise invoices
- **Global spend ceiling** — the proxy blocks once the month's cap is hit. No runaway bills.
- **Per-user budgets** — each person gets an enforced limit; over-budget returns a clear error,
  never a silent overage.

## 4. See exactly where money goes
- Per-call trace: user, model, route, latency, tokens, cost, status.
- LiteLLM usage dashboard + a clean **daily Slack spend digest**.
- Catch the one workflow burning tokens before it shows up on the invoice.

## 5. No lock-in when you scale
Start on shared subscriptions (cheapest). When you outgrow them, swap to real provider APIs by
changing one config file — model names stay the same, so nothing downstream changes. You move
to metered APIs only for what actually needs it.

---
> **Bottom line:** one shared gateway + smart routing + enforced budgets = the AI your small
> team needs, at a fraction of per-seat pricing.

Set it up → [getting-started.md](getting-started.md)

# How Axonate cuts your AI bill

Built for small companies and teams that need AI without a plan-per-person bill.

## 1. One shared gateway, per-user budgets
Everyone uses one endpoint with their own identity and enforced budget. You manage AI access
centrally — provision keys, set caps, and see usage — instead of juggling separate plans and
invoices per person.

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

## 5. No lock-in
OpenAI-compatible everywhere. Add or swap providers by changing one config file — model names
stay the same, so clients never change. Use the cheapest provider for each job and move freely
as prices shift.

---
> **Bottom line:** one shared gateway + smart routing across many providers (incl. free local
> models) + enforced budgets = the AI your small team needs, without a plan-per-person bill.

Set it up → [getting-started.md](getting-started.md)

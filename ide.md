# IDE

Use Axonate from your editor two ways: the official **VS Code extension**, or any IDE that
accepts an **OpenAI-compatible** base URL + key.

## VS Code extension (official)

Repo: [Axonate/vscode](https://github.com/Axonate/vscode).

1. Install the **Axonate** extension (Marketplace, or `code --install-extension axonate.vsix`).
2. Open Settings → search "Axonate":
   - `axonate.url` = `https://axonate.yourdomain.com` (or `http://127.0.0.1:4100`)
   - `axonate.apiKey` = your virtual key
   - `axonate.model` = `auto` (or `claude` / `codex` / `minimax`)
3. Use it:
   - Command Palette → **Axonate: Ask** — type a prompt.
   - Select code → **Axonate: Ask about selection** — sends the selection + your question.
   - Replies stream into the Axonate output panel, with the chosen route shown.

## Generic OpenAI-compatible IDEs

Anywhere you can set "OpenAI base URL + API key", point it at the gateway:

```
Base URL:  https://axonate.yourdomain.com/v1
API key:   sk-your-virtual-key
Model:     auto | claude | codex | minimax
```

- **Cursor** — Settings → Models → OpenAI API key + "Override base URL" → gateway `/v1`.
- **Continue (VS Code/JetBrains)** — add a model with `provider: openai`, `apiBase`, `apiKey`.
- **Zed** — assistant settings → OpenAI-compatible provider with the base URL + key.
- **JetBrains AI / others** — any "custom OpenAI endpoint" field works.

Every request still flows through the gateway: per-user budget, routing, and trace apply no
matter which editor sent it.

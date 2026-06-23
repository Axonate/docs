# Web / API

Axonate is **OpenAI-compatible**, so anything that speaks the OpenAI API works — no SDK lock-in.
Base URL = your gateway, key = your virtual key.

```
Base URL:  https://axonate.yourdomain.com/v1   (or http://127.0.0.1:4100/v1 locally)
API key:   sk-your-virtual-key
Models:    auto | claude | codex | minimax
```

## curl
```bash
curl https://axonate.yourdomain.com/v1/chat/completions \
  -H "Authorization: Bearer $AXONATE_KEY" \
  -H "Content-Type: application/json" \
  -d '{"model":"auto","messages":[{"role":"user","content":"hello"}]}'
```
Response headers include `X-Router-Route` and `X-Router-Reason` so you can see the routing.

## OpenAI Python SDK
```python
from openai import OpenAI
client = OpenAI(base_url="https://axonate.yourdomain.com/v1", api_key="sk-your-virtual-key")
r = client.chat.completions.create(
    model="auto",
    messages=[{"role": "user", "content": "summarize this changelog"}],
)
print(r.choices[0].message.content)
```

## JavaScript / TypeScript
```ts
import OpenAI from "openai";
const client = new OpenAI({
  baseURL: "https://axonate.yourdomain.com/v1",
  apiKey: "sk-your-virtual-key",
});
const r = await client.chat.completions.create({
  model: "auto",
  messages: [{ role: "user", content: "write a commit message" }],
});
console.log(r.choices[0].message.content);
```

## Streaming
Set `"stream": true` (curl) or `stream: true` (SDK) — server-sent events, standard OpenAI chunks.

## Any other tool
Cursor, Continue, LibreChat, Open WebUI, LangChain, LlamaIndex — anywhere you can set an
"OpenAI base URL + key", point it at the gateway. One endpoint, every model, shared budget.

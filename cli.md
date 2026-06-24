# CLI — `ax`

The tiny, zero-dependency command-line client. Repo: [Axonate/ax](https://github.com/Axonate/ax).

## Install

**macOS (Homebrew)**
```bash
brew install Axonate/tap/ax
```
**pip — macOS / Linux / Windows** (zero deps, Python 3.8+)
```bash
pip install axonate-cli          # or: pipx install axonate-cli
```
**Windows** (PowerShell / CMD)
```powershell
py -m pip install axonate-cli
```

## Configure
`~/.config/axonate/config` (or env vars `AXONATE_URL` / `AXONATE_KEY`):
```
AXONATE_URL=https://axonate.yourdomain.com   # or http://127.0.0.1:4100 locally
AXONATE_KEY=sk-your-virtual-key
```

## Usage
```bash
ax "explain this error"                  # auto-routing
ax -m claude "write a haiku"             # force a model (claude | codex | minimax)
git diff | ax "review this"              # pipe stdin (appended to the prompt)
ax -s work "remember: deploy is Friday"  # session: persists history locally
ax -s work "when is deploy?"             #   ...same session recalls it
ax -s work --new "new topic"             # reset the session
ax --no-stream "..."                     # full response at once
```

## Flags
| Flag | Meaning |
|---|---|
| `-m, --model` | model name (default `auto`) |
| `-s, --session NAME` | persist + resend conversation history |
| `--new` | reset the named session before this turn |
| `--no-stream` | disable streaming output |

The gateway echoes the chosen backend to stderr (`[route: codex]`), so you always see where
your tokens went — handy when watching cost.

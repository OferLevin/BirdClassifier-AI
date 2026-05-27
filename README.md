# VERDICT — AI Sports Debate Judge

Settle any sports debate with an AI verdict: scores, a ruling, key evidence, and a dissenting opinion.

## Setup

### 1. Add your API key

Open `.env` and replace `your_key_here` with your Anthropic API key:

```
ANTHROPIC_API_KEY=sk-ant-...
```

### 2. Run the server

```bash
node server.js
```

### 3. Open the app

Visit [http://localhost:3000](http://localhost:3000) in your browser.

---

## How it works

- `index.html` — the entire frontend (single file, no build tools)
- `server.js` — a minimal Node.js HTTP server that:
  - Serves `index.html` at `/`
  - Proxies `POST /api/verdict` to the Anthropic API, injecting the API key server-side so it's never exposed to the browser
- `.env` — stores your API key locally

## Requirements

- Node.js 16+ (uses built-in `http` and `https` modules, no npm install needed)
- An Anthropic API key with access to `claude-sonnet-4-20250514`

## Usage

1. Type any sports debate in the text box (or pick a quick debate)
2. Click **JUDGE IT** (or press Cmd/Ctrl + Enter)
3. Read the verdict — scores, ruling, evidence, and dissent
4. Hit **Copy Verdict** to share a text summary

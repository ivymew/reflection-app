# Sotto

A client-side journaling app. Speak or type your thoughts, AI organizes them into a structured journal entry, and save directly to your Obsidian vault.

**Live:** [reflection.zheng-yao.com](https://reflection.zheng-yao.com)

## How It Works

1. Open the app on your phone (or desktop)
2. Type or dictate what happened today
3. AI organizes your raw thoughts into a clean journal entry
4. Review and edit the result
5. Tap save — the entry goes straight into your Obsidian vault

Everything runs in the browser. No backend, no database, no account. Your API key and PIN stay in localStorage on your device. AI calls go directly from your browser to the API provider.

## Prerequisites

**Required:**

- **Obsidian** installed on the same device ([obsidian.md](https://obsidian.md)). The app saves entries using Obsidian's `obsidian://new` URL scheme, so Obsidian needs to be present to receive them.
- **An Obsidian vault** with a folder for entries (e.g. `entries/2026/`). You can configure the vault name and entry path in the app's settings.
- **An API key** from one of these providers:
  - [Anthropic](https://console.anthropic.com/) (Claude) — or
  - [OpenAI](https://platform.openai.com/) (GPT)

**Optional (for voice mode):**

- **An OpenAI API key** for voice transcription. If you already chose OpenAI as your LLM provider, the same key is used. If you use Anthropic for the LLM, you'll need a separate OpenAI key for transcription.

## Self-Hosting

The entire app is a single `index.html` file with no build step and no dependencies. To host it yourself:

1. Fork this repo
2. Deploy to any static hosting (Cloudflare Pages, GitHub Pages, Vercel, Netlify — anything works)

Or just open `index.html` locally in a browser. It works over `file://` too, though some browsers may restrict `obsidian://` links from local files.

## Privacy

- All data stays on your device (localStorage)
- API calls go directly from your browser to Anthropic/OpenAI — no intermediary server
- Journal entries are saved locally to your Obsidian vault, not to any cloud service
- This repo contains zero tracking, analytics, or telemetry

# Sotto

A client-side journaling app. Speak or type your thoughts, AI organizes them into a structured journal entry, and save directly to your Obsidian vault.

**Live:** [sotto.zheng-yao.com](https://sotto.zheng-yao.com)

## How It Works

1. Open the app on your phone
2. Type or dictate what happened today
3. AI organizes your raw thoughts into a clean journal entry
4. Review and edit the result
5. Tap save — the entry goes straight into your Obsidian vault

Everything runs in the browser. No backend, no database, no account. Your API key stays in localStorage on your device. AI calls go directly from your browser to the API provider.

## Prerequisites

**Required:**

- **Obsidian** installed on the device you use the app on ([obsidian.md](https://obsidian.md)). The app saves entries using Obsidian's `obsidian://new` URL scheme, so Obsidian needs to be present to receive them.
- **An Obsidian vault** — see [Vault Setup](#vault-setup) below.
- **An API key** from one of these providers:
  - [Anthropic](https://console.anthropic.com/) (Claude)
  - [OpenAI](https://platform.openai.com/) (GPT)
  - [Google](https://aistudio.google.com/apikey) (Gemini)

**Recommended setup:**

- **Obsidian on desktop** — needed for initial vault setup. You'll import the vault template folder on your computer, then sync it to your phone.
- **Obsidian on your phone** — for daily use with the app.
- **iCloud sync** — keeps the vault in sync between desktop and phone. Both Obsidian apps should be pointed at the same iCloud folder.

**Optional (for voice mode):**

- **An OpenAI API key** for voice transcription. If you already chose OpenAI as your LLM provider, the same key is used. If you use another LLM provider, you'll need a separate OpenAI key for transcription.

## Vault Setup

This repo includes a `vault-template/` folder — a ready-to-use Obsidian vault with the Sotto theme, a calendar view, and an all-entries index.

**Quick setup:**

1. Copy the `vault-template/` folder to wherever you keep your vaults (e.g. your iCloud or local Documents folder)
2. Rename it to `Sotto` (or any name you like — just update the vault name in the app's settings to match)
3. In Obsidian, choose **Open folder as vault** and select the folder
4. Obsidian will ask you to **Trust author and enable plugins** — click Trust. This enables the Dataview plugin, which powers the Calendar and All Entries pages.

That's it. The CSS theme and Dataview plugin are pre-configured and will load automatically.

**What's included:**

- `All Entries.md` — a table of all your journal entries, sorted by date
- `Calendar.md` — a calendar view showing which days have entries
- `entries/` — where your journal entries will be saved
- `.obsidian/snippets/sotto-daily.css` — the Sotto visual theme (warm paper tones, serif typography)
- `.obsidian/plugins/dataview/` — the Dataview plugin (pre-installed)

> **Note:** The vault name defaults to `Sotto` in the app. If you rename the vault, go to the app's Settings and update the vault name to match.

## Install on iPhone

Sotto is a PWA (Progressive Web App) — you can add it to your home screen and use it like a native app.

1. Open [sotto.zheng-yao.com](https://sotto.zheng-yao.com) in Safari
2. Tap the **Share** button (the square with an arrow)
3. Scroll down and tap **Add to Home Screen**
4. Tap **Add**

The app will appear on your home screen with the Sotto icon. It opens full-screen without Safari's address bar.

## Self-Hosting

The entire app is a single `index.html` file with no build step and no dependencies. To host it yourself:

1. Fork this repo
2. Deploy to any static hosting (Cloudflare Pages, GitHub Pages, Vercel, Netlify — anything works)

Or just open `index.html` locally in a browser. It works over `file://` too, though some browsers may restrict `obsidian://` links from local files.

## Privacy

- All data stays on your device (localStorage)
- API calls go directly from your browser to Anthropic/OpenAI/Google — no intermediary server
- Journal entries are saved locally to your Obsidian vault, not to any cloud service
- This repo contains zero tracking, analytics, or telemetry

# Qrblox

**Dynamic QR codes for every surface — mobile, Canva, web, and AI agents.**

Qrblox is the QR platform you can use anywhere you work. Make a code in
the iOS or Android app, drop one into a Canva design, generate one in
the web portal, or call the MCP server from Claude / Cursor / Codex —
every code lives on one account, with the same dashboard, the same
scan analytics, and the same daily reports.

🌐 **Marketing site:** [qrblox.com](https://qrblox.com)
📱 **iOS app:** [Qrblox: AI Chat with QR Code](https://apps.apple.com/us/app/qrblox-ai-chat-with-qr-code/id6737632062)
🤖 **Android app:** [`com.qrblox.app` on Google Play](https://play.google.com/store/apps/details?id=com.qrblox.app)
🎨 **Canva app:** Available in the [Canva apps marketplace](https://www.canva.com/apps/) — search **Qrblox**
🖥️ **Web portal:** [app.qrblox.com](https://app.qrblox.com)
📚 **Docs:** [docs.qrblox.com](https://docs.qrblox.com)
🧠 **MCP for agents:** [docs.qrblox.com/mcp.html](https://docs.qrblox.com/mcp.html)

---

## What is Qrblox?

Qrblox is QR codes done right — dynamic by default (so you can
re-point a printed code), scan-tracked, and consistent across every
way you make them. One Qrblox account holds every code, regardless of
which surface produced it; analytics roll up daily.

---

## Where you can create codes

### iOS app — Qrblox: AI Chat with QR Code

Create dynamic codes on iPhone or iPad. Scan a QR code straight from a
photo in your camera roll (not only the live camera), chat with the
built-in AI about what you scanned, and share links with sound using
**Audio Handshake**. Sign in with Google, email/password, or Apple.

→ [Download on the App Store](https://apps.apple.com/us/app/qrblox-ai-chat-with-qr-code/id6737632062)

### Android app

The same Qrblox toolkit on Android phones and tablets, backed by the
same account.

→ [Get it on Google Play](https://play.google.com/store/apps/details?id=com.qrblox.app)

### Canva app — Qrblox for Canva

Drop a real, scannable QR code into any Canva design — a poster, a
flyer, business cards — with branded **templates** and **5x boost
reward frames**. Codes made in Canva are claimed to your Qrblox account
in one click so you can re-point and track them later.

→ Find it in the [Canva apps marketplace](https://www.canva.com/apps/) — search **Qrblox**

### Web app — app.qrblox.com

Manage everything in one dashboard. Generate codes from the
**Generate QR Codes** tab, edit any destination, view scan analytics,
manage billing, claim Canva codes, connect your Canva account, and
mint API keys for AI agents.

→ [app.qrblox.com](https://app.qrblox.com)

---

## For AI agents and developers

The **Qrblox MCP server** (`qrblox-mcp`) lets any MCP-aware AI —
Claude, Cursor, Codex, custom agents — generate, list, and re-point QR
codes (and audio codes, menus, and loyalty campaigns) on the caller's
account.

**Endpoint:** `https://app.qrblox.com/api/mcp`
**Auth:** `Bearer sk-qrblox-...` — mint at [create.qrblox.com/settings/api-keys](https://create.qrblox.com/settings/api-keys)
**No-key sandbox:** `POST https://app.qrblox.com/api/generate-qr-code`

| Tool | What it does |
|---|---|
| `qrblox.ping` / `qrblox.merchant.get_profile` | Reachability + identity. |
| `qrblox.qr.list` / `qrblox.qr.create` | List and create QR codes. |
| `qrblox.audio.create` | Audio codes (near-ultrasonic payloads). |
| `qrblox.menu.create` / `.list` / `.add_item` | Build and extend menus. |
| `qrblox.challenge.create` | Scan streaks, games, loyalty campaigns. |
| `qrblox.analytics.scan_summary` | Total scans + by-day series. |

### Try it without signing up

```bash
curl -X POST https://app.qrblox.com/api/generate-qr-code \
  -H 'content-type: application/json' \
  -d '{"url":"https://example.com"}'
```

Returns a scannable QR code (inline PNG + hosted image URL) — no key
required. Sandbox: 3 codes per IP per day, expire in 7 days.

### Quick install (Claude Desktop)

```jsonc
// ~/Library/Application Support/Claude/claude_desktop_config.json
{
  "mcpServers": {
    "qrblox": {
      "url": "https://app.qrblox.com/api/mcp",
      "headers": {
        "Authorization": "Bearer sk-qrblox-..."
      }
    }
  }
}
```

Restart Claude Desktop. Full reference and connect snippets at
[**docs.qrblox.com/mcp.html**](https://docs.qrblox.com/mcp.html).

---

## Daily reports

Scan activity rolls up into daily reports on every Qrblox account:

- **Daily city rank** — top cities by scan volume.
- **Daily DataPro report** — per-code export with destination URL,
  scan location, city/state, and day-of-week for deeper analysis.

---

## License

© Qrblox / Terahertz Inc.

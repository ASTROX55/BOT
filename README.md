# 🤖 Slobos & Mr. Juice Aternos 24/7 Hosting Bot

A Minecraft bot that helps keep an Aternos server online 24/7 by automatically joining it using a Mineflayer-based bot. Perfect for SMPs or small multiplayer servers that shut down when no players are online.

---

## ✨ Features
*   ✅ **Auto-Connect**: Automatically joins your server.
*   ✅ **Infinite Uptime**: Prevents AFK kicks and server shutdowns.
*   ✅ **Smart Reconnect**: Automatically reconnects if the internet drops or server restarts.
*   ✅ **Render-Ready**: Includes "Self-Ping" to run 24/7 for FREE on Render.com.
*   ✅ **Plugin Support**: Compatible with Paper/Spigot/Bukkit (auto-auth included).

---

## 🛠️ Requirements
*   **GitHub Account**
*   **Aternos Server**
*   **Render Account** (for 24/7 hosting)
*   **Common Sense!** 🧠        

---

## 🚀 Setup Guide

We have made setup super easy! Check out the guide below:

[**Detailed Google Doc Guide**](https://docs.google.com/document/d/1Fl0dRzP6O30ehp5-QcaB11IobF8I1JJhKUipzCWiCYA/edit?tab=t.0).

---

## ⚙️ Usage
*   **Start**: Just turn on your Aternos server. The bot will join automatically.
*   **Status**: Visit the Render URL to see a status dashboard.
*   **Chat**: The bot logs chat to the console.

---

## ⚠️ Disclaimer
This project is not affiliated with Aternos, Mojang, or Microsoft. Use at your own risk. Misuse may violate platform terms of service. This bot does not bypass Aternos queue limits; it only keeps the server active once it is online.

---

## ❤️ Credits
*   **Slobos (Discord: sloboscc)** — Original creator & idea. (The GOAT 🐐)
*   **Mr.Juice (Discord: Mr.Juice3046)** — Updates, Guide, & Maintenance.

**License**: MIT License


## 🔧 Connection configuration (updated)

The bot now supports environment variables, which is safer for GitHub deployments.
`settings.json` can contain non-secret defaults, while hosting providers should set:

- `MC_HOST` — your Aternos Java server hostname
- `MC_PORT` — the **current Java port shown by Aternos**
- `MC_USERNAME` — the bot's Minecraft username
- `MC_PASSWORD` — the password used by the server's `/login` plugin, if applicable
- `MC_AUTH` — normally `offline` for an Aternos server with cracked/offline mode enabled
- `MC_VERSION` — optional; leave unset to auto-detect

Do not commit a real password to GitHub.

### Aternos checklist

1. Start the Aternos **Java Edition** server first.
2. Copy the current **DynIP/hostname and port** shown by Aternos. The port can change, so update `MC_PORT` when Aternos gives you a new one.
3. If the server requires `/login`, put that password in `MC_PASSWORD`.
4. If the server is configured for online-mode, an `offline` Mineflayer bot cannot join; use an appropriate Microsoft-authenticated account instead.
5. Keep the server software compatible with Java Edition. Mineflayer does not connect to Bedrock-only servers.
6. The bot automatically detects the Minecraft protocol version unless `MC_VERSION` is set.
7. Unexpected disconnects trigger exponential-backoff reconnects; deliberate dashboard stops do not reconnect.

### Important hosting note

This is a long-running Minecraft bot. Vercel's serverless platform is not a suitable host for a process that must maintain a persistent Minecraft connection. Use a host that supports an always-running Node.js worker/service.

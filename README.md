<div align="center">

# TOOLSTORE

### The lightweight, secure app store for desktop tools — the *Steam / F-Droid of desktop utilities*.

**Browse a signed catalog, install free tools on demand, keep them updated — one click, no clutter.**

[![Download](https://img.shields.io/badge/Download-Windows%20.exe-2563eb?style=for-the-badge&logo=windows)](https://github.com/emilioperna/TOOLSTORE/releases/latest)
[![License](https://img.shields.io/badge/License-Proprietary-64748b?style=for-the-badge)](#license)
[![Signed catalog](https://img.shields.io/badge/Catalog-Ed25519%20signed-16a34a?style=for-the-badge)](#-security)

[**⬇️ Download**](https://github.com/emilioperna/TOOLSTORE/releases/latest) · [**📖 How it works**](#-how-it-works) · [**❓ FAQ**](#-faq)

</div>

---

## What is TOOLSTORE?

**TOOLSTORE is a free, lightweight desktop app store for Windows.** Think of it as the *Steam* or *F-Droid* for productivity and AI tools: a small, fast launcher that lets you **browse, install, update and uninstall standalone tools** from a single place — without hunting for installers across the web.

Each tool is a **self-contained app** (its runtime and models live *inside* the app), so the store itself stays tiny and the tools run **fully offline and private** on your PC. The catalog is a **cryptographically signed index** hosted on GitHub, so new tools and updates appear automatically — you never have to reinstall the store.

> **Privacy-first · Offline · No account · No telemetry · Open catalog.**

---

## ✨ Why TOOLSTORE

| | |
|---|---|
| 🪶 **Featherweight** | The store is a ~17 MB launcher. Heavy dependencies (AI models, OCR engines) live *inside each tool*, never in the store. |
| 🔐 **Signed & tamper-proof** | Every catalog is verified with an **Ed25519** signature against a pinned trust key. A modified catalog is rejected before anything is shown. |
| 🔄 **Auto-updating catalog** | New tools and versions are published to a signed GitHub-hosted index. The store picks them up automatically — **no store update needed**. |
| 🧩 **Install / update / uninstall** | Manage tools like phone apps: one-click install, in-app "Update available" badges, clean uninstall. |
| 🛡️ **Offline & private** | Tools run locally on your machine. No cloud, no account, your data never leaves your PC. |
| ⚡ **Hardware-aware** | Each tool picks the right version/model tier (*lite* vs *pro*) for your RAM/VRAM automatically. |

---

## 🚀 How it works

```
┌─────────────┐   signed index    ┌──────────────────┐
│  TOOLSTORE  │◀──(Ed25519)───────│  GitHub catalog  │
│  (launcher) │                   │   index.json     │
└──────┬──────┘                   └──────────────────┘
       │ install (verified sha256)
       ▼
┌─────────────┐   runs as its own process (own runtime inside)
│   A Tool    │   ← OCR, transcription, … fully offline
└─────────────┘
```

1. **Install TOOLSTORE** — one `.exe`, no dependencies to set up.
2. **Browse the catalog** — the store fetches a **signed** list of tools from GitHub.
3. **Install a tool** — the package is downloaded and **sha256-verified**, then the tool is ready.
4. **Stay updated** — when a tool's repository publishes a new version, the store shows an **"Update"** badge.

---

## ⬇️ Install

1. Go to **[Releases](https://github.com/emilioperna/TOOLSTORE/releases/latest)**.
2. Download `TOOLSTORE-Setup.exe`.
3. Run it. That's it — the store opens and you can install your first tool.

> Windows 10/11 · 64-bit. No Python, no extra runtime required.

---

## 📦 Featured tools

| Tool | What it does | Runs offline |
|------|--------------|:---:|
| **Trascrizioni** | Images, chats & video frames → editable text and spreadsheets (OCR) | ✅ |

*More tools are added continuously — they show up in your store automatically thanks to the signed catalog.*

---

## 🔐 Security

Security is a first-class design goal, not an afterthought:

- **Signed catalog (Ed25519).** The tool index is signed with an offline private key; the store verifies it against a **pinned public key**. Any tampering → the catalog is refused.
- **Verified downloads.** Every tool package and model is checked by **sha256** before install.
- **GitHub-only sources.** Downloads are restricted to a GitHub allowlist; arbitrary URLs are rejected.
- **No path traversal.** Tool IDs and served assets are strictly validated/whitelisted.
- **EXE-only distribution.** We ship **signed installers**, not source folders — the code of every tool and of the store stays protected.

---

## ❓ FAQ

**What is TOOLSTORE in one sentence?**
A lightweight, secure desktop app store for Windows — like Steam or F-Droid, but for productivity and AI tools that run offline on your PC.

**Is it free?**
Yes. The store and the listed tools are free to download and use.

**Do I need an account or internet connection?**
No account. You need internet to download tools; once installed, tools run **fully offline**.

**Do my files or data get uploaded anywhere?**
No. Tools process everything **locally**. There is no telemetry and no cloud.

**How is it different from just downloading installers from the web?**
TOOLSTORE gives you **one trusted place** with a **cryptographically signed** catalog, **verified** downloads, and built-in **updates** — instead of chasing random installers.

**How do new tools appear without updating the store?**
The catalog is a **signed index hosted on GitHub**. When a new tool (or a new version) is published to the index, the store fetches it automatically.

**Which platforms are supported?**
Windows 10/11 (64-bit) today. Each tool declares the versions it supports.

**Is it safe to install?**
Yes — installers are signed and every download is signature/hash-verified. See [Security](#-security).

---

## 🇮🇹 In breve (Italiano)

**TOOLSTORE è lo store leggero e sicuro per i tool desktop — lo *Steam / F-Droid* delle utility.**
Sfogli un **catalogo firmato**, installi app gratuite **on-demand**, le tieni aggiornate e le disinstalli con un clic. Ogni tool è **autonomo** (runtime e modelli **dentro l'app**) e gira **offline** sul tuo PC: nessun account, nessuna telemetria, massima privacy. Il catalogo è un **indice firmato Ed25519** su GitHub, quindi i nuovi tool compaiono **automaticamente** senza reinstallare lo store.

**Installa:** scarica `TOOLSTORE-Setup.exe` dalle **[Releases](https://github.com/emilioperna/TOOLSTORE/releases/latest)**, avvialo, installa il tuo primo tool.

---

## License

Proprietary. Installers are provided free of charge; redistribution of the binaries and reverse engineering are not permitted. © Emilio Perna.

<div align="center">
<sub>TOOLSTORE — the app store for desktop tools · signed · offline · private</sub>
</div>

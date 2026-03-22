![DropByte MSG](https://files.catbox.moe/ejkw30.png)

# DropByte MSG

*Modular · Evolving · Private*

<br>

![Node](https://img.shields.io/badge/Node.js-v18+-brightgreen?style=flat-square&logo=node.js)
![Baileys](https://img.shields.io/badge/Baileys-whiskeysockets-blueviolet?style=flat-square)
![Status](https://img.shields.io/badge/Status-In_Development-orange?style=flat-square)
![Since](https://img.shields.io/badge/Since-2022-lightgrey?style=flat-square)
![Private](https://img.shields.io/badge/Repo-Private-critical?style=flat-square)

<br>

*"From a small experiment in 2022 — growing ever since."*

</div>

---

## About

**DropByte MSG** is a Multi Device WhatsApp Bot that has been running since **2022**, going through many changes in name, system, and architecture following the evolution of WhatsApp's ecosystem and Baileys library updates.

Built on top of **Shota Base** as its foundation, then gradually developed with custom features. The bot is still in active development — some features may not be perfect and bugs are being fixed regularly.

**Repository is private and not publicly available.**

---

## Project Timeline

```
2022  Founded — first experiments, name & system changed frequently
2023  Stabilized — plugin system introduced
2024  Major refactor — hybrid architecture, structured database
2025  Added tax, accounting & student tools modules
2026  Rebranding → DropByte MSG, ongoing development
```

---

## Goals

- Build a functional, modular, and easily extendable WhatsApp bot
- Provide features useful for everyday needs
- Explore and learn the Node.js & Baileys ecosystem
- Serve as a solid foundation for future feature development

> ⚠️ **Disclaimer:** This bot is still in active development. Some features may not work perfectly. Bugs found will be fixed gradually.

```
  Total Plugins   : 65+ features
  Categories      : 10 categories
  Database        : SQLite + JSON
  Module System   : ESM (import/export)
  Login Method    : Pairing Code (no QR)
  Status          : Active Development 🔧
```

---

## Tech Stack

```
  Runtime          Node.js v18+
  WhatsApp         @whiskeysockets/baileys (wileys fork)
  Module System    ESM — import / export
  Database         SQLite3 (main data) + JSON (RPG)
  Media Processing FFmpeg + canvas + jimp + node-webpmux
  Terminal UI      chalk (colored logs)
  HTTP Client      axios + node-fetch
  Date & Time      moment-timezone
  System Info      node-os-utils + os
```

---

## Features

| | Category | Description |
|---|---|---|
| 🔌 | System | Modular plugins, hot reload, auto-detect menu |
| 🔐 | Auth | Pairing code login, multi-owner, public/self mode |
| ⚔️ | RPG | Hunt, battle, shop, inventory, leaderboard, Terra economy |
| 🧾 | Tax | PPh 21/23/25, PPN, PPnBM, UMKM, PTKP, 2024 tax reference |
| 📊 | Accounting | BEP, COGS, P&L, depreciation, financial ratios, bank reconciliation |
| 🎓 | Student | GPA calculator, target grade, cumulative GPA, research sampling |
| 💬 | Social | Anonymous menfess & reply system |
| 💳 | Financial | KPR / vehicle loan installment calculator |
| 📁 | File Manager | Manage plugins & server files directly via WA |
| 🖼️ | Media | Sticker, video convert, voice note, upload to URL |

---

## Project Structure

```
dropbyte-msg/
│
├── index.js                     ← Entry point, Baileys connection, pairing code
├── settings.js                  ← Global bot config (hot-reload)
├── case.js                      ← Fallback switch-case commands
├── package.json
│
├── src/
│   ├── handler.js               ← Main message handler, routing, terminal logging
│   └── plugins.js               ← Recursive plugin loader, stats, getMenuData
│
├── lib/
│   ├── config.js                ← Baileys message serializer → m object
│   ├── database.js              ← SQLite helper (users, groups, settings)
│   ├── function.js              ← Global utility functions
│   ├── items.js                 ← RPG item master data + consistent emoji
│   ├── rpg-json.js              ← RPG JSON database helper
│   └── webp.js                  ← Media to WebP converter for stickers
│
├── plugins/
│   ├── command/                 ← Main commands
│   │   └── menu.js              → .menu
│   │
│   ├── owner/                   ← Owner-only commands
│   │   ├── eval.js              → .eval .> .$ .q
│   │   ├── backup.js            → .backup
│   │   ├── restart.js           → .restart
│   │   ├── modebot.js           → .mode
│   │   ├── prefix.js            → .prefix .setprefix
│   │   ├── addown.js            → .addow
│   │   ├── delown.js            → .delown
│   │   ├── listown.js           → .listown
│   │   └── clear-sesions.js     → .clearsesion
│   │
│   ├── files/                   ← File & plugin manager via WA
│   │   ├── addplugin.js         → .addplugin
│   │   ├── delplugin.js         → .delplugin
│   │   ├── getplugin.js         → .getplugin
│   │   ├── listplugin.js        → .listplugin
│   │   ├── ganti-file.js        → .gantifile
│   │   ├── get-file.js          → .getfile
│   │   └── list-file.js         → .listfile
│   │
│   ├── other/                   ← General features
│   │   ├── ping.js              → .ping .os
│   │   ├── sticker.js           → .sticker .s
│   │   ├── tourl.js             → .tourl
│   │   ├── runtime.js           → .runtime .rt
│   │   ├── totalfitur.js        → .totalfitur
│   │   ├── script.js            → .script
│   │   ├── tqto.js              → .tqto
│   │   ├── menfess.js           → .menfess .confess
│   │   ├── balas.js             → .balas
│   │   └── cicilan.js           → .cicilan .kpr
│   │
│   ├── tools/                   ← Media conversion
│   │   ├── toimage.js           → .toimage
│   │   ├── tovid.js             → .tovid
│   │   ├── tovn.js              → .tovn .toptt
│   │   ├── tolid.js             → .tolid
│   │   └── get.js               → .get
│   │
│   ├── grup/                    ← Group management
│   │   └── antilinkgc.js        → .antilink
│   │
│   ├── rpg/                     ← RPG & economy system
│   │   ├── profile.js           → .profile .me
│   │   ├── inventory.js         → .inv .inventory
│   │   ├── hunt.js              → .hunt .berburu
│   │   ├── work.js              → .work .kerja
│   │   ├── battle.js            → .battle .fight
│   │   ├── daily.js             → .daily .harian
│   │   ├── rest.js              → .rest .istirahat
│   │   ├── shop.js              → .shop .beli
│   │   ├── use.js               → .use .pakai
│   │   ├── leaderboard.js       → .lb .top
│   │   └── levelup.js           → .level .lvl
│   │
│   ├── pajak/                   ← Indonesian tax calculators
│   │   ├── pph21.js             → .pph21
│   │   ├── pph23.js             → .pph23
│   │   ├── pph25.js             → .pph25 .angsuran
│   │   ├── pphumkm.js           → .pphumkm .umkm
│   │   ├── ppn.js               → .ppn
│   │   ├── ppnbm.js             → .ppnbm
│   │   ├── ptkp.js              → .ptkp
│   │   └── tarifpph.js          → .tarifpph .infopajak
│   │
│   ├── akuntansi/               ← Accounting & banking
│   │   ├── bep.js               → .bep .breakeven
│   │   ├── hpp.js               → .hpp .cogs
│   │   ├── labarugi.js          → .labarugi .pl
│   │   ├── depresiasi.js        → .depresiasi .penyusutan
│   │   ├── rasio.js             → .rasio .ratio
│   │   ├── bunga.js             → .bunga .interest
│   │   ├── rekonsiliasi.js      → .rekonsiliasi .rekon
│   │   └── jurnal.js            → .jurnal
│   │
│   └── mahasiswa/               ← Academic student tools
│       ├── ipk.js               → .ipk .ip
│       ├── konversinilai.js     → .konversi .grade
│       ├── targetuas.js         → .targetuas .uas
│       ├── targetipk.js         → .targetipk
│       └── sampling.js          → .sampling .sampel
│
├── data/
│   ├── database.db              ← SQLite (auto-created)
│   ├── rpg.json                 ← RPG JSON data (auto-created)
│   ├── owner.json               ← Additional owners list
│   └── trash/                   ← Temporary media files
│
└── Auth/                        ← Baileys session (auto-created on pairing)
```

---

## Commands

### 📌 Main
`.menu` — show all commands (auto-detect)

---

### 🍉 Owner
`.eval` · `.restart` · `.backup` · `.mode` · `.setprefix` · `.addow` · `.delown` · `.listown` · `.clearsesion`

---

### 📁 File Manager
`.addplugin` · `.delplugin` · `.getplugin` · `.listplugin` · `.gantifile` · `.getfile` · `.listfile`

---

### 🍓 Other
`.ping` · `.sticker` · `.tourl` · `.runtime` · `.totalfitur` · `.menfess` · `.balas` · `.cicilan`

---

### 🔖 Tools
`.toimage` · `.tovid` · `.tovn` · `.tolid` · `.get`

---

### ⚔️ RPG

| Command | Cooldown | Description |
|---|---|---|
| `.profile` | — | View profile & character stats |
| `.inventory` | — | View items grouped by category |
| `.daily` | 24h | Claim daily reward |
| `.hunt` | 30s | Hunt for random loot |
| `.work` | 1h | Work to earn Terra & bonus items |
| `.battle` | 1m | Fight monsters, scaled by level |
| `.rest` | 15m | Restore HP & Stamina |
| `.shop` | — | Browse item shop |
| `.shop <item>` | — | Buy item from shop |
| `.use <item>` | — | Use a consumable item |
| `.leaderboard` | — | Player ranking by Terra |

---

### 🧾 Tax

| Command | Description |
|---|---|
| `.pph21` | Employee income tax — progressive rate, PTKP, occupational deduction |
| `.pph23` | Withholding tax — dividends 15%, services/rent 2% |
| `.pph25` | Monthly PPh 25 installment |
| `.pphumkm` | UMKM final tax 0.5% — checks 500M limit |
| `.ppn` | VAT 11% or custom rate |
| `.ppnbm` | Luxury goods tax 10%–75% |
| `.ptkp` | Check PTKP or view full table |
| `.tarifpph` | Complete 2024 tax rate reference |

---

### 📊 Accounting & Banking

| Command | Description |
|---|---|
| `.bep` | Break Even Point in units & rupiah + profit target simulation |
| `.hpp` | Cost of Goods Sold |
| `.labarugi` | P&L statement simulation + corporate tax |
| `.depresiasi` | Asset depreciation — Straight Line, Declining Balance, SYD |
| `.rasio` | 10 financial ratios — liquidity, solvency, profitability, activity |
| `.bunga` | Bank interest — flat, effective, annuity, deposit, compound |
| `.rekonsiliasi` | Bank reconciliation + automatic adjusting entries |
| `.jurnal` | Journal entry guide for 12 types of bank transactions |

---

### 🎓 Student Tools

| Command | Description |
|---|---|
| `.ipk` | Calculate semester GPA from subject list |
| `.konversi` | Convert grade number → letter → 4.0/5.0 scale |
| `.targetuas` | Minimum final exam score needed + scenario simulation |
| `.targetipk` | GPA needed next semester to reach cumulative target |
| `.sampling` | Sample size — Slovin, Krejcie & Morgan, Cochran |

---

## Installation

```bash
git clone <repo-url>
cd repo-name
npm install
node index.js
```


---

## Run with PM2

```bash
npm install -g pm2
pm2 start index.js --name repo-name
pm2 save && pm2 startup
```

---

## Configuration

All settings are in `settings.js`. This file supports hot reload — changes apply instantly without restart. Configurable: owner numbers, bot name, version, thumbnail image, reply image, and auto-rejection messages.

Prefix and bot mode can be changed via commands and are saved to the database.

---

## Plugin System

Each feature is a separate `.js` file inside the `plugins/` folder. Loaded automatically and recursively — including all subfolders. New plugins are active immediately without restart and automatically appear in the menu.

---

## Hot Reload

Bot uses `fs.watchFile` on all main files. If a file is changed, the bot automatically reloads it without a full restart. Applies to all config files, handlers, and plugins.

---

## Database

Uses two databases running in parallel. **SQLite** for main user data, group settings, prefix, and bot mode. **JSON flat-file** for more flexible RPG data such as inventory, cooldowns, and quests.

---

## Troubleshooting

**Messages not read after pairing** — restart bot once, this is a known Baileys bug.

**Module not found** — run `npm install` again.

**Plugin not showing in menu** — make sure the file has `handler.command` and `export default`.

**Session expired** — delete the `Auth/` folder and re-pair.

---

## FAQ

**Can it run on Termux?** Yes, but not recommended for production. Use VPS or hosting panel.

**How to backup data?** Backup the `data/` and `Auth/` folders, or use the `.backup` command.

**Prefix resets after restart?** Prefix is stored in the database. Make sure the `data/` folder is not deleted.

**How to add a new menu category?** Create a new subfolder in `plugins/`. It's automatically detected and shown in the menu.

---

## Roadmap

- [ ] RPG quest & mission system
- [ ] Real-time crypto price checker
- [ ] Real-time currency conversion
- [ ] Full group management (welcome, kick, promote)
- [ ] Anti-spam & per-user rate limiter
- [ ] Bug fixes & stabilization

---

## Changelog

**DropByte MSG v3.0.0** *(2026, current)*
Rebranding, hybrid architecture, tax & accounting modules, student tools, RPG system, anonymous menfess, hot reload, canvas terminal dashboard, KPR calculator, 100+ RPG item master data.

**Shota Base v2.x.x** *(2026)*
Modular plugin system, migration to pairing code, multi-owner, SQLite database.

**v1.x.x** *(2023)*
Switch-case system, JSON database, basic features: sticker, ping, eval.

**Early Days** *(2022)*
First experiments with Baileys. Name and structure changed frequently.

---

## Contributing

This repository is **private** and does not accept public contributions. For those with access, follow standard plugin development guidelines and commit conventions.

Report bugs with: command used, error output, reproduction steps, Node.js version and OS.

---

## License

```
PRIVATE PROJECT — All Rights Reserved
Copyright (c) 2022–2026 DropByte MSG

Not for distribution or publication without permission.
```

---

## Credits

[@whiskeysockets/baileys](https://github.com/WhiskeySockets/Baileys) — WhatsApp protocol · Shota Base — architecture foundation · jarr — base developer

---

<div align="center">

<br>

```
  ✦ ✦ ✦
```

**DropByte MSG**

*2022 – 2026 · Still in Development*

*"Not perfect, but always improving."*

<br>

[![WhatsApp](https://img.shields.io/badge/WhatsApp-Developer-25D366?style=flat-square&logo=whatsapp)](https://wa.me/15812414442)
![Private](https://img.shields.io/badge/Project-Private-critical?style=flat-square)

</div>

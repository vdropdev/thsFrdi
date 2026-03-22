<div align="center">

<img src="https://files.catbox.moe/h7cvkw.jpg" width="360" style="border-radius:20px"/>

<br><br>

# DropByte MSG

### *Modular • Evolving • Private*
### WhatsApp Bot Multi Device

<br>

[![Node](https://img.shields.io/badge/Node.js-v18%2B-brightgreen?style=flat-square&logo=node.js)](https://nodejs.org)
[![Baileys](https://img.shields.io/badge/Baileys-whiskeysockets-blueviolet?style=flat-square)](https://github.com/WhiskeySockets/Baileys)
[![Status](https://img.shields.io/badge/Status-In%20Development-orange?style=flat-square)](.)
[![Type](https://img.shields.io/badge/Module-ESM-orange?style=flat-square)](.)
[![DB](https://img.shields.io/badge/Database-SQLite%20%2B%20JSON-yellow?style=flat-square)](.)
[![Version](https://img.shields.io/badge/Version-3.0.0-red?style=flat-square)](.)
[![Since](https://img.shields.io/badge/Since-2022-lightgrey?style=flat-square)](.)
[![Private](https://img.shields.io/badge/Repository-Private-critical?style=flat-square)](.)

<br>

> *"Terus berkembang, terus diperbaiki — dari nol menjadi sesuatu."*

</div>

---

## Daftar Isi

- [Tentang](#tentang)
- [Fitur Unggulan](#fitur-unggulan)
- [Tech Stack](#tech-stack)
- [Persyaratan](#persyaratan)
- [Instalasi](#instalasi)
- [Menjalankan Bot](#menjalankan-bot)
- [Konfigurasi](#konfigurasi)
- [Struktur Proyek](#struktur-proyek)
- [Sistem Plugin](#sistem-plugin)
- [Sistem Case](#sistem-case)
- [Database](#database)
- [Daftar Perintah](#daftar-perintah)
- [Cara Tambah Plugin](#cara-tambah-plugin)
- [Hot Reload](#hot-reload)
- [Environment & Deployment](#environment--deployment)
- [Troubleshooting](#troubleshooting)
- [FAQ](#faq)
- [Roadmap](#roadmap)
- [Changelog](#changelog)
- [Contributing](#contributing)
- [Lisensi](#lisensi)
- [Credits](#credits)

---

## Tentang

**DropByte MSG** adalah proyek WhatsApp Bot Multi Device yang telah berjalan sejak **2022** — melewati banyak perubahan nama, sistem, arsitektur, dan fitur mengikuti perkembangan ekosistem WhatsApp dan update library Baileys.

Proyek ini dibangun di atas **Shota Base** sebagai fondasi, kemudian dikembangkan secara bertahap dengan penambahan fitur-fitur custom. Saat ini bot masih dalam tahap pengembangan aktif — beberapa fitur mungkin belum sempurna dan terdapat bug yang sedang diperbaiki secara berkala.

**Repository bersifat private** — tidak dipublikasikan secara umum.

### Tujuan Proyek

```
  ✦  Membangun bot WhatsApp yang fungsional, modular, dan mudah dikembangkan
  ✦  Menyediakan fitur-fitur yang berguna untuk kebutuhan sehari-hari
  ✦  Belajar dan eksplorasi teknologi Node.js, Baileys, dan sistem plugin
  ✦  Menjadi fondasi untuk pengembangan fitur lebih lanjut
```

### Perjalanan Proyek

```
  2022   ← Awal berdiri, sistem masih sangat sederhana
    │       Nama & struktur sering berubah
    │       Eksperimen berbagai pendekatan
    │
  2023   ← Mulai stabil dengan sistem plugin
    │       Migrasi dari QR ke pairing code
    │       Database mulai terstruktur
    │
  2024   ← Refactor besar, arsitektur hybrid
    │       Tambah modul pajak & akuntansi
    │       Sistem RPG & ekonomi
    │
  2025   ← Pengembangan fitur mahasiswa
    │       Stabilisasi dan perbaikan bug
    │       Update ke Baileys terbaru
    │
  2026   ← DropByte MSG — versi sekarang
              Masih aktif dikembangkan
```

> ⚠️ **Disclaimer:** Bot ini masih dalam pengembangan aktif. Beberapa fitur mungkin belum berfungsi sempurna. Bug yang ditemukan akan diperbaiki secara bertahap.

```
  Total Plugin    : 65+ fitur
  Kategori        : 10 kategori
  Database        : SQLite + JSON
  Module System   : ESM (import/export)
  Login Method    : Pairing Code (tanpa QR)
  Status          : Active Development 🔧
```

---

## Fitur Unggulan

| Kategori | Fitur |
|---|---|
| 🔌 **Arsitektur** | Plugin modular, hybrid case+plugin, hot reload tanpa restart |
| 🔐 **Auth** | Login via pairing code, multi-owner, mode public/self |
| 📋 **Menu** | Auto-detect dari plugin yang ter-load, update otomatis |
| 🗃️ **Database** | SQLite untuk data utama, JSON flat-file untuk RPG |
| ⚔️ **RPG** | Hunt, battle, shop, inventory, leaderboard, menfess |
| 🧾 **Perpajakan** | PPh 21/23/25, PPN, PPnBM, UMKM, PTKP, tarif referensi |
| 📊 **Akuntansi** | BEP, HPP, laba rugi, depresiasi, rasio keuangan, rekonsiliasi bank |
| 🎓 **Mahasiswa** | IP/IPK, target UAS, target IPK kumulatif, sampling penelitian |
| 📁 **File Manager** | Tambah/hapus/ambil plugin & file langsung lewat WhatsApp |
| 🖼️ **Media** | Sticker, toimage, tovid, voice note, tourl |

---

## Tech Stack

```
  Runtime          Node.js v18+
  WhatsApp         @whiskeysockets/baileys (wileys fork)
  Module System    ESM — import / export
  Database         SQLite3 (data utama) + JSON (RPG)
  Media Processing FFmpeg + canvas + jimp + node-webpmux
  Terminal UI      chalk (colored logs)
  HTTP Client      axios + node-fetch
  Date & Time      moment-timezone
  System Info      node-os-utils + os
```

---

## Persyaratan

| Kebutuhan | Versi | Keterangan |
|---|---|---|
| Node.js | ≥ 18.0.0 | Runtime utama |
| npm | ≥ 8.0.0 | Package manager |
| FFmpeg | Latest | Konversi media |
| Git | Latest | Clone repository |
| RAM | ≥ 512 MB | Rekomendasi minimum |
| Storage | ≥ 1 GB | Untuk dependencies & media |

Cek versi Node.js:
```bash
node -v && npm -v
```

Upgrade Node.js ke v20 (jika di bawah v18):
```bash
curl -fsSL https://deb.nodesource.com/setup_20.x | bash -
apt install -y nodejs
```

---

## Instalasi

### Linux / VPS

```bash
# 1. Update sistem & install dependensi OS
apt update && apt upgrade -y
apt install git ffmpeg imagemagick -y

# 2. Clone repository
git clone https://github.com/USERNAME/shota-base
cd shota-base

# 3. Install package
npm install

# 4. Sesuaikan konfigurasi
nano settings.js
```

### Windows

1. Install [Node.js](https://nodejs.org) v18+
2. Install [FFmpeg](https://ffmpeg.org/download.html) — tambahkan ke PATH sistem
3. Install [Git](https://git-scm.com)
4. Buka terminal (CMD/PowerShell) di folder project
5. Jalankan `npm install`

### Pterodactyl / Panel Hosting

```bash
# Di console panel, jalankan:
npm install
node index.js
```

> Pastikan Node.js v18+ tersedia di panel. Ganti versi di pengaturan egg jika perlu.

---

## Menjalankan Bot

```bash
node index.js
```

Saat pertama kali jalan, bot meminta nomor telepon untuk **Pairing Code**:

```
[!] - Enter your number, Example 628:
628xxxxxxxxx

[✓] - Your code : ABCD-EFGH
```

**Cara memasukkan kode di WhatsApp:**
`Pengaturan` → `Perangkat Tertaut` → `Tautkan Perangkat` → `Tautkan dengan Nomor Telepon`

Masukkan kode 8 karakter yang diberikan.

> ⚠️ **Penting:** Setelah pairing berhasil, **restart bot sekali**. Tanpa restart, pesan tidak akan terbaca. Ini adalah known bug dari Baileys.

### Menjalankan dengan PM2 (Rekomendasi Production)

```bash
# Install PM2
npm install -g pm2

# Jalankan bot
pm2 start index.js --name shota-base

# Auto-start saat server reboot
pm2 startup
pm2 save

# Monitor log
pm2 logs shota-base
pm2 monit
```

---

## Konfigurasi

Semua pengaturan ada di `settings.js`. File ini di-watch oleh bot — perubahan langsung aktif tanpa restart.

```js
// ── Kepemilikan ───────────────────────────────
global.owner = ['628xxxxxxxxx']   // bisa lebih dari satu nomor

// ── Identitas Bot ────────────────────────────
global.namaBot   = 'Shota Base'
global.namaOwner = 'jarr'
global.versi     = '3.0.0'
global.url       = 'https://t.me/jarroffc2'

// ── WhatsApp Channel ─────────────────────────
// ID channel untuk forward info di menu
global.idCh = '120363420360528990@newsletter'

// ── Gambar ────────────────────────────────────
global.thumbnail = 'https://link-gambar-menu.jpg'    // thumbnail menu/reply
global.fotoreply = 'https://link-gambar-reply.jpg'   // thumbnail reply biasa

// ── Pesan Penolakan ───────────────────────────
global.mess = {
  owner   : '*[REJECT]* - ONLY OWNER',
  admin   : '*[REJECT]* - ONLY ADMINS GROUPS',
  botAdmin: '*[REJECT]* - BOT HARUS ADMIN',
  group   : '*[REJECT]* - ONLY IN THE GROUP',
  sewa    : '*[REJECT]* - ONLY USER PREMIUM',
  private : '*[REJECT]* - ONLY IN THE PRIVATE CHAT',
}
```

**Prefix & Mode** — dapat diubah live lewat perintah, tersimpan ke SQLite:

```
.setprefix !         → ganti prefix ke !
.prefix on           → aktifkan mode prefix ketat
.prefix off          → nonaktifkan prefix (bebas simbol)
.mode public         → bot merespon semua orang
.mode self           → bot hanya merespon owner
```

---

## Struktur Proyek

```
shota-base/
│
├── index.js                     ← Entry point, koneksi Baileys, pairing code
├── settings.js                  ← Konfigurasi global bot (hot-reload)
├── case.js                      ← Switch-case fallback commands
├── package.json
│
├── src/
│   ├── handler.js               ← Message handler, routing, logging terminal
│   └── plugins.js               ← Plugin loader rekursif, stats, getMenuData
│
├── lib/
│   ├── config.js                ← Serializer pesan Baileys → objek m
│   ├── database.js              ← SQLite helper (users, groups, settings)
│   ├── function.js              ← Global utility (bytesToSize, runtime, dll)
│   ├── items.js                 ← Master data item RPG + emoji konsisten
│   ├── rpg-json.js              ← RPG database JSON (getUser, saveUser, dll)
│   ├── rpg-db.js                ← RPG database SQLite (legacy)
│   └── webp.js                  ← Konversi media ke WebP untuk sticker
│
├── plugins/
│   ├── command/                 ← Command utama
│   │   └── menu.js              → .menu .mani
│   │
│   ├── owner/                   ← Perintah khusus owner
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
│   ├── other/                   ← Fitur umum
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
│   ├── tools/                   ← Konversi media
│   │   ├── toimage.js           → .toimage
│   │   ├── tovid.js             → .tovid
│   │   ├── tovn.js              → .tovn .toptt
│   │   ├── tolid.js             → .tolid
│   │   └── get.js               → .get
│   │
│   ├── grup/                    ← Manajemen grup
│   │   └── antilinkgc.js        → .antilink
│   │
│   ├── rpg/                     ← Sistem RPG & ekonomi
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
│   ├── pajak/                   ← Kalkulator perpajakan Indonesia
│   │   ├── pph21.js             → .pph21
│   │   ├── pph23.js             → .pph23
│   │   ├── pph25.js             → .pph25 .angsuran
│   │   ├── pphumkm.js           → .pphumkm .umkm
│   │   ├── ppn.js               → .ppn
│   │   ├── ppnbm.js             → .ppnbm
│   │   ├── ptkp.js              → .ptkp
│   │   └── tarifpph.js          → .tarifpph .infopajak
│   │
│   ├── akuntansi/               ← Akuntansi & perbankan
│   │   ├── bep.js               → .bep .breakeven
│   │   ├── hpp.js               → .hpp .cogs
│   │   ├── labarugi.js          → .labarugi .pl
│   │   ├── depresiasi.js        → .depresiasi .penyusutan
│   │   ├── rasio.js             → .rasio .ratio
│   │   ├── bunga.js             → .bunga .interest
│   │   ├── rekonsiliasi.js      → .rekonsiliasi .rekon
│   │   └── jurnal.js            → .jurnal
│   │
│   └── mahasiswa/               ← Tools akademik mahasiswa
│       ├── ipk.js               → .ipk .ip
│       ├── konversinilai.js     → .konversi .grade
│       ├── targetuas.js         → .targetuas .uas
│       ├── targetipk.js         → .targetipk
│       └── sampling.js          → .sampling .sampel
│
├── data/
│   ├── database.db              ← SQLite (auto-created)
│   ├── rpg.json                 ← Data RPG JSON (auto-created)
│   ├── owner.json               ← Daftar owner tambahan
│   └── trash/                   ← File media temporary
│
└── Auth/                        ← Session Baileys (auto-created)
```

---

## Sistem Plugin

Plugin adalah file `.js` di dalam folder `plugins/`. Diload otomatis oleh `src/plugins.js` secara **rekursif** — semua subfolder ikut di-scan.

### Format Plugin

```js
const handler = async (m, {
  sock,          // Baileys WASocket
  args,          // string[] argumen setelah command
  text,          // args.join(' ')
  reply,         // function: balas dengan thumbnail
  isOwner,       // boolean
  isAdmin,       // boolean (grup)
  isBotAdmin,    // boolean (grup)
  usedPrefix,    // string prefix yang dipakai
  command,       // string nama command
  mime,          // MIME type quoted message
  qmsg,          // quoted message object
  getGroup,      // function: ambil data grup dari SQLite
  updateData,    // function: update data di SQLite
  getSettings,   // function: ambil settings dari SQLite
}) => {

  // Guard: hanya owner
  if (!isOwner) return reply(global.mess.owner)

  // Cek argumen
  if (!args[0]) return reply(`Cara pakai: ${usedPrefix}command <teks>`)

  // Kirim pesan dengan gambar & thumbnail
  await sock.sendMessage(m.chat, {
    image  : { url: global.thumbnail },
    caption: `Hasil: ${text}`,
    contextInfo: {
      externalAdReply: {
        title             : global.namaBot,
        body              : 'Deskripsi fitur',
        thumbnailUrl      : global.thumbnail,
        sourceUrl         : '',
        mediaType         : 1,
        renderLargerThumbnail: true,
      }
    }
  }, { quoted: m })
}

handler.command = ['namacommand', 'alias']
export default handler
```

### Properti Objek `m`

| Properti | Tipe | Keterangan |
|---|---|---|
| `m.sender` | `string` | JID pengirim (`628xxx@s.whatsapp.net`) |
| `m.chat` | `string` | JID chat tujuan |
| `m.isGroup` | `boolean` | Apakah pesan dari grup |
| `m.fromMe` | `boolean` | Apakah pesan dari bot sendiri |
| `m.pushName` | `string` | Nama pengirim di WhatsApp |
| `m.body` | `string` | Isi teks lengkap pesan |
| `m.text` | `string` | Alias dari `m.body` |
| `m.type` | `string` | Tipe pesan (`conversation`, `imageMessage`, dll) |
| `m.mtype` | `string` | Message type dari Baileys |
| `m.quoted` | `object \| null` | Pesan yang di-quote/reply |
| `m.mentionedJid` | `string[]` | JID yang di-mention |
| `m.key` | `object` | Message key Baileys |
| `m.message` | `object` | Raw message object |
| `m.reply(text)` | `function` | Balas pesan dengan thumbnail |

### Alur Pemrosesan Pesan

```
Pesan Masuk (messages.upsert)
         │
         ▼
   index.js — event listener
         │
         ▼
   handler.js — serialize pesan → objek m
         │
         ├── Parse prefix & command
         │
         ├── Cek isOwner, isAdmin, isBotAdmin
         │
         ├── Build handleData (context object)
         │
         ▼
   plugins.js — loadPlugins()
         │
         ├── Plugin ditemukan? → jalankan plugin(m, handleData)
         │
         └── Tidak ditemukan? → caseSwitch(m, sock, command, handleData)
```

---

## Sistem Case

`case.js` adalah fallback untuk command ringan yang tidak perlu file plugin terpisah. Sangat cocok untuk command satu-dua baris.

```js
export async function caseSwitch(m, sock, command, data) {
  const { reply, args, text, isOwner, usedPrefix } = data

  switch (command) {

    case 'halo':
    case 'hai': {
      await reply(`Halo juga, ${m.pushName}! 👋`)
      break
    }

    case 'info': {
      await reply(`Bot: ${global.namaBot}\nVersi: ${global.versi}`)
      break
    }

    // ← tambah case baru di sini

    default:
      return false   // ← JANGAN diubah
  }

  return true        // ← JANGAN diubah
}
```

> Command di `case.js` otomatis terhitung di `.menu` dan `.totalfitur` lewat `getCaseStats()` yang membaca file ini secara statik.

---

## Database

### SQLite — `data/database.db`

Database utama bot. Diakses lewat `lib/database.js`.

**Tabel `users`**

| Kolom | Tipe | Default | Keterangan |
|---|---|---|---|
| `id` | TEXT | PRIMARY KEY | JID WhatsApp pengguna |
| `name` | TEXT | — | Nama pengguna |
| `limit_val` | INT | 20 | Limit penggunaan fitur |
| `balance` | INT | 0 | Saldo Terra |
| `premium` | INT | 0 | Status premium (0/1) |
| `health` | INT | 100 | HP karakter RPG |
| `stamina` | INT | 100 | Stamina karakter RPG |
| `level` | INT | 1 | Level karakter |
| `exp` | INT | 0 | Experience points |
| `role` | TEXT | Warga | Role/jabatan karakter |
| `potion` | INT | 0 | Stok potion |
| `iron` | INT | 0 | Stok iron |
| `gold` | INT | 0 | Stok gold |
| `diamond` | INT | 0 | Stok diamond |
| `sword` | INT | 0 | Stok sword |

**Tabel `groups`**

| Kolom | Default | Keterangan |
|---|---|---|
| `id` | PRIMARY KEY | JID grup |
| `welcome` | 0 | Pesan sambutan aktif |
| `antilink` | 0 | Anti link grup aktif |
| `antidelete` | 0 | Anti hapus pesan |
| `antiviewonce` | 0 | Anti view once |
| `rpg_mode` | 1 | Mode RPG di grup ini |

**Tabel `settings`**

| Kolom | Default | Keterangan |
|---|---|---|
| `prefix` | `.` | Prefix command aktif |
| `multiprefix` | 0 | Mode prefix ketat (0/1) |
| `public` | 1 | Mode public (1) / self (0) |

**Helper functions di `lib/database.js`:**

```js
getUser(jid, name)              // ambil atau buat user baru
getGroup(jid)                   // ambil atau buat data grup
updateData(table, id, col, val) // update satu kolom
incrementData(table, id, col, val) // tambah nilai kolom
getSettings()                   // ambil settings bot
```

### JSON — `data/rpg.json`

Database untuk sistem RPG — lebih fleksibel, tidak perlu migrasi schema.

```json
{
  "628xxxxxxxxx@s.whatsapp.net": {
    "name"       : "Ferdi",
    "hp"         : 100,
    "maxHp"      : 100,
    "stamina"    : 100,
    "terra"      : 500,
    "inventory"  : {
      "meat"   : 3,
      "potion" : 2,
      "iron"   : 5,
      "bone"   : 1
    },
    "last_daily"  : 1748000000000,
    "last_hunt"   : 1748000000000,
    "last_work"   : 0,
    "last_battle" : 0,
    "last_rest"   : 0,
    "last_quest"  : 0,
    "quest"       : null
  }
}
```

**Helper functions di `lib/rpg-json.js`:**

```js
getUser(jid, name)        // ambil atau buat user RPG
saveUser(jid, user)       // simpan user ke JSON
addItem(user, id, qty)    // tambah item ke inventory
removeItem(user, id, qty) // hapus item dari inventory
hasItem(user, id, qty)    // cek apakah punya item
onCooldown(user, key, ms) // cek apakah masih cooldown
setCooldown(user, key)    // set timestamp cooldown sekarang
fmtCD(ms)                 // format ms → "2j 30m 10d"
getLeaderboard(top)       // ambil top N pemain
```

---

## Daftar Perintah

### 📌 Utama

| Perintah | Alias | Keterangan |
|---|---|---|
| `.menu` | `.mani` | Tampilkan semua menu (auto-detect dari plugin) |

### 🍉 Owner

| Perintah | Keterangan |
|---|---|
| `.eval <kode>` | Jalankan kode JavaScript di runtime bot |
| `.> <kode>` | Eval dengan output langsung |
| `.$ <cmd>` | Jalankan perintah terminal/shell |
| `.q` | Inspect & tampilkan raw quoted message |
| `.restart` | Restart proses bot |
| `.backup` | Backup seluruh file script |
| `.mode public` | Bot merespon semua pengguna |
| `.mode self` | Bot hanya merespon owner |
| `.setprefix <p>` | Ganti prefix command |
| `.prefix on/off` | Aktifkan/nonaktifkan mode prefix ketat |
| `.addow <no>` | Tambah nomor sebagai owner |
| `.delown <no>` | Hapus owner |
| `.listown` | Tampilkan semua owner |
| `.clearsesion` | Hapus sesi login (perlu pairing ulang) |

### 📁 File Manager

| Perintah | Keterangan |
|---|---|
| `.addplugin` | Upload & tambah plugin baru via WA |
| `.delplugin <nama>` | Hapus plugin berdasarkan nama file |
| `.getplugin <nama>` | Download file plugin dari server |
| `.listplugin` | Lihat semua plugin beserta kategori |
| `.gantifile` | Replace file tertentu dengan file baru |
| `.getfile <path>` | Download file dari path server |
| `.listfile` | Lihat semua file di direktori |

### 🍓 Other

| Perintah | Alias | Keterangan |
|---|---|---|
| `.ping` | `.os` | Ping latency + dashboard server (CPU, RAM, disk, network) |
| `.runtime` | `.rt` | Uptime bot sejak terakhir jalan |
| `.sticker` | `.s` | Konversi foto atau video ke sticker WebP |
| `.tourl` | — | Upload media ke URL publik |
| `.totalfitur` | `.ttf` | Hitung total plugin + case aktif |
| `.script` | `.sc` | Info script & versi |
| `.tqto` | `.tq` | Credits & ucapan terima kasih |
| `.menfess <no>.<nama>.<pesan>` | `.cf` | Kirim pesan anonim ke nomor tertentu |
| `.balas <pesan>` | — | Balas menfess (harus reply ke pesan menfess) |
| `.cicilan <harga> <dp%> <tenor> <bunga%>` | `.kpr` | Simulasi cicilan KPR/kredit kendaraan |

### 🔖 Tools

| Perintah | Alias | Keterangan |
|---|---|---|
| `.toimage` | `.toimg` | Konversi sticker/WebP ke gambar |
| `.tovid` | `.tovideo` | Konversi video note ke video biasa |
| `.tovn` | `.toptt` | Konversi video/audio ke voice note |
| `.tolid` | `.getlid` | Ambil link ID dari pesan |
| `.get <url>` | — | Download file dari URL |

### 👥 Grup

| Perintah | Keterangan |
|---|---|
| `.antilink` | Toggle anti-link grup (hapus pesan berisi link WA lain) |

### ⚔️ RPG

| Perintah | Alias | Cooldown | Keterangan |
|---|---|---|---|
| `.profile` | `.me` `.profil` | — | Lihat profil, HP, stamina, Terra |
| `.inventory` | `.inv` `.bag` | — | Lihat semua item dikelompokkan per kategori |
| `.daily` | `.harian` | 24 jam | Klaim hadiah harian (Terra + Potion) |
| `.hunt` | `.berburu` | 30 detik | Berburu — dapat loot item acak |
| `.work` | `.kerja` | 1 jam | Kerja — dapat Terra + item bonus |
| `.battle` | `.fight` | 1 menit | Lawan monster — skalabel dengan level |
| `.rest` | `.istirahat` | 15 menit | Pulihkan HP & Stamina |
| `.shop` | `.toko` | — | Lihat toko item |
| `.shop <item>` | `.beli` | — | Beli item dari toko |
| `.use <item>` | `.pakai` | — | Pakai item konsumable (potion, food) |
| `.leaderboard` | `.lb` `.top` | — | Ranking pemain berdasarkan Terra |

### 🧾 Perpajakan

| Perintah | Keterangan |
|---|---|
| `.pph21 <gaji> <status> <tanggungan>` | PPh 21 karyawan — tarif progresif, PTKP, biaya jabatan |
| `.pph23 <jenis> <bruto>` | PPh 23 — dividen 15%, jasa/sewa 2%, dengan/tanpa NPWP |
| `.pph25 <terutang> <kredit>` | Angsuran PPh 25 bulanan |
| `.pphumkm <omzet bulan> <omzet YTD>` | PPh Final UMKM 0,5% (PP 55/2022), cek batas 500 juta |
| `.ppn <harga> [tarif]` | PPN 11% atau tarif custom |
| `.ppnbm <harga> <tarif>` | PPnBM 10%–75% dengan identifikasi objek |
| `.ptkp [status] [tanggungan]` | Cek PTKP atau tampilkan tabel lengkap |
| `.tarifpph` | Referensi lengkap semua tarif pajak 2024 |

### 📊 Akuntansi & Perbankan

| Perintah | Keterangan |
|---|---|
| `.bep <b.tetap> <harga> <b.variabel>` | Break Even Point unit & rupiah + simulasi target laba |
| `.hpp <p.awal> <beli> <beban> <retur> <p.akhir>` | Harga Pokok Penjualan — pembelian bersih |
| `.labarugi <pend> <hpp> <b.ops> <b.lain> <p.lain>` | Simulasi laporan laba rugi + PPh Badan 22% |
| `.depresiasi <metode> <harga> <n.sisa> <umur>` | Penyusutan aset — Garis Lurus, Saldo Menurun, SYD |
| `.rasio <jenis> <val1> <val2>` | 10 rasio keuangan (likuiditas, solvabilitas, profitabilitas, aktivitas) |
| `.bunga <metode> <pokok> <bunga%> <tenor>` | Bunga bank — flat, efektif, anuitas, deposito, compound |
| `.rekonsiliasi <saldo buku> <saldo bank> <...>` | Rekonsiliasi bank + jurnal penyesuaian otomatis |
| `.jurnal [jenis]` | Panduan jurnal 12 jenis transaksi perbankan |

### 🎓 Mahasiswa

| Perintah | Keterangan |
|---|---|
| `.ipk <matkul:nilai:sks> ...` | Hitung IP semester dari daftar matkul + konversi nilai |
| `.konversi <nilai>` | Konversi angka → huruf → bobot 4.0 & 5.0 |
| `.targetuas <b.UTS> <n.UTS> <b.Tgs> <n.Tgs> <b.UAS> <target>` | Nilai UAS minimal + simulasi semua skenario |
| `.targetipk <ipk> <sks lulus> <sks baru> <target>` | IP semester depan yang dibutuhkan untuk target IPK kumulatif |
| `.sampling <rumus> <N> [margin]` | Ukuran sampel — Slovin, Krejcie & Morgan, Cochran |

---

## Cara Tambah Plugin

### 1. Buat file plugin baru

Letakkan di folder yang sesuai, contoh `plugins/other/namafitur.js`:

```js
const handler = async (m, { sock, args, text, reply, usedPrefix, isOwner, isAdmin }) => {

  // ── Guard (opsional) ──────────────────────────
  if (!isOwner) return reply(global.mess.owner)

  // ── Panduan penggunaan ────────────────────────
  if (!args[0]) {
    return sock.sendMessage(m.chat, {
      image  : { url: global.thumbnail },
      caption: `📌 *Nama Fitur*\n\nCara pakai:\n\`${usedPrefix}namacommand <argumen>\`\n\nContoh:\n\`${usedPrefix}namacommand hello\``,
      contextInfo: {
        externalAdReply: {
          title            : global.namaBot,
          body             : 'Deskripsi singkat fitur',
          thumbnailUrl     : global.thumbnail,
          sourceUrl        : '',
          mediaType        : 1,
          renderLargerThumbnail: true,
        }
      }
    }, { quoted: m })
  }

  // ── Logika utama ──────────────────────────────
  const hasil = `Kamu memasukkan: ${text}`

  await sock.sendMessage(m.chat, {
    image  : { url: global.thumbnail },
    caption: hasil,
    contextInfo: {
      externalAdReply: {
        title            : global.namaBot,
        body             : 'Nama Fitur',
        thumbnailUrl     : global.thumbnail,
        sourceUrl        : '',
        mediaType        : 1,
        renderLargerThumbnail: true,
      }
    }
  }, { quoted: m })
}

// Daftarkan command (huruf kecil semua)
handler.command = ['namacommand', 'alias1', 'alias2']
export default handler
```

### 2. Selesai

Plugin **langsung aktif** tanpa restart. Menu `.menu` otomatis menampilkan plugin baru di kategori sesuai nama foldernya.

### Tips

- Satu file = satu fitur utama
- Nama file = nama fitur (lowercase, tanpa spasi)
- Folder = kategori (muncul di menu)
- Selalu sertakan panduan penggunaan jika tidak ada argumen
- Gunakan `global.thumbnail` & `global.fotoreply` agar konsisten

---

## Hot Reload

Bot menggunakan `fs.watchFile` pada semua file inti. Jika file diubah (disimpan), bot otomatis reload file tersebut tanpa perlu restart penuh.

```
~> Update File : /home/container/settings.js
~> Update File : /home/container/src/handler.js
~> Update File : /home/container/plugins/rpg/hunt.js
```

**File yang di-watch secara otomatis:**

| File | Keterangan |
|---|---|
| `index.js` | Entry point |
| `settings.js` | Konfigurasi global |
| `src/handler.js` | Message handler |
| `src/plugins.js` | Plugin loader |
| `lib/config.js` | Message serializer |
| Semua `plugins/**/*.js` | Auto-reload saat plugin diubah |

> Plugin yang baru ditambah via `.addplugin` langsung tersedia karena plugin loader menggunakan dynamic `import()` + cache-busting (`?update=timestamp`).

---

## Environment & Deployment

### VPS / Linux Server

```bash
# Jalankan langsung
node index.js

# Atau dengan PM2 (rekomendasi)
pm2 start index.js --name shota-base
pm2 logs shota-base --lines 100
```

### Pterodactyl Panel

1. Upload semua file ke panel
2. Pastikan egg menggunakan Node.js v18+
3. Startup command: `node index.js`
4. Jalankan install: `npm install` di console

### Railway / Render / Heroku

```bash
# Procfile (sudah tersedia)
worker: node index.js
```

Tambahkan environment variable jika diperlukan lewat dashboard platform.

### Docker (Opsional)

```dockerfile
FROM node:20-alpine
RUN apk add --no-cache ffmpeg
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
CMD ["node", "index.js"]
```

```bash
docker build -t shota-base .
docker run -d --name shota-base shota-base
```

---

## Troubleshooting

### Pesan tidak terbaca setelah pairing

**Solusi:** Restart bot sekali setelah pairing berhasil. Ini adalah known bug dari Baileys.

```bash
# Ctrl+C untuk stop, lalu
node index.js
```

---

### Error: Cannot find module 'xxx'

**Solusi:** Dependensi belum terinstall atau versi salah.

```bash
npm install
# Jika masih error:
rm -rf node_modules package-lock.json
npm install
```

---

### Plugin tidak muncul di menu

**Kemungkinan penyebab:**
1. File tidak memiliki `handler.command = [...]`
2. `export default handler` tidak ada
3. Ada syntax error di file plugin

Cek log terminal — error plugin ditampilkan saat startup:
```
Gagal memuat plugin di /path/to/plugin.js: SyntaxError: ...
```

---

### Bot tidak merespon command

**Cek urutan:**
1. Prefix sudah benar? Coba `.menu`
2. Mode bot — apakah aktif self mode? Cek dengan `.mode`
3. Plugin terdaftar? Cek `.listplugin`
4. Ada error di terminal?

---

### Session expired / logout

**Solusi:** Hapus folder `Auth/` dan jalankan ulang untuk pairing baru.

```bash
rm -rf Auth/
node index.js
```

---

### Error SQLite database locked

**Solusi:** Hanya boleh ada satu instance bot yang berjalan. Matikan semua instance sebelumnya.

```bash
# Cek proses yang berjalan
pm2 list
# Stop semua
pm2 stop all
# Jalankan ulang
pm2 start index.js --name shota-base
```

---

## FAQ

**Q: Apakah bisa dijalankan di HP (Termux)?**

A: Bisa, namun tidak direkomendasikan untuk penggunaan production. Gunakan VPS atau panel hosting untuk stabilitas lebih baik.

---

**Q: Apakah bisa multi-session (lebih dari satu nomor)?**

A: Bisa dengan cara menjalankan beberapa instance di port/folder berbeda, masing-masing dengan folder `Auth/` terpisah.

---

**Q: Bagaimana cara backup data?**

A: Backup folder `data/` (berisi database.db, rpg.json, owner.json) dan folder `Auth/` (sesi login). Atau gunakan perintah `.backup`.

---

**Q: Prefix berubah sendiri setelah restart?**

A: Prefix disimpan di SQLite. Pastikan file `data/database.db` tidak terhapus. Jika hilang, prefix kembali ke default `.`.

---

**Q: Bagaimana cara menambah kategori menu baru?**

A: Buat subfolder baru di `plugins/`, misalnya `plugins/ekonomi/`. Semua plugin di dalamnya otomatis masuk kategori "Ekonomi" di menu. Tambahkan emoji di objek `catEmoji` di `plugins/command/menu.js` jika ingin emoji khusus.

---

**Q: Apakah bisa menggunakan prefix lebih dari satu karakter?**

A: Bisa. Set dengan `.setprefix !!` atau edit langsung di SQLite/settings.

---

## Roadmap

Fitur dan perbaikan yang direncanakan ke depan. Urutan tidak menjamin prioritas — tergantung waktu dan kebutuhan.

### 🔧 Bug & Stabilitas
- [ ] Perbaikan bug plugin RPG yang tidak konsisten
- [ ] Optimasi load time plugin saat startup
- [ ] Error handling lebih baik di semua plugin
- [ ] Validasi input yang lebih robust

### 🆕 Fitur Baru
- [ ] Sistem quest & misi RPG
- [ ] Kalkulator kripto — cek harga real-time (CoinGecko API)
- [ ] Kalkulator konversi mata uang real-time
- [ ] Sistem group management lebih lengkap (welcome, kick, promote)
- [ ] Anti-spam & rate limiter per pengguna
- [ ] Fitur reminder & scheduler

### 🏗️ Arsitektur
- [ ] Sistem konfigurasi per-guild/grup yang lebih fleksibel
- [ ] Logging sistem yang lebih terstruktur
- [ ] Unit test untuk fungsi-fungsi kritis

### 📚 Dokumentasi
- [x] README lengkap ✅
- [ ] Dokumentasi API internal plugin
- [ ] Contoh plugin untuk berbagai use case

---

## Changelog

> Proyek ini telah melewati banyak iterasi sejak 2022 — perubahan nama, sistem, arsitektur, dan fitur mengikuti perkembangan teknologi dan kebutuhan.

### DropByte MSG v3.0.0 — 2025–2026 *(current)*
- Rebranding dari Shota Base → **DropByte MSG**
- Arsitektur hybrid plugin + case yang lebih bersih
- Sistem menu auto-detect dari plugin ter-load
- Login via pairing code (tanpa QR)
- Database dual: SQLite (main) + JSON (RPG)
- Modul perpajakan lengkap — PPh 21/23/25, PPN, PPnBM, UMKM, PTKP
- Modul akuntansi & perbankan — BEP, HPP, depresiasi, rasio, rekonsiliasi bank
- Tools mahasiswa — IP/IPK, target UAS, target IPK, sampling penelitian
- Sistem RPG — hunt, battle, shop, inventory, leaderboard
- Menfess & sistem balas anonim
- Hot reload semua file utama
- Terminal dashboard visual dengan canvas
- Kalkulator cicilan KPR/kredit
- Master data 100+ item RPG dengan emoji konsisten
- 🔧 *Masih dalam pengembangan aktif, beberapa fitur beta*

### Shota Base v2.x.x — 2024
- Sistem plugin modular diperkenalkan
- Migrasi autentikasi dari QR scan ke pairing code
- Multi-owner support
- Database SQLite menggantikan JSON murni
- Perbaikan berbagai bug koneksi

### v1.x.x — 2023
- Sistem case switch sebagai fondasi utama
- Database JSON sederhana
- Fitur dasar: sticker, ping, eval
- Struktur masih monolitik

### Awal Mula — 2022
- Eksperimen pertama dengan Baileys
- Nama dan struktur sering berganti
- Belajar ekosistem WhatsApp bot dari nol
- Berbagai percobaan arsitektur yang tidak stabil

---

## Contributing

Repository ini bersifat **private** dan tidak menerima kontribusi publik secara langsung.

Namun jika kamu adalah bagian dari tim atau mendapat akses khusus, berikut panduan pengembangan:

### Panduan Pengembangan Plugin

- Satu file = satu fitur yang jelas
- Selalu sertakan panduan penggunaan jika tanpa argumen
- Gunakan `global.thumbnail` & `global.fotoreply` untuk konsistensi tampilan
- Nama command lowercase, tanpa spasi
- Tambahkan komentar di logika yang kompleks
- Test plugin secara menyeluruh sebelum deploy

### Standar Commit

```
feat     : tambah fitur baru
fix      : perbaiki bug
refactor : refaktor kode tanpa mengubah fungsi
docs     : update dokumentasi
style    : perubahan format/style kode
chore    : maintenance, update dependency
```

### Melaporkan Bug

Temukan bug? Catat dengan detail:
- Perintah yang digunakan
- Output/error yang muncul
- Langkah reproduksi
- Versi Node.js dan OS

---

## Lisensi

```
PRIVATE PROJECT — All Rights Reserved

Copyright (c) 2022–2026 DropByte MSG

Proyek ini bersifat PRIVATE dan tidak didistribusikan secara publik.
Dilarang menyalin, memodifikasi, mendistribusikan, atau menggunakan
kode ini tanpa izin tertulis dari pemilik proyek.

Repository tidak dipublikasikan. Akses hanya untuk pihak yang
mendapat izin langsung dari developer.
```

---

## Credits

| Kontribusi | Keterangan |
|---|---|
| [@whiskeysockets/baileys](https://github.com/WhiskeySockets/Baileys) | Protokol WhatsApp Multi Device |
| [wileys](https://www.npmjs.com/package/wileys) | Fork Baileys yang digunakan |
| [Shota Base](.) | Fondasi arsitektur bot ini |
| Developer | jarr — pengembang utama base |

---

<div align="center">

<br>

<img src="https://files.catbox.moe/h7cvkw.jpg" width="120" style="border-radius:50%"/>

<br><br>

```
  ✦ ✦ ✦
```

### DropByte MSG

*Dari eksperimen kecil di 2022 — terus tumbuh hingga sekarang.*

**2022 – 2026 · Still in Development · Built with ❤️**

<br>

> *"Tidak sempurna, tapi terus diperbaiki."*

<br>

[![Telegram](https://img.shields.io/badge/Developer-jarr-blue?style=flat-square&logo=telegram)](https://t.me/jarroffc2)
[![Status](https://img.shields.io/badge/Status-Private%20Project-critical?style=flat-square)](.)
[![Built On](https://img.shields.io/badge/Built%20on-Shota%20Base-blueviolet?style=flat-square)](.)

</div>

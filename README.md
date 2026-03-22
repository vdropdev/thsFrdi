<div align="center">

<img src="https://files.catbox.moe/h7cvkw.jpg" width="340" style="border-radius:20px"/>

<br><br>

# DropByte MSG

### *Modular · Evolving · Private*

<br>

[![Node](https://img.shields.io/badge/Node.js-v18%2B-brightgreen?style=flat-square&logo=node.js)](https://nodejs.org)
[![Baileys](https://img.shields.io/badge/Baileys-whiskeysockets-blueviolet?style=flat-square)](https://github.com/WhiskeySockets/Baileys)
[![Status](https://img.shields.io/badge/Status-In%20Development-orange?style=flat-square)](.)
[![Since](https://img.shields.io/badge/Since-2022-lightgrey?style=flat-square)](.)
[![Private](https://img.shields.io/badge/Repository-Private-critical?style=flat-square)](.)

<br>

> *"Dari eksperimen kecil di 2022 — terus tumbuh hingga sekarang."*

</div>

---

## Tentang

**DropByte MSG** adalah WhatsApp Bot Multi Device yang telah berjalan sejak **2022**, melewati banyak perubahan nama, sistem, dan arsitektur mengikuti perkembangan teknologi.

Dibangun di atas **Shota Base** sebagai fondasi, kemudian dikembangkan secara bertahap dengan fitur-fitur custom. Bot ini masih dalam tahap pengembangan aktif — beberapa fitur mungkin belum sempurna dan terus diperbaiki.

**Repository bersifat private.**

---

## Perjalanan Proyek

| Tahun | Keterangan |
|---|---|
| 2022 | Awal berdiri — eksperimen pertama, nama & struktur sering berganti |
| 2023 | Mulai stabil, sistem plugin diperkenalkan |
| 2024 | Refactor besar, arsitektur hybrid, database lebih terstruktur |
| 2025 | Penambahan modul pajak, akuntansi, tools mahasiswa |
| 2026 | Rebranding → **DropByte MSG**, pengembangan lanjutan |

---

## Tujuan

- Membangun bot WhatsApp yang fungsional dan mudah dikembangkan
- Menyediakan fitur yang berguna untuk kebutuhan sehari-hari
- Eksplorasi dan belajar ekosistem Node.js & Baileys
- Menjadi fondasi untuk pengembangan fitur lebih lanjut

---

## Tech Stack

| Komponen | Teknologi |
|---|---|
| Runtime | Node.js v18+ |
| Protokol WA | @whiskeysockets/baileys |
| Module System | ESM (import/export) |
| Database | SQLite + JSON |
| Media | FFmpeg, canvas, jimp |

---

## Fitur

| Kategori | Deskripsi |
|---|---|
| 🔌 **Sistem** | Plugin modular, hybrid case+plugin, hot reload |
| 🔐 **Auth** | Login via pairing code, multi-owner, mode public/self |
| 📋 **Menu** | Auto-detect dari plugin yang ter-load |
| ⚔️ **RPG** | Hunt, battle, shop, inventory, leaderboard |
| 🧾 **Perpajakan** | PPh 21/23/25, PPN, PPnBM, UMKM, PTKP |
| 📊 **Akuntansi** | BEP, HPP, laba rugi, depresiasi, rasio, rekonsiliasi bank |
| 🎓 **Mahasiswa** | IP/IPK, target UAS, target IPK, sampling penelitian |
| 💬 **Sosial** | Menfess & balas anonim |
| 📁 **File Manager** | Kelola plugin & file langsung lewat WA |
| 🖼️ **Media** | Sticker, konversi video, voice note, tourl |

---

## Daftar Perintah

### 📌 Utama
`.menu` — tampilkan semua menu

### 🍉 Owner
`.eval` · `.restart` · `.backup` · `.mode` · `.setprefix` · `.addow` · `.delown` · `.listown` · `.clearsesion`

### 📁 File Manager
`.addplugin` · `.delplugin` · `.getplugin` · `.listplugin` · `.gantifile` · `.getfile` · `.listfile`

### 🍓 Other
`.ping` · `.sticker` · `.tourl` · `.runtime` · `.totalfitur` · `.menfess` · `.balas` · `.cicilan`

### 🔖 Tools
`.toimage` · `.tovid` · `.tovn` · `.tolid` · `.get`

### ⚔️ RPG

| Perintah | Cooldown | Keterangan |
|---|---|---|
| `.profile` | — | Lihat profil & statistik |
| `.inventory` | — | Lihat inventaris item |
| `.daily` | 24 jam | Klaim hadiah harian |
| `.hunt` | 30 detik | Berburu loot |
| `.work` | 1 jam | Kerja untuk Terra |
| `.battle` | 1 menit | Lawan monster |
| `.rest` | 15 menit | Pulihkan HP & Stamina |
| `.shop` | — | Toko & beli item |
| `.use` | — | Pakai item |
| `.leaderboard` | — | Ranking pemain |

### 🧾 Perpajakan
`.pph21` · `.pph23` · `.pph25` · `.pphumkm` · `.ppn` · `.ppnbm` · `.ptkp` · `.tarifpph`

### 📊 Akuntansi
`.bep` · `.hpp` · `.labarugi` · `.depresiasi` · `.rasio` · `.bunga` · `.rekonsiliasi` · `.jurnal`

### 🎓 Mahasiswa
`.ipk` · `.konversi` · `.targetuas` · `.targetipk` · `.sampling`

---

## Cara Tambah Plugin

Buat file di folder `plugins/<kategori>/namafitur.js` dengan format:

```js
const handler = async (m, { sock, args, reply, usedPrefix }) => {
  if (!args[0]) return reply(`Cara pakai: ${usedPrefix}command <argumen>`)

  // logika di sini
  await reply('Hasil')
}

handler.command = ['command', 'alias']
export default handler
```

Plugin langsung aktif dan otomatis muncul di menu — tanpa edit file lain.

---

## Instalasi

```bash
# Clone & install
git clone <repo-url>
cd dropbyte-msg
npm install

# Jalankan
node index.js
```

Saat pertama kali jalan, masukkan nomor WA untuk mendapatkan **pairing code**.
Lalu masukkan kode di: `WhatsApp → Perangkat Tertaut → Tautkan dengan Nomor Telepon`

> Setelah pairing, **restart bot sekali** agar pesan mulai terbaca.

---

## Roadmap

- [ ] Sistem quest & misi RPG
- [ ] Cek harga kripto real-time
- [ ] Konversi mata uang real-time
- [ ] Group management lebih lengkap
- [ ] Anti-spam & rate limiter
- [ ] Perbaikan bug & stabilisasi

---

## Catatan

- Bot masih dalam pengembangan aktif, beberapa fitur mungkin belum sempurna
- Bug yang ditemukan akan diperbaiki secara bertahap
- Folder `data/trash/` aman dihapus berkala untuk hemat storage
- Jangan hapus folder `data/` dan `Auth/` kecuali ingin reset penuh

---

## Lisensi

```
PRIVATE PROJECT — All Rights Reserved
Copyright (c) 2022–2026 DropByte MSG

Tidak untuk didistribusikan atau dipublikasikan tanpa izin.
```

---

## Credits

- [@whiskeysockets/baileys](https://github.com/WhiskeySockets/Baileys) — protokol WhatsApp
- Shota Base — fondasi arsitektur
- jarr — developer base

---

<div align="center">

<br>

```
  ✦ ✦ ✦
```

**DropByte MSG**

*2022 – 2026 · Still in Development*

<br>

[![Contact](https://img.shields.io/badge/WhatsApp-Developer-25D366?style=flat-square&logo=whatsapp)](https://wa.me/15812414442)
[![Status](https://img.shields.io/badge/Project-Private-critical?style=flat-square)](.)

</div>

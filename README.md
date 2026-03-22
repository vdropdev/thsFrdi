<div align="center">

<img src="https://files.catbox.moe/h7cvkw.jpg" width="320" style="border-radius:18px"/>

<br><br>

# DropByte MSG

*Modular · Evolving · Private*

<br>

![Node](https://img.shields.io/badge/Node.js-v18+-brightgreen?style=flat-square&logo=node.js)
![Baileys](https://img.shields.io/badge/Baileys-whiskeysockets-blueviolet?style=flat-square)
![Status](https://img.shields.io/badge/Status-In_Development-orange?style=flat-square)
![Since](https://img.shields.io/badge/Since-2022-lightgrey?style=flat-square)
![Private](https://img.shields.io/badge/Repo-Private-critical?style=flat-square)

<br>

*"Dari eksperimen kecil di 2022 — terus tumbuh hingga sekarang."*

</div>

---

## Overview

**DropByte MSG** adalah WhatsApp Bot Multi Device yang telah berjalan sejak 2022, melewati banyak perubahan nama, sistem, dan arsitektur mengikuti perkembangan teknologi. Dibangun di atas **Shota Base** sebagai fondasi, kemudian dikembangkan secara bertahap dengan fitur-fitur custom.

Bot ini masih dalam tahap pengembangan aktif. Beberapa fitur mungkin belum sempurna dan terus diperbaiki secara berkala. Repository bersifat **private**.

---

## Perjalanan

```
2022  Awal berdiri — eksperimen pertama, nama & sistem sering berganti
2023  Mulai stabil — sistem plugin diperkenalkan
2024  Refactor besar — arsitektur hybrid, database lebih terstruktur  
2025  Penambahan modul pajak, akuntansi, tools mahasiswa
2026  Rebranding → DropByte MSG, pengembangan lanjutan
```

---

## Tujuan

Membangun bot WhatsApp yang fungsional, modular, dan mudah dikembangkan. Menyediakan fitur yang berguna untuk kebutuhan sehari-hari sekaligus menjadi media eksplorasi teknologi Node.js dan ekosistem Baileys. Dirancang sebagai fondasi solid untuk pengembangan fitur lebih lanjut ke depan.

---

## Tech Stack

Runtime yang digunakan adalah **Node.js v18+** dengan protokol **@whiskeysockets/baileys** (wileys fork). Menggunakan sistem module **ESM** (import/export), database **SQLite** untuk data utama dan **JSON flat-file** untuk data RPG. Media diproses menggunakan FFmpeg, canvas, dan jimp.

---

## Fitur

| | Kategori | Deskripsi |
|---|---|---|
| 🔌 | Sistem | Plugin modular, hot reload, menu auto-detect dari plugin ter-load |
| 🔐 | Auth | Login via pairing code, multi-owner, mode public/self |
| ⚔️ | RPG | Hunt, battle, shop, inventory, leaderboard, sistem ekonomi Terra |
| 🧾 | Perpajakan | PPh 21/23/25, PPN, PPnBM, UMKM, PTKP, referensi tarif 2024 |
| 📊 | Akuntansi | BEP, HPP, laba rugi, depresiasi, rasio keuangan, rekonsiliasi bank |
| 🎓 | Mahasiswa | IP/IPK, target UAS, target IPK kumulatif, sampling penelitian |
| 💬 | Sosial | Menfess & sistem balas anonim antar pengguna |
| 💳 | Finansial | Kalkulator cicilan KPR, kredit motor/mobil |
| 📁 | File Manager | Kelola plugin & file server langsung lewat WA |
| 🖼️ | Media | Sticker, konversi video, voice note, upload ke URL |

---

## Daftar Perintah

### General
`.menu` — tampilkan semua menu (auto-detect)

---

### Owner
`.eval` `.restart` `.backup` `.mode` `.setprefix` `.addow` `.delown` `.listown` `.clearsesion`

---

### File Manager
`.addplugin` `.delplugin` `.getplugin` `.listplugin` `.gantifile` `.getfile` `.listfile`

---

### Other
`.ping` `.sticker` `.tourl` `.runtime` `.totalfitur` `.menfess` `.balas` `.cicilan`

---

### Tools
`.toimage` `.tovid` `.tovn` `.tolid` `.get`

---

### RPG

| Perintah | Cooldown | Keterangan |
|---|---|---|
| `.profile` | — | Profil & statistik karakter |
| `.inventory` | — | Inventaris item dikelompokkan per kategori |
| `.daily` | 24 jam | Klaim hadiah harian |
| `.hunt` | 30 detik | Berburu — dapat loot item acak |
| `.work` | 1 jam | Kerja — dapat Terra & item bonus |
| `.battle` | 1 menit | Lawan monster, skalabel dengan level |
| `.rest` | 15 menit | Pulihkan HP & Stamina |
| `.shop` | — | Lihat toko item |
| `.shop <item>` | — | Beli item dari toko |
| `.use <item>` | — | Pakai item konsumable |
| `.leaderboard` | — | Ranking pemain berdasarkan Terra |

---

### Perpajakan

| Perintah | Keterangan |
|---|---|
| `.pph21` | PPh 21 karyawan — tarif progresif, PTKP, biaya jabatan |
| `.pph23` | PPh 23 — dividen, jasa, royalti, sewa |
| `.pph25` | Angsuran PPh 25 bulanan |
| `.pphumkm` | PPh Final UMKM 0,5% — cek batas omzet |
| `.ppn` | PPN 11% atau tarif custom |
| `.ppnbm` | PPnBM barang mewah 10%–75% |
| `.ptkp` | Cek PTKP atau tampilkan tabel lengkap |
| `.tarifpph` | Referensi semua tarif pajak 2024 |

---

### Akuntansi & Perbankan

| Perintah | Keterangan |
|---|---|
| `.bep` | Break Even Point unit & rupiah + simulasi target laba |
| `.hpp` | Harga Pokok Penjualan |
| `.labarugi` | Simulasi laporan laba rugi + PPh Badan |
| `.depresiasi` | Penyusutan aset — Garis Lurus, Saldo Menurun, SYD |
| `.rasio` | 10 rasio keuangan — likuiditas, solvabilitas, profitabilitas |
| `.bunga` | Bunga bank — flat, efektif, anuitas, deposito, compound |
| `.rekonsiliasi` | Rekonsiliasi bank + jurnal penyesuaian otomatis |
| `.jurnal` | Panduan jurnal 12 jenis transaksi perbankan |

---

### Mahasiswa

| Perintah | Keterangan |
|---|---|
| `.ipk` | Hitung IP semester dari daftar matkul |
| `.konversi` | Konversi nilai angka → huruf → bobot 4.0/5.0 |
| `.targetuas` | Nilai UAS minimal + simulasi semua skenario |
| `.targetipk` | IP yang dibutuhkan untuk capai target IPK kumulatif |
| `.sampling` | Ukuran sampel — Slovin, Krejcie & Morgan, Cochran |

---

## Instalasi

```bash
git clone <repo-url>
cd dropbyte-msg
npm install
node index.js
```

Saat pertama jalan, masukkan nomor WA untuk mendapat **pairing code**. Lalu masukkan kode di WhatsApp melalui Pengaturan → Perangkat Tertaut → Tautkan dengan Nomor Telepon.

Setelah pairing berhasil, restart bot sekali agar pesan mulai terbaca.

---

## Menjalankan dengan PM2

```bash
npm install -g pm2
pm2 start index.js --name dropbyte-msg
pm2 save && pm2 startup
```

---

## Konfigurasi

Semua pengaturan ada di `settings.js`. File ini mendukung hot reload — perubahan langsung aktif tanpa restart. Yang bisa dikonfigurasi: nomor owner, nama bot, versi, gambar thumbnail, gambar reply, dan pesan penolakan otomatis.

Prefix dan mode bot dapat diubah langsung lewat perintah dan tersimpan ke database.

---

## Sistem Plugin

Setiap fitur adalah file `.js` terpisah di dalam folder `plugins/`. Diload secara otomatis dan rekursif — termasuk semua subfolder. Plugin baru langsung aktif tanpa restart dan otomatis muncul di menu.

---

## Hot Reload

Bot menggunakan `fs.watchFile` pada semua file utama. Jika file diubah, bot otomatis reload tanpa perlu restart penuh. Berlaku untuk semua file konfigurasi, handler, dan plugin.

---

## Database

Menggunakan dua database yang bekerja paralel. **SQLite** untuk data utama pengguna, pengaturan grup, prefix, dan mode bot. **JSON flat-file** untuk data RPG yang lebih fleksibel seperti inventory, cooldown, dan quest.

---

## Deployment

Bisa dijalankan di VPS Linux, Pterodactyl panel, Railway, Render, atau Heroku. Procfile sudah disertakan untuk platform berbasis Heroku. Untuk Docker, cukup base image Node.js dengan FFmpeg.

---

## Troubleshooting

**Pesan tidak terbaca setelah pairing** — restart bot sekali, ini known bug dari Baileys.

**Module tidak ditemukan** — jalankan `npm install` ulang.

**Plugin tidak muncul di menu** — pastikan file memiliki `handler.command` dan `export default`.

**Session expired** — hapus folder `Auth/` dan jalankan ulang untuk pairing baru.

---

## FAQ

**Bisa dijalankan di Termux?**
Bisa, tapi tidak direkomendasikan untuk production. Gunakan VPS atau panel hosting.

**Cara backup data?**
Backup folder `data/` dan `Auth/`. Atau gunakan perintah `.backup`.

**Prefix berubah setelah restart?**
Prefix disimpan di database. Pastikan folder `data/` tidak terhapus.

**Cara tambah kategori menu baru?**
Buat subfolder baru di `plugins/`. Otomatis terbaca dan muncul di menu.

---

## Roadmap

- [ ] Sistem quest & misi RPG
- [ ] Cek harga kripto real-time
- [ ] Konversi mata uang real-time
- [ ] Group management lebih lengkap (welcome, kick, promote)
- [ ] Anti-spam & rate limiter per pengguna
- [ ] Perbaikan bug & stabilisasi

---

## Changelog

**DropByte MSG v3.0.0** *(2025–2026, current)*
Rebranding, arsitektur hybrid, modul pajak & akuntansi, tools mahasiswa, RPG, menfess, hot reload, terminal dashboard canvas.

**Shota Base v2.x.x** *(2024)*
Sistem plugin modular, migrasi ke pairing code, multi-owner, database SQLite.

**v1.x.x** *(2023)*
Sistem case switch, database JSON, fitur dasar sticker & ping.

**Awal** *(2022)*
Eksperimen pertama dengan Baileys. Nama dan struktur sering berganti.

---

## Lisensi

```
PRIVATE PROJECT — All Rights Reserved
Copyright (c) 2022–2026 DropByte MSG

Tidak untuk didistribusikan atau dipublikasikan tanpa izin.
```

---

## Credits

[@whiskeysockets/baileys](https://github.com/WhiskeySockets/Baileys) — protokol WhatsApp · Shota Base — fondasi arsitektur · jarr — developer base

---

<div align="center">

<br>

**DropByte MSG**

*2022 – 2026 · Still in Development*

<br>

[![WhatsApp](https://img.shields.io/badge/WhatsApp-Developer-25D366?style=flat-square&logo=whatsapp)](https://wa.me/15812414442)
![Private](https://img.shields.io/badge/Project-Private-critical?style=flat-square)

</div>

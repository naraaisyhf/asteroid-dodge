# PLAN.md — Universal 2D Arcade Game Roadmap (Untuk Siswa)

Dokumen ini adalah rencana kerja universal dan log perkembangan proyek pembuatan game arcade 2D dalam 1 file `index.html`. Dokumen ini diperbarui secara otomatis oleh AI setiap kali ada perubahan kode sebelum push ke GitHub.

---

## 1. Ikhtisar Game

- **Judul Game**: Asteroid Dodge — Endless Runner
- **Genre**: 2D Arcade Game
- **Format**: Single-File HTML (`index.html`) tanpa dependensi eksternal
- **Platform**: Web Browser (Desktop & Mobile Responsive)
- **Audio**: Web Audio API Sintetis
- **Penyimpanan**: LocalStorage (`arcade_leaderboard`, `arcade_last_username`, `arcade_theme`, `arcade_sound`)
- **Kebijakan Caching**: Zero-Cache (`no-cache, no-store, must-revalidate`)
- **Deployment**: GitHub Pages (Branch `main`, path `/`) → `https://naraisyhf.github.io/asteroid-dodge/`

---

## 2. Fase Pengembangan Universal

### Phase 0: Brainstorming & Desain Game
- [x] Siswa menentukan ide & tema game: **Asteroid Dodge** (endless runner, hindari asteroid).
- [x] Kontrol: keyboard panah/A-D + sentuh & geser untuk mobile.
- [x] Aturan: skor bertambah tiap detik + bonus asteroid terlewat; tabrakan = game over; level naik tiap 15 detik.
- [x] Gaya visual: Retro Neon Glow dengan dukungan tema gelap & terang.

### Phase 1: Setup Single-File `index.html`
- [x] Buat kerangka HTML5 dengan meta tag **Zero-Cache**.
- [x] Siapkan kanvas responsif dengan rasio layar tetap.
- [x] Susun struktur kode modular 8 blok di JavaScript.
- [x] Siapkan game loop utama (`requestAnimationFrame`).

### Phase 2: Username & Leaderboard LocalStorage
- [x] Buat modal input username dengan validasi nama (2–15 karakter, anti-XSS).
- [x] Simpan dan baca username terakhir dari `arcade_last_username`.
- [x] Buat fungsi penyimpanan dan penyortiran Top 10 skor di `arcade_leaderboard`.
- [x] Buat tampilan antarmuka (UI) tabel peringkat skor di menu game.

### Phase 3: Mekanik Inti Permainan (Core Gameplay)
- [x] Sistem status game (`MENU`, `PLAYING`, `PAUSED`, `GAMEOVER`).
- [x] Karakter pemain (pergerakan dan batas layar).
- [x] Rintangan / musuh (kecepatan, variasi ukuran, dan pola kemunculan).
- [x] Deteksi tabrakan (Collision Detection) dan perhitungan skor.
- [x] Power-up Shield (tahan 1 tabrakan) dan Slow-Mo (5 detik).

### Phase 4: Efek Suara & Visual Juice
- [x] Efek suara arcade sintetis dengan Web Audio API (Start, Power-Up, Shield Pecah, Level Up, Tabrakan, Game Over).
- [x] Efek ledakan partikel sederhana saat tabrakan/poin didapat.
- [x] Efek getar layar (screen shake) saat tabrakan dan game over.
- [x] Starfield parallax, particle trail, dan flash level.

### Phase 5: Publikasi GitHub Pages
- [x] Inisialisasi git dan branch `main` (commit lokal).
- [x] Buat repository GitHub publik via GitHub CLI (`gh repo create`): `naraaisyhf/asteroid-dodge`.
- [x] Aktifkan GitHub Pages (REST API `POST /repos/.../pages`, source `main` root `/`); build pertama sukses.
- [x] Kompatibilitas Google AI Studio: Sediakan snippet perintah terminal siap salin jika proyek dilanjutkan lewat antarmuka web (lihat README).
- [ ] Pantau status workflow build di tab Actions (`gh run list`). — N/A: Pages legacy build (tanpa workflow), build berstatus `built`.
- [ ] Tes live demo (`https://naraisyhf.github.io/asteroid-dodge/`) — **BLOCKED eksternal**: URL publik mengembalikan 404 karena akun `naraisyhf` juga 404 untuk publik (kemungkinan akun ditinjau/dibatasi GitHub). Repository & Pages sudah ada dan push berhasil (diverifikasi via `git ls-remote`).

---

## 3. Matriks Tugas & Status Pelaksanaan

| ID | Tugas / Fitur | Fase | Status | Pelaksana | Catatan |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **T-00** | Pembuatan template `AGENTS.md` & `PLAN.md` untuk Siswa | Fondasi | `DONE` | AI | Template standar single model siap |
| **T-01** | Brainstorming Ide & Konsep Game Spesifik | Phase 0 | `DONE` | Siswa | Terpilih: Asteroid Dodge (endless runner) |
| **T-02** | Pembuatan Skeleton `index.html` & Meta Zero-Cache | Phase 1 | `DONE` | AI | Kanvas responsif, 8 blok modular, rAF loop |
| **T-03** | Modul Input Username & Leaderboard Top 10 | Phase 2 | `DONE` | AI | LocalStorage CRUD, validasi anti-XSS, UI tabel |
| **T-04** | Logika Pergerakan, Rintangan & Tabrakan | Phase 3 | `DONE` | AI | Level scaling, collision, shield, slow-mo |
| **T-05** | Efek Suara Synth Web Audio API & Partikel | Phase 4 | `DONE` | AI | Audio sintetis, particle trail, screen shake |
| **T-06** | Deployment GitHub Pages via GitHub CLI (`gh`) | Phase 5 | `BLOCKED` | AI | Repo `naraaisyhf/asteroid-dodge` + Pages build `built`; URL publik 404 karena akun GitHub dibatasi |

*Status: `TODO` | `IN-PROGRESS` | `DONE` | `BLOCKED`*

---

## 4. Changelog & Riwayat Revisi

| Versi | Tanggal | Pelaksana | Ringkasan Perubahan | Referensi Commit |
| :--- | :--- | :--- | :--- | :--- |
| **v0.3.1** | 2026-11-14 | AI | Repo publik `naraaisyhf/asteroid-dodge` dibuat & di-push; GitHub Pages diaktifkan dan build sukses; URL publik 404 karena pembatasan akun GitHub | `66e5b99` |
| **v0.3.0** | 2026-11-14 | AI | Implementasi penuh Asteroid Dodge (canvas, leaderboard, audio, power-up, tema) + README & commit lokal; deploy remote tertunda | `66e5b99` |
| **v0.2.2** | 2026-10-24 | AI | Menambahkan panduan alur integrasi khusus Google AI Studio & penegasan repo wajib Public | `07475fb` |
| **v0.2.1** | 2026-10-24 | AI | Menambahkan panduan detail aktivasi GitHub Pages (CLI gh api & Web UI visual) serta troubleshooting | `3aaf671` |
| **v0.2.0** | 2026-10-24 | AI | Konfigurasi ulang ke Single Model AI untuk siswa, modularisasi 8 blok kode, dan penyesuaian matriks tugas | `2954bb0` |
| **v0.1.0** | 2026-10-24 | AI | Inisialisasi awal file sistem `AGENTS.md` dan universal blueprint `PLAN.md` | `47aa88e` |

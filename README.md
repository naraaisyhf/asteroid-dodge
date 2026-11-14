# Asteroid Dodge

> Game arcade 2D endless runner: hindari hujan asteroid, kumpulkan power-up, dan rebut peringkat teratas papan skor. Dibuat sebagai materi belajar siswa dalam satu file `index.html`.

Game dapat dimainkan langsung dengan membuka `index.html` di browser — tanpa build tools, tanpa dependensi eksternal, tanpa server.

## Fitur Utama

- **Gameplay endless** — asteroid jatuh makin cepat dan rapat setiap 15 detik (level naik).
- **Power-up** — Shield menahan satu tabrakan, Slow-Mo memperlambat asteroid selama 5 detik.
- **Kontrol ganda** — Panah kiri/kanan atau A/D di keyboard, sentuh & geser di perangkat mobile.
- **Papan skor Top 10** — tersimpan di `localStorage` (`arcade_leaderboard`) dengan validasi nama pilot anti-XSS.
- **Audio sintetis** — efek suara dibuat langsung dengan Web Audio API, tanpa file audio.
- **Juice visual** — starfield parallax, particle trail, ledakan, screen shake, dan indikator level.
- **Tema gelap & terang** — toggle manual, preferensi tersimpan.
- **Single-file** — Vanilla HTML5, CSS3, dan ES6 JavaScript (No Build Tools).
- **Zero-cache** — meta tag mencegah browser menyajikan versi lama setelah update.

## Struktur Data

```json
{
  "arcade_leaderboard": [
    { "name": "Nova", "score": 4321, "date": 1763160000000 }
  ],
  "arcade_last_username": "Nova",
  "arcade_theme": "dark",
  "arcade_sound": "1"
}
```

## Cara Menjalankan Secara Lokal

Buka `index.html` langsung di browser, atau gunakan server statis:

```bash
python3 -m http.server 8000
# lalu buka http://localhost:8000
```

## Deploy ke GitHub Pages

```bash
git init
git branch -M main
git add .
git commit -m "feat: initial release of Asteroid Dodge"
gh repo create asteroid-dodge --public --source=. --remote=origin --push
gh api --method POST -H "Accept: application/vnd.github+json" \
  /repos/<username>/asteroid-dodge/pages \
  -f source='{"branch":"main","path":"/"}'
```

Live demo: `https://<username>.github.io/asteroid-dodge/`

## Kontrol

| Aksi | Keyboard | Sentuh |
| --- | --- | --- |
| Bergerak | `←` `→` / `A` `D` | Sentuh & geser |
| Jeda / Lanjut | `Esc` / `P` | Tombol pause |
| Mulai / Ulang | `Enter` / `Space` | Tombol |

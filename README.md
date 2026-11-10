# Goi N3 – Flashcard SRS (6 minggu)

Aplikasi flashcard kosakata N3 (971 kartu, 36 pelajaran) dengan jadwal ulang ala Anki.
Seluruh aplikasi ada di satu file: `index.html`. `deck.json` hanya salinan data kartu (opsional).

## Skema yang disarankan: dua repo

| Repo | Isi | Visibilitas |
|---|---|---|
| `goi-n3` | `index.html`, `deck.json`, `README.md` | Public (isinya hanya kosakata) |
| `goi-n3-progres` | `progress.json` (dibuat otomatis) | Private |

### 1. Repo aplikasi (public)
1. Buat repo `goi-n3`, unggah `index.html`.
2. Settings → Pages → Source: *Deploy from a branch* → `main` / root.
3. Alamatnya: `https://NAMAKAMU.github.io/goi-n3/`

### 2. Repo progres (private)
1. Buat repo `goi-n3-progres` (Private) dan centang *Add a README* agar branch `main` sudah ada.

### 3. Token
1. GitHub → Settings → Developer settings → Personal access tokens → **Fine-grained tokens** → Generate.
2. Repository access: *Only select repositories* → pilih `goi-n3-progres`.
3. Permissions → Repository → **Contents: Read and write**.
4. Salin token (diawali `github_pat_`).

### 4. Hubungkan di aplikasi
Buka aplikasi → tab **Simpan** → bagian *Sinkron otomatis ke GitHub*:
- Repo: `NAMAKAMU/goi-n3-progres`
- Branch: `main`, Path: `progress.json`
- Tempel token → **Simpan dan sinkron**

Ulangi langkah ini di HP, laptop, dan tablet (token ditempel sekali per perangkat). Progres yang sama langsung termuat.

## Catatan
- Setiap penilaian kartu dikirim ke repo setelah jeda sekitar 4 detik, jadi satu commit bisa mencakup beberapa kartu.
- Offline tetap bisa belajar; perubahan dikirim saat koneksi kembali.
- Jangan menilai kartu di dua perangkat bersamaan. Bentrokan digabung per kartu menurut waktu penilaian terbaru.
- Safari bisa menghapus data situs yang lama tidak dibuka. Kalau token hilang, tempel lagi. Progres di repo aman.
- Token bocor? Cabut di GitHub; yang terancam hanya repo progres itu.

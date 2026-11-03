# Realita AI — content pack

Paket produksi serial film pendek vertikal untuk personal branding Sam (CTO ConexLab).
Enam film, satu ide per film, semua gambar dan suara dibuat dengan kode memakai library
[Lemo-Opuscar](https://github.com/lemomo-ai/lemo-opuscar) (66 style film). Tanpa video model,
tanpa stock footage, tanpa generator gambar.

Repo ini bukan kode aplikasi. Isinya materi, aturan, dan brief yang sudah jadi. Yang
mengeksekusi adalah agent AI (Opus 5.5 di Hyperagent, atau Claude Code lokal).

---

## Kalau kamu agent AI, baca ini dulu

Kamu diminta membuat salah satu film dari repo ini. Ikuti urutannya, jangan improvisasi.

1. **Baca `00-BRAND-VOICE.md` sampai habis.** Itu hukumnya: persona, formula suara, palet,
   tipografi, safe zone vertikal, struktur 54 detik. Semua yang kamu tulis harus lolos dokumen itu.
2. **Baca `01-KNOWLEDGE-BASE.md`.** Itu satu-satunya sumber fakta. Kalau sebuah angka atau
   klaim tidak ada di sana, jangan dipakai dan jangan dikarang. Ubah kalimatnya supaya tidak
   butuh angka.
3. **Pilih satu film dari `02-SLATE.md`.** Satu film satu ide. Kalau materinya terasa butuh
   dua ide, itu dua film, bukan satu film yang padat.
4. **Ambil file siap pakai di `04-PASTE/film-0N-*.md`.** File itu sudah mandiri: setup
   sandbox, aturan merek, brief lengkap, dan daftar deliverable. Kamu tidak perlu membuka
   file lain untuk mengeksekusinya.
5. **Jangan mengubah isi brief tanpa alasan.** Kalau kamu mengubah sesuatu (memecah kalimat,
   menyesuaikan durasi, mengganti satu kata), catat di `TREATMENT.md` bagian "yang saya ubah".
6. **Verifikasi sebelum menyerahkan.** Jalankan pemeriksaan di bagian [QC](#qc-sebelum-menyerahkan).
   Jangan melaporkan selesai tanpa keluaran perintah yang nyata.

Aturan yang paling sering dilanggar agent, dan tidak boleh:

- Frame pertama harus sudah terbaca penuh dalam 0,6 detik. Bukan frame setengah jadi.
- Subtitle di pita y 1330–1450. Tidak ada teks penting di bawah y 1500 (zona UI Reels).
- Margin kanan minimal 120 px. Tidak ada objek yang menutupi teks, termasuk pensil atau garis.
- Teks sekunder minimal 22 px pada kanvas 1080. Kalau tidak muat, buang elemennya.
- Tanpa em dash, tanpa emoji, tanpa hype, tanpa ajakan semangat di akhir.
- Tanpa nama klien, tanpa angka dari proyek lain.

---

## Isi repo

| Path | Isi |
|---|---|
| `00-BRAND-VOICE.md` | Persona The Growth Architect, formula suara, larangan bahasa, palet resmi, tipografi, safe zone, struktur 54 detik. Wajib dibaca lebih dulu. |
| `01-KNOWLEDGE-BASE.md` | Materi: identitas, keyakinan, delapan analogi, bukti lapangan, 4M Framework, bank 28 hook, penutup, daftar larangan. |
| `02-SLATE.md` | Enam film musim pertama, urutan rilis, aturan lintas film, dua film opsional. |
| `02-slate-preview.html` | Tampilan slate dalam satu halaman, untuk dilihat manusia. |
| `03-BRIEFS/` | Brief sumber per film, plus `00-hyperagent-master.md` (panduan operasional Hyperagent). |
| `04-PASTE/` | Enam file siap tempel. **Ini yang dipakai.** Masing-masing sudah lengkap dan mandiri. |
| `05-CONTENT-MINE.md` | Bedah vault versi AI saja: 18 film dalam 4 kelompok, 5 titik temu, aturan attribusi. |
| `06-AI-RESOURCES.md` | Inventaris seluruh resource AI di vault, mana yang sudah dipakai, 20 ide cadangan. |

Semua angka di repo ini berasal dari pengalaman dan catatan sendiri. Tidak ada data klien.

## Musim pertama

| # | Film | Style Lemo | Inti | Durasi |
|---|---|---|---|---|
| 01 | Pertanyaan yang Salah | `swiss-motion` | Pertanyaan soal AI yang diajukan ke bisnis sejak awal keliru | 52 dtk |
| 02 | Akuarium | `watercolor` | AI memperbesar kondisi, bukan memperbaikinya | 50 dtk |
| 03 | Tarkam | `pictogram-motion` | AI butuh lapangan dengan aturan, bukan kekacauan | 52 dtk |
| 04 | Data di HP Sales | `iso-infographic` | Data bukan berkas, data adalah kemampuan memutuskan | 54 dtk |
| 05 | Titik Berangkat | `transit-map` | 4M: rute hanya benar kalau titik mulai jujur | 54 dtk |
| 06 | Standar Minimum | `risograph` | Yang kalah bukan yang tidak bisa, tapi yang cuma menonton | 50 dtk |

Urutan pengerjaan: 01 sebagai patokan nada, lalu 02 dan 03 berpasangan, lalu 04, lalu 05
sendiri karena film IP, terakhir 06 sebagai penutup musim.

## Cara pakai di Hyperagent

Satu thread satu film. Sandbox Hyperagent tidak mewarisi file antar thread, karena itu setiap
paste file membawa setup sendiri.

1. Buka thread baru, pilih model **Opus 5.5**, reasoning high.
2. Salin seluruh isi `04-PASTE/film-01-pertanyaan.md`, tempel, kirim.
3. Biarkan jalan 30 sampai 60 menit. Agent sudah diinstruksikan untuk tidak bertanya.
4. Di akhir, minta `mp4`, `poster.jpg`, `.srt`, `TREATMENT.md`, `CREDITS`, dan `build.sh`
   sebagai artifact yang bisa diunduh, dengan path absolut.
5. Tonton hasilnya. Kalau ada catatan, kirim di thread yang sama, sandbox masih hidup.

Maksimal tiga thread paralel. Render WebGL saling berebut CPU kalau kebanyakan.

Syarat sandbox: Node 20+, Python 3.11+, **ffmpeg 7+**, git, headless Chrome, akses jaringan
untuk edge-tts. Kalau `ffmpeg -version` di bawah 7, pasang static build. Di ffmpeg 6 mux gagal
karena durasi audio dilaporkan salah.

## Cara pakai lokal (macOS)

```bash
git clone --depth 1 https://github.com/lemomo-ai/lemo-opuscar.git ~/lemo-opuscar
cd ~/lemo-opuscar
sh plugin/skills/lemo-opuscar/scripts/setup.sh deps
sh plugin/skills/lemo-opuscar/scripts/setup.sh deps voice

# satu film
mkdir -p films/realita-01
# taruh index.html, film.js, lines.json milik brief di situ, lalu:
node core/render/still.mjs films/realita-01 1.0 --out films/realita-01/stills   # cek tampilan cepat
sh films/realita-01/build.sh                                                    # render + mux
```

Voice Indonesia lewat edge-tts, bukan model berbayar:

```bash
.venv/bin/python core/tts/tts_zh.py --text "kalimat" --voice id-ID-ArdiNeural \
  --rate +0% --pitch -2Hz --out voices/01.mp3
```

`tts_zh.py` generik meski namanya Mandarin. Ia menerima voice edge-tts apa pun.

## Spesifikasi keluaran

- Video 1080×1920, 24 fps, H.264, loudness −14 LUFS.
- Durasi 48 sampai 56 detik.
- Subtitle Indonesia burned in, plus satu berkas `.srt` terpisah.
- `poster.jpg` diambil dari frame tanpa subtitle.
- Tidak ada frame hitam, tidak ada NaN, tidak ada teks terpotong.

## QC sebelum menyerahkan

```bash
ffprobe -v error -show_entries format=duration,size \
  -show_entries stream=width,height,r_frame_rate -of default=noprint_wrappers=1 \
  films/<slug>/<slug>.mp4

ffmpeg -hide_banner -i films/<slug>/<slug>.mp4 -af ebur128 -f null - 2>&1 | grep -E '^\s+I:'

node core/render/readcheck.mjs films/<slug> --size 1080x1920   # wajib 0 BAD
```

`readcheck` **wajib** memakai `--size 1080x1920`. Tanpa itu, film vertikal dilaporkan
"outside frame" secara palsu karena pemeriksa memakai asumsi 1920×1080.

Setelah tiga perintah itu lolos, lihat filmnya. Ambil delapan frame, buat contact sheet, dan
periksa: ada elemen terpotong, ada frame terlalu kosong atau terlalu padat, hierarki terbaca
di ukuran ponsel, subtitle menutupi isi, dan tiga perbaikan paling berharga. Satu putaran
perbaikan itu normal. Dua putaran adalah batas.

## Troubleshooting

| Gejala | Sebab dan tindakan |
|---|---|
| `mux.sh` menolak berkas yang sebenarnya utuh | ffmpeg 6.x melaporkan durasi audio salah lewat loudnorm. Pasang ffmpeg 7+. |
| `window.READY` timeout | Error di halaman. Cek console log, biasanya font atau module path. |
| Render 50 detik lebih dari 25 menit | Turunkan `--workers` ke 2, atau render 720×1280 untuk review. |
| Voice keluar bahasa lain | `tts_zh.py` dipanggil tanpa `--voice`. Tambahkan `--voice id-ID-ArdiNeural`. |
| Subtitle ketutup UI Reels | Pita subtitle harus y 1330–1450, bukan di bawah 1500. |
| Teks kecil tidak terbaca | Minimum 22 px. Buang elemen, jangan kecilkan teks. |

## Status

Musim pertama selesai di tahap rencana dan brief. Belum ada film yang diproduksi dari paket
ini. Satu uji produksi lokal dipakai untuk mengukur mutu dan menemukan aturan safe zone,
tetapi materinya berasal dari topik lain dan tidak dipakai di sini.

## Lisensi dan kredit

Materi dan brief: milik Sam, boleh dipakai untuk produksi kontennya sendiri.
Library Lemo-Opuscar: MIT, milik Lemomo. Semua aset pihak ketiga (voice edge-tts Microsoft,
font OFL) dicatat di berkas `CREDITS` tiap film. Jangan menaruh credit LemoLab di dalam film,
credit hanya di berkas.

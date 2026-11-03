# Cara menjalankan semuanya di Hyperagent

Satu thread = satu film. Sandbox Hyperagent tidak mewarisi file antar thread, jadi setiap
thread harus menyiapkan library sendiri. Karena itu folder `04-PASTE/` berisi enam file
yang sudah **lengkap dan mandiri**: aturan merek, materi, dan brief ada di dalamnya.
Tempel satu file utuh, tidak perlu menambah apa pun.

## Urutan kerja

1. **EP 01** dulu. Paling jelas, jadi patokan nada untuk lima film lain.
2. **EP 02 dan EP 03** berpasangan, keduanya analogi. Boleh dua thread paralel.
3. **EP 04** setelah itu, karena ini film bukti dan butuh ketenangan visual.
4. **EP 05** IP, kerjakan sendiri, jangan paralel dengan film lain.
5. **EP 06** terakhir, penutup musim.

Jangan jalankan lebih dari tiga thread sekaligus. Render WebGL di sandbox saling berebut
CPU kalau kebanyakan.

## Yang harus ada di Hyperagent

Sandbox Linux dengan Node 24, Python 3, git, npm, pip, ffmpeg, dan headless Chrome.
Lemo butuh **Node 20+, ffmpeg 7+, Python 3.11+**. Kalau `ffmpeg -version` masih 6.x, agent
harus memasang static build, bukan lanjut, karena mux akan gagal.

Voice Indonesia memakai edge-tts, perlu jaringan. Voice `id-ID-ArdiNeural` untuk suara
laki-laki tenang, `id-ID-GadisNeural` kalau ingin perempuan. Pakai
`core/tts/tts_zh.py --voice ...` yang menerima voice edge-tts apa pun.

## Cara pakai satu thread

1. Buka thread baru di Hyperagent, pilih model **Opus 5.5**, reasoning high.
2. Salin seluruh isi `04-PASTE/film-01-pertanyaan.md`, tempel, kirim.
3. Biarkan jalan. Satu film 30 sampai 60 menit waktu agent. Jangan menyela untuk pertanyaan
   kecil, agent sudah diinstruksikan untuk tidak bertanya.
4. Di akhir, agent menyerahkan `mp4`, `poster.jpg`, `.srt`, `TREATMENT.md`, `CREDITS`, dan
   `build.sh`. Minta semuanya sebagai artifact yang bisa diunduh.
5. Tonton mp4-nya. Kalau ada catatan, kirim di thread yang sama, sandbox-nya masih hidup.

## Kalau ada yang macet

| Gejala | Yang harus dilakukan agent |
|---|---|
| `mux.sh` gagal soal durasi audio | ffmpeg di bawah 7. Pasang static build. |
| `window.READY` timeout | Ada error di page. Cek console log, biasanya font atau module path. |
| Render 50 detik lebih dari 25 menit | Turunkan `--workers` ke 2, atau render 720×1280 untuk review. |
| Voice keluar bahasa lain | `tts_zh.py` dipanggil tanpa `--voice`. Tambahkan `--voice id-ID-ArdiNeural`. |
| Teks keluar frame atau ketutup UI Reels | Baca ulang bagian safe zone di dalam paste file. |

## Biaya

Satu film 50 detik biasanya 30 sampai 60 menit waktu agent. Dengan credit 500 dolar, satu
musim enam film masih lega, termasuk satu atau dua putaran perbaikan per film. Yang paling
menghabiskan waktu bukan render, tapi menulis dan memperbaiki kode gambar.

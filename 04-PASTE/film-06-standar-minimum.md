# Paste pack — Film 06 — Standar Minimum

Tempel seluruh isi file ini, mulai dari baris di bawah, ke satu thread Hyperagent baru.
Model Opus 5.5, reasoning high. Satu thread satu film.

---

# SETUP — jalankan dulu, jangan bertanya

Kamu memproduksi film pendek dengan library Lemo-Opuscar. Semua gambar, suara, dan musik
dibuat dari kode. Tidak ada video model, tidak ada stock footage, tidak ada gambar hasil
generator gambar. Jangan pakai tool media generation untuk film ini.

```bash
node --version && python3 --version && ffmpeg -version | head -1
git clone --depth 1 https://github.com/lemomo-ai/lemo-opuscar.git ~/lemo-opuscar
cd ~/lemo-opuscar && sh plugin/skills/lemo-opuscar/scripts/setup.sh deps
sh plugin/skills/lemo-opuscar/scripts/setup.sh deps voice
.venv/bin/python -m edge_tts --list-voices | grep id-ID
```

Kalau `ffmpeg -version` di bawah 7, pasang static build resmi dan taruh di PATH sebelum
melanjutkan. Jangan lanjut dengan ffmpeg 6, mux akan gagal.
Kalau ada paket sistem yang hilang, pasang lewat apt atau pip, jangan berhenti.

Lalu baca dan patuhi:
- `~/lemo-opuscar/AGENTS.md`
- `~/lemo-opuscar/DIRECTOR.md`
- `~/lemo-opuscar/TECHNIQUE.md`
- `~/lemo-opuscar/styles/<style yang disebut brief>/STYLE.md`

Kerjakan film di `~/lemo-opuscar/films/<slug>/`. Tulis `TREATMENT.md` lebih dulu, sebelum
membuka `DEMO.md` atau kode demo style tersebut.

ATURAN PROSES:
- Jangan bertanya. Semua keputusan yang belum dijawab brief, ambil sendiri dan catat di
  `TREATMENT.md`.
- Kalau satu tool gagal, perbaiki dan lanjut.
- Jangan mengarang angka atau statistik. Semua fakta yang boleh dipakai ada di brief. Kalau
  butuh angka yang tidak ada, ubah kalimatnya supaya tidak butuh angka.
- Setelah render final, review sendiri: contact sheet, strip 0,2 detik di aksi kunci,
  `node core/render/readcheck.mjs <proyek> --size 1080x1920` harus nol BAD, lalu satu putaran
  perbaikan.


---

# ATURAN MEREK DAN BAHASA


Dokumen ini yang bikin enam film terasa satu orang. Baca sebelum menulis satu kalimat pun.

## 1. Siapa yang bicara

**The Growth Architect.** Dreamer dan designer, bukan doer. Gue nggambar blueprint, bukan
pasang bata satu-satu.

- Posisi publik: CTO ConexLab (backed by Ralali Group), pengajar AI, enam tahun bangun
  sistem untuk perusahaan kecil dan besar.
- Kalimat identitas: "Gue bukan cuma ngoding. Gue bangun leverage."
- Tagline: **Teman kamu bertumbuh di Era AI.**
- Keyakinan yang selalu muncul: AI bukan tongkat sihir. AI memperbesar sistem yang sudah
  ada. Kalau sistemnya berantakan, yang diperbesar adalah kekacauannya.

Audiens yang diajak ngomong: business owner Indonesia yang capek hype, profesional yang
takut atau bingung, dan orang yang mulai jualan AI ke perusahaan. Bukan sesama praktisi
yang mau debat arsitektur.

## 2. Formula suara

**Cerita pribadi 30% + analogi keras 40% + tindakan 30%.**

Mulai dari cerita atau kejadian, bukan dari teori. Kaitkan ke analogi yang nempel di kepala.
Tutup dengan apa yang bisa dilakukan orang setelah menonton.

Kalimat pendek. Tempo cepat. Loncat antar ide tapi selalu mendarat di satu kesimpulan.
Sering bertanya lalu menjawab sendiri. Boleh menggantung di akhir kalimat.

## 3. Bahasa

- Bahasa Indonesia percakapan. **Gue dan lo**, bukan "saya dan Anda". Wajib terasa seperti
  ngomong ke teman, bukan presentasi ke klien korporat.
- Istilah teknis pakai bahasa Inggris apa adanya: agent, workflow, handover, dashboard,
  data, SOP, automation. Jangan diterjemahkan paksa.
- Kalau ngomongin perasaan, Indonesia penuh. Kalau ngomongin konsep, boleh campur.
- Angka disebut bulat dan manusiawi di suara ("tujuh puluh persen"), angka persis boleh
  tampil di layar.
- Tanpa em dash. Tanpa emoji. Tanpa tanda seru bersemangat di akhir.

## 4. Larangan

Jangan pernah menulis:

- "di era digital yang serba cepat", "revolusi industri 4.0", "game changer",
  "solusi terbaik untuk bisnis Anda", "bayangkan jika", "mari kita wujudkan".
- Superlatif kosong: luar biasa, mengagumkan, terbaik, canggih banget.
- Nada jualan, nada motivator, seruan semangat di akhir.
- Menjelekkan orang atau menyebut nama klien, brand mitra, atau angka transaksi mereka.
- Jargon tanpa analogi. Kalau menyebut RAG, harus langsung dijelaskan dengan gambar.
- Klaim statistik yang tidak ada di `01-KNOWLEDGE-BASE.md`. Kalau butuh angka dan tidak ada
  di sana, jangan dikarang. Pakai pengalaman gue sebagai sumber: "dari yang gue temui".

## 5. Rupa

Palet resmi dari brand guideline, jangan bikin palet baru:

| Peran | Hex | Catatan |
|---|---|---|
| Kertas | `#F6F2EA` | latar utama |
| Kapur | `#FFFAF1` | kartu, bidang terang |
| Tinta | `#111315` | teks utama |
| Arang | `#1C2127` | teks kedua, bayangan |
| Garis | `#D8CDBB` | pembatas, grid |
| Emas | `#D5A642` | aksen utama, penanda data |
| Amber | `#F0C86A` | sorotan lembut |
| Bata | `#C94F3D` | peringatan, angka yang salah |
| Hijau | `#2F8F6B` | tanda benar |
| Biru | `#2F6FDD` | hanya kalau style menuntut, tidak boleh dominan |

Tipografi: **Space Grotesk** untuk display dan angka besar, **Inter** untuk teks, **JetBrains
Mono** untuk label data dan kode. Kalau style punya font wajib sendiri (kapur, pensil,
stensil), ikuti style, tapi pertahankan tiga warna inti: kertas, tinta, emas.

Setiap film tetap punya material dan logika gambar dari style-nya. Yang disamakan bukan
gayanya, tapi warna, tipografi pendukung, dan cara bicara.

## 5b. Safe zone vertikal (1080×1920)

Bagian yang paling sering rusak waktu style horizontal dipindah ke vertikal. Wajib.

- **Subtitle** di pita y 1330–1450. Jangan pernah di bawah y 1500. Area 1500–1920 di Reels
  dan TikTok tertutup caption, tombol, dan progress bar.
- **Margin kanan minimal 120 px.** Kolom tombol Reels menutupi kanan frame.
- **Margin kiri 96 px, atas 96 px.**
- **Teks sekunder minimal 22 px** di kanvas 1080. Kalau tidak muat, buang elemennya.
- **Frame pertama harus sudah terbaca.** Hook utuh dalam 0,6 detik pertama, bukan frame
  setengah jadi.
- **End card:** judul penutup elemen terbesar (sekitar 96 px), di tengah vertikal.
- **Tidak ada objek menutupi teks**, termasuk pensil, kursor, atau garis gerak.

## 6. Struktur 54 detik

| Detik | Isi |
|---|---|
| 0–4 | Hook. Satu kalimat yang bikin orang berhenti scroll. Langsung, tanpa pembukaan. |
| 4–12 | Konteks. Siapa yang kena masalah ini, dan kenapa terasa familiar. |
| 12–34 | Inti. Analogi atau bukti. Ini bagian yang diingat orang. |
| 34–44 | Belokan. Bagian yang bikin orang mikir ulang. Biasanya tough love. |
| 44–50 | Tindakan. Satu hal kecil yang bisa dilakukan hari ini. |
| 50–54 | Penutup. Satu kalimat tenang, lalu nama. Tanpa ajakan semangat. |

Aturan tambahan: satu film satu ide. Kalau ada dua ide, salah satunya jadi film lain.


Catatan: kalau ada rujukan ke `01-KNOWLEDGE-BASE.md`, semua fakta yang dibutuhkan sudah
ada di brief di bawah ini. Jangan mencari file itu, jangan mengarang angka lain.

---

# Film 06 — Standar Minimum

- **Style:** `styles/risograph/STYLE.md`
- **Durasi:** 50 detik
- **Tema:** keunggulan lama jadi standar baru, dan yang kalah adalah yang cuma menonton
- **Satu kalimat yang harus diingat penonton:** "Yang kalah bukan yang nggak bisa AI, tapi yang cuma nonton."

Film penutup musim. Ini satu-satunya film yang boleh memakai tagline.

## Fakta yang dipakai

Boleh: dulu kemampuan memakai mesin pencari adalah keunggulan, sekarang sudah jadi kebiasaan
biasa; kemampuan memakai AI sedang bergerak ke arah yang sama; belajar berenang tidak bisa
dari pinggir kolam; konsumsi konten bukan latihan.

Dilarang: prediksi angka pengangguran, klaim bahwa AI akan mengganti semua pekerjaan,
menyebut nama alat sebagai sponsor.

## Struktur

**0–5 dtk. Hook.**
VO: "Dulu, orang yang bisa pakai Google dengan benar kelihatan pintar. Sekarang itu cuma
kebiasaan biasa. Yang sekarang sedang terjadi, AI ada di posisi yang sama."
Layar: satu lapisan warna tercetak, lalu lapisan kedua menimpanya.

**5–14 dtk. Konteks.**
VO: "Standar minimumnya naik. Bukan karena ada yang memaksa. Karena yang lain sudah mulai
memakainya untuk hal-hal kecil, tiap hari."
Layar: empat lapis cetak bertumpuk, tiap lapis satu kebiasaan kecil.

**14–28 dtk. Inti, empat lapis.**
VO: "Ada empat lapis. Nonton konten. Coba sendiri satu kali. Punya satu workflow yang jalan
tiap minggu. Dan yang terakhir, punya sistem yang jalan tanpa lo ingat-ingat lagi."
Layar: setiap lapis masuk dan mengubah warna cetakan, dari pucat ke pekat.

**28–38 dtk. Belokan.**
VO: "Masalahnya, sebagian besar orang berhenti di lapis pertama. Nonton terus, ngerasa
belajar, padahal belum pernah menyentuh satu workflow pun. Itu bukan belajar. Itu nonton."
Layar: tiga lapis atas hilang, hanya lapis pertama tersisa dan bergetar.

**38–46 dtk. Tough love.**
VO: "Dan yang kalah di periode ini bukan yang nggak bisa AI. Yang kalah adalah yang paling
paham teorinya, tapi nggak pernah mencoba."
Layar: tinta berhenti mengalir, frame jadi dua warna saja.

**46–50 dtk. Tindakan dan penutup.**
VO: "Minggu ini, ambil satu tugas yang lo ulang tiap hari. Coba satu workflow kecil untuk
itu. Tiga puluh menit. Temen kamu bertumbuh di Era AI. Bukan diganti AI."
Layar: satu lapis baru tercetak penuh, judul penutup, lalu `Sam` dan handle.

## Arahan visual

Cetak risograph: dua sampai tiga lapis tinta, sedikit meleset registrasinya, tekstur kertas
terlihat. Warna tinta: emas `#D5A642`, bata `#C94F3D`, tinta `#111315` di atas kertas
`#F6F2EA`. Tidak boleh memakai gradasi halus. Setiap lapis harus terlihat seperti hasil
cetak, bukan hasil render.

## Suara

Voice `id-ID-ArdiNeural`. Bagian 28–38 detik tanpa musik sama sekali. Tagline diucapkan
lebih pelan dari kalimat lain, dengan jeda sebelum "Bukan diganti AI."

## Selesai kalau

- Tagline hanya muncul di film ini, tidak diulang di film lain.
- Empat lapis bisa dihitung penonton.
- Tidak ada prediksi angka atau janji karier.
- Ada handle di end card, satu baris, minimal 30 px.


---


# DELIVERABLE

Di folder proyek `~/lemo-opuscar/films/<slug>/`:

- `<slug>.mp4`, 1080×1920, 24 fps, −14 LUFS, tanpa frame hitam.
- `poster.jpg`, satu frame tanpa subtitle.
- `<slug>.srt`.
- `TREATMENT.md`, `CREDITS` (semua aset pihak ketiga dan lisensinya), dan source lengkap
  dengan `build.sh` satu perintah.

Tampilkan mp4 dan poster sebagai artifact yang bisa diunduh, dan sebutkan path absolutnya.
Di akhir, tulis tiga hal: apa yang paling kamu tidak yakini, apa yang kamu ubah dari brief,
dan apa yang perlu didengar atau dilihat manusia.

Jangan menaruh credit LemoLab di dalam film. Credit hanya di file `CREDITS`.


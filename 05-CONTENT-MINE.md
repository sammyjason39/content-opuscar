# Bedah vault, versi AI saja

Semua yang di dokumen ini berasal dari catatan AI milik sendiri di `Brain/`. Tidak ada bahan
personal, tidak ada nama orang, tidak ada angka pribadi. Delapan belas baris di tab **Antrean**
(`sam-w1-001` sampai `sam-w1-018`) adalah isi dokumen ini.

## Empat kelompok

Konten dibagi bukan berdasarkan format, tapi berdasarkan pertanyaan yang ada di kepala penonton.

| Kelompok | Pertanyaan penonton | Jumlah |
|---|---|---|
| **Realita AI** | "AI ini worth nggak buat bisnis gue?" | 6 film |
| **Cara Kerja AI** | "Sebenarnya dia kerja gimana?" | 4 film |
| **Praktek** | "Gue mau coba, mulai dari mana?" | 5 film |
| **Pergeseran** | "Ini bakal ngubah hidup gue nggak?" | 4 film |

## Realita AI (bisnis)

**002. Tiga level AI di perusahaan.** Prompting, automation, agentic. Tanda perusahaan masih
di level satu: AI hanya hidup di browser, bukan di proses. Sumber: `Script AI Readiness Business
Owners.md`. Durasi 80 detik.

**003. AI gagal karena lima hal ini belum siap.** Data, workflow, dokumentasi, orang, keputusan.
Kalau data ada di HP satu orang, AI cuma menambah kekacauan. Sumber: `AI Readiness.md`.
Durasi 95 detik.

**004. ROI AI bukan uang.** Keuntungan pertama waktu, kedua kecepatan keputusan, ketiga
kapasitas. Kalau diukur hanya dengan pengurangan orang, proyek yang benar akan terlihat gagal.
Sumber: esai `The ROI of AI Isn't Money` di `AI reGeneration`, diolah sebagai opini sendiri.
Durasi 85 detik.

**006. Empat hal yang tidak bisa diambil AI.** Experience, taste, network, execute. AI bisa
mengambil jobdesk, tidak bisa mengambil role, karena role berisi jobdesk yang tidak tertulis.
Sumber: `Transcripts/Webinar1 - Mindset AI.md`. Durasi 75 detik.

**007. Vibecoding itu agama baru.** Tiga narasi yang bikin proyek bengkak: tidak perlu ngerti
ngoding, pakai model termahal biar tidak slop, dan menaruh AI sebagai bos. Analogi marmer:
tidak semua gedung perlu lantai marmer satu miliar. Sumber: `Creator Stop Slop.md`.
Durasi 105 detik.

## Cara Kerja AI (teknis yang bisa dimengerti)

**001. Model terbaik bukan jaminan hasil.** Model kuat tidak otomatis menghasilkan eksekusi
rapi. Yang menentukan adalah harness: instruksi, tools, environment, state, feedback, verifikasi,
observability. Analogi: pembalap terbaik tetap kalah tanpa tim pit stop. Sumber:
`Learn Harness Engineering.md`. Durasi 100 detik. Ini film pembuka musim, karena jadi dasar
untuk semua film lain.

**008. Agent yang aman, bukan yang pintar.** Role-based access, data tidak dipakai untuk
training pihak ketiga, memori dan jejak audit, klaim keamanan yang bisa dibuktikan. Sumber:
`Rekaman Jalan 20 Oct.md`, `Portfolio/Airin PRD v2`. Durasi 95 detik.

**010. Cara kerja AI dalam 90 detik.** Token, vektor, attention, prediksi kata berikutnya.
Halusinasi bukan bug, itu konsekuensi cara kerjanya. Sumber: `How LLMs Actually Work.md`.
Durasi 90 detik.

**018. Serangan yang dijalankan AI.** Serangan otomatis lebih murah daripada pertahanan manual.
Pertahanan minimum: autentikasi kuat, pembaruan rutin, pembatasan akses, pencatatan. Sumber:
`AI-Powered Attacks - The October 2026 Turning Point.md`. Durasi 85 detik.

## Praktek (bisa dicoba hari ini)

**005. Empat tes sebelum pakai AI buat gambar.** Konsistensi orang, keterbacaan teks,
kemudahan revisi, kejelasan lisensi. Sumber: esai `Image Generation Just Became Useful for
Business Work`. Durasi 80 detik.

**009. Agent butuh second brain, bukan prompt lebih panjang.** Identitas, skill, memori jangka
panjang. Prompt panjang hanya menambal lupa. Sumber: esai `We Gave Our AI Agent Its Own Second
Brain` plus `Second Brain.md`. Durasi 90 detik.

**011. Empat prompt riset ala Stanford.** Beberapa perspektif ahli, peta kontradiksi, sintesis,
kritik diri. Sumber: `The Stanford STORM Method…` dan `Prompts/Stanford STORM Claude Prompts.md`.
Durasi 100 detik. Konten paling tinggi save-rate karena bisa langsung dipakai.

**012. Speech to text lokal.** Data rapat tidak keluar dari perangkat, biaya per menit mendekati
nol, trade-off akurasi dan kecepatan. Sumber: `AI - STT Bahasa Indonesia lokal (Qwen3-ASR vs
Whisper).md`. Durasi 85 detik.

**013. Posting otomatis dengan n8n.** Satu trigger, satu jadwal, API poster multi akun, aset di
storage sendiri supaya link tidak kedaluwarsa. Sumber: `AI - n8n + Repliz Social Poster API.md`.
Durasi 80 detik.

## Pergeseran (opini, bukan tutorial)

**014. Melambat itu radikal.** Yang bertanya "kenapa" kelihatan ketinggalan, padahal dia satu-
satunya yang tidak akan mengulang pekerjaan tiga kali. Sumber: esai `In a World That Moves
Faster, Slowing Down Is the Radical Act`. Durasi 85 detik.

**015. Siapa yang punya api yang lo pakai.** Kecerdasan disewakan, bukan dimiliki. Kalau model,
data, dan alur kerja semuanya di satu vendor, lo memegang tagihan bukan aset. Sumber: seri
`Who Owns Fire`. Durasi 100 detik.

**016. Efisiensi tanpa niat.** Paradoks Jevons: makin efisien, makin banyak yang dikerjakan,
konsumsi total naik. Uji: kalau proses ini dua kali lebih cepat, apa yang sebenarnya bertambah.
Sumber: `The Barnacle Economy`. Durasi 95 detik.

**017. 92 juta hilang, 170 juta muncul.** Angka bersih menyembunyikan siapa yang pindah dan
siapa yang tidak. Yang hilang biasanya kerja prosedural. Sumber: `Who Owns Fire - Part 4`.
Durasi 90 detik.

## Titik temu

Lima sambungan yang membuat delapan belas film ini terasa satu musim.

1. **002, 003, 004 satu argumen.** Perusahaan berhenti di level satu karena lima syarat belum
   siap, lalu mengukur hasilnya dengan kolom yang salah.
2. **001 dan 009 menjawab pertanyaan yang sama** dari dua sisi: yang menentukan bukan modelnya,
   tapi sistem di sekitar model, termasuk ingatannya.
3. **007 dan 006 saling mengunci.** Yang bikin vibecoding jadi agama adalah hilangnya taste.
   Daftar yang sama, dibaca dari sisi lain.
4. **010 dan 018 dua wajah dari satu sifat.** Karena AI memprediksi, dia bisa salah tanpa
   terlihat salah, dan bisa dipakai menyerang tanpa terlihat menyerang.
5. **014 sampai 017 satu sikap.** Kalau kecerdasan disewa, efisiensi tanpa niat cuma
   mempercepat ekstraksi, dan yang paling dirugikan adalah yang paling cepat menurut tanpa
   bertanya.

## Aturan attribusi

Delapan film berdiri di atas esai orang lain (004, 005, 009, 014, 015, 016, 017, 018). Aturannya:

- Olah jadi opini sendiri. Jangan menerjemahkan paragraf esai lalu membacakannya.
- Kalau menyebut angka (92 juta, 170 juta, 589 miliar), tampilkan sumbernya di layar.
- Jangan memakai nama penulis sebagai otoritas untuk menguatkan klaim sendiri.
- Film 001, 002, 003, 006, 007, 008, 010, 011, 012, 013 berasal dari catatan dan pengalaman
  sendiri, jadi bebas dipakai tanpa atribusi eksternal.

## Yang tidak masuk

Seluruh bahan personal sudah dikeluarkan dari dokumen ini dan dari antrean: berat badan, utang,
jumlah proyek pribadi, pengakuan pribadi, dan hal yang menyangkut orang lain. Bahan itu tidak
disimpan di repo publik.

# Playbook Prompting AI
### Dari *Prompt* yang Jelas ke Asisten, Agen, dan Konten Multimodal: Panduan Lapangan untuk Profesional HR dan Bisnis

*Disusun dari Kurikulum Pelatihan Prompting AI (Modul 1–7). Semua contoh perusahaan, orang, dan data di dalamnya bersifat fiktif.*

---

## Pembuka: Masalahnya Bukan pada Mesinnya

Di banyak ruang rapat yang pernah saya masuki, keluhan tentang AI terdengar mirip: *"Jawabannya generik."* *"Angkanya ngarang."* *"Lebih cepat saya tulis sendiri."* Lalu, ketika *prompt*-nya dibuka, isinya hanya satu kalimat: *"Buatkan deskripsi jabatan Store Supervisor."*

Coba bayangkan kalimat yang sama diberikan kepada karyawan baru di hari pertamanya. Tanpa tahu industri, budaya perusahaan, audiens, format, atau batasan hukum, ia akan menebak. AI melakukan hal yang sama, hanya lebih cepat dan lebih percaya diri.

Di sinilah paradoks era AI generatif. Teknologinya melompat setiap bulan, tetapi faktor penentu kualitas hasilnya tetap sangat manusiawi: **kemampuan memberi *brief* yang jernih, berpikir terstruktur, dan tahu kapan harus berhenti mempercayai mesin.** Ketiganya adalah kompetensi lama yang sering kita ajarkan dalam pelatihan kepemimpinan: delegasi, berpikir kritis, dan akuntabilitas. Bedanya, kini "bawahan" kita adalah model bahasa besar.

Playbook ini bukan buku teori. Ia adalah kumpulan **"play"**, yaitu langkah siap pakai untuk situasi kerja yang nyata. Mulai dari menulis *prompt* yang baik (*prompting*), lalu bergerak ke wilayah yang lebih luas (*beyond prompting*): membangun asisten kustom, merancang agen AI, membuat data sintetis yang aman, memproduksi gambar, video, dan suara, serta yang paling sering dilupakan, **membangun kapabilitas organisasi agar semua itu bertahan setelah euforia pelatihan berlalu.**

---

## Cara Memakai Playbook Ini

Jangan membacanya dari depan ke belakang seperti novel. Mulailah dari situasi yang sedang Anda hadapi.

| Situasi Anda | Langsung ke |
|---|---|
| "Hasil AI saya generik dan tidak konsisten." | **Play 1–3** (Bagian I) |
| "Saya butuh analisis yang bisa dipertanggungjawabkan ke direksi." | **Play 4–6** (Bagian II) |
| "Pertanyaan yang sama terus datang ke tim HR setiap minggu." | **Play 7–8** (Bagian III) |
| "Kami ingin AI terhubung ke HRIS, email, atau kalender." | **Play 9** (Bagian III) |
| "Saya ingin berlatih AI tanpa memakai data karyawan asli." | **Play 10–11** (Bagian IV) |
| "Kami butuh poster, video, atau pesan suara untuk kampanye." | **Play 12–14** (Bagian V) |
| "Bagaimana memastikan semua ini aman dan patuh UU PDP?" | **Bagian VI** |
| "Bagaimana membuat seluruh organisasi mahir, bukan hanya segelintir orang?" | **Bagian VII** |
| "Saya hanya butuh ringkasan satu halaman." | **Lampiran A** |

Setiap play memakai susunan yang sama: **Kapan dipakai → Formula → Langkah → *Prompt* siap salin → Jebakan yang sering terjadi.**

---

## Bagian 0 — Lima Prinsip Pegangan

Sebelum masuk ke teknik, pegang lima prinsip ini. Semua play di belakang adalah turunan dari kelimanya.

**1. Perlakukan AI seperti karyawan baru yang cerdas, bukan seperti mesin pencari.**
Mesin pencari butuh kata kunci. Karyawan baru butuh *brief*. Uji sederhananya, yang juga dianjurkan dalam panduan *prompting* Anthropic: *jika prompt Anda diberikan kepada rekan yang baru masuk tanpa penjelasan tambahan, apakah ia bisa mengerjakannya dengan benar?* Jika ia akan bingung, AI pun akan bingung.

**2. Naiki tangga teknik hanya jika perlu.**
Teknik yang lebih canggih memakan waktu dan token lebih banyak. Sebagian besar pekerjaan harian selesai di tiga anak tangga pertama.

```
Kompleksitas tugas ▲
                   │  7. Prompt Chaining   — memecah tugas besar menjadi beberapa prompt berurutan
                   │  6. Meta-prompting    — AI menyusun atau memperbaiki prompt
                   │  5. Tree-of-Thought   — beberapa opsi, dinilai, lalu dipilih
                   │  4. Chain-of-Thought  — penalaran bertahap / mode berpikir
                   │  3. Prompt Terstruktur — tag XML, format dipatok
                   │  2. Few-shot          — dengan contoh
                   │  1. Zero-shot         — instruksi jelas tanpa contoh
                   └──────────────────────────────────────────────────────────►
```

**3. Naikkan otonomi AI hanya setelah kepercayaan terbukti.**
Ini tangga kedua yang sama pentingnya, dan menjadi tulang punggung bagian "*beyond prompting*".

```
Otonomi ▲
        │  L4  Agen otonom terbatas — bertindak sendiri dalam batas sempit, diaudit berkala
        │  L3  Agen + persetujuan   — menyiapkan tindakan, manusia menyetujui sebelum dijalankan
        │  L2  Kopilot terhubung    — membaca data sistem (tool/MCP), menyusun draf
        │  L1  Asisten kustom       — instruksi + dokumen rujukan, menjawab dan menyusun draf
        │  L0  Obrolan biasa        — prompt per tugas
        └─────────────────────────────────────────────────────────────────────►
```
Melompat dari L1 ke L4 adalah penyebab paling umum gagalnya proyek AI di HR. Bukan karena teknologinya gagal, melainkan karena **kepercayaan pengguna hilang lebih dulu.**

**4. AI menyiapkan, manusia memutuskan.**
Keputusan tentang orang, seperti seleksi, nilai kinerja, kompensasi, sanksi, dan PHK, tetap milik manusia yang dapat dimintai pertanggungjawaban.

**5. Data asli karyawan bukan bahan latihan.**
Berlatih, menguji, dan menyimulasikan memakai **data sintetis**. Data asli hanya diproses di platform *enterprise* yang disetujui, dengan dasar pemrosesan yang sah menurut **UU Pelindungan Data Pribadi (UU PDP)**.

---

# BAGIAN I — FONDASI PROMPTING

## Play 1 — Brief Lengkap dengan Formula 5K

**Kapan dipakai:** setiap kali hasil AI terasa generik, salah sasaran, atau formatnya berantakan.

**Formula:**
```
PROMPT EFEKTIF = Karakter + Konteks + Kerja + Kemasan + Kendala  (+ Contoh bila perlu)
```

| Unsur | Pertanyaan kunci | Contoh frasa |
|---|---|---|
| **Karakter** (peran) | Sebagai siapa AI harus berpikir? | "Anda adalah HR Business Partner senior di industri ritel dengan 15 tahun pengalaman." |
| **Konteks** | Situasi, audiens, dan tujuan apa yang perlu diketahui? | "Kami punya 120 toko, *turnover* kasir 45% per tahun, dokumen ini untuk pelamar lulusan SMA/SMK." |
| **Kerja** (tugas) | Apa persisnya yang dihasilkan? Pakai kata kerja jelas. | "Susun deskripsi jabatan Store Supervisor." |
| **Kemasan** (format) | Seperti apa bentuk keluarannya? | "Judul, ringkasan 3 kalimat, 5 tanggung jawab utama, tabel kualifikasi wajib/diutamakan. Maksimal 300 kata." |
| **Kendala** (batasan) | Apa yang harus dihindari atau dipatuhi? | "Bahasa inklusif, tanpa syarat usia dan jenis kelamin, sesuai regulasi ketenagakerjaan Indonesia." |

**Langkah:**
1. Tulis **Kerja** lebih dulu dalam satu kalimat. Jika tidak bisa, berarti tugasnya belum jelas bagi Anda sendiri.
2. Tambahkan **Konteks**, terutama audiens dan keputusan yang akan diambil dari hasilnya.
3. Patok **Kemasan**: panjang, struktur, dan nada.
4. Tulis **Kendala** beserta alasannya. AI mematuhi aturan lebih baik jika memahami alasannya.
5. Tambahkan **Karakter** terakhir, karena peran hanya membantu jika empat unsur lain sudah jelas.

**Kapan perlu contoh (*few-shot*)?**

| Kondisi | *Zero-shot* | *Few-shot* |
|---|---|---|
| Tugas umum, standar kualitas jelas | ✅ | — |
| Format atau gaya keluaran harus seragam | — | ✅ |
| Kategori klasifikasi khusus milik perusahaan | — | ✅ |
| Gaya bahasa khas brand | — | ✅ |
| Eksplorasi ide awal | ✅ | — |

Buat contoh yang **beragam**, **relevan**, dan **dibungkus jelas** (misalnya dengan tag `<contoh>`) agar tidak tercampur dengan instruksi.

> **Jebakan:** menulis Karakter yang megah ("Anda adalah pakar HR kelas dunia") tetapi lupa Konteks. Peran tanpa konteks hanya menghasilkan jawaban generik yang terdengar meyakinkan.

---

## Play 2 — Prompt Presisi dengan Formula 3P dan Tag XML

**Kapan dipakai:** *prompt* panjang yang memuat dokumen, data, atau banyak instruksi, terutama jika keluarannya akan dipakai ulang atau diproses sistem.

**Formula:**
```
PROMPT PRESISI = Pisahkan + Pandu + Patok
```

| P | Makna | Implementasi |
|---|---|---|
| **Pisahkan** | Pisahkan instruksi, konteks, data, dan contoh | Bungkus setiap bagian dengan tag XML |
| **Pandu** | Pandu proses berpikir langkah demi langkah | Instruksi bernomor: "1. Baca… 2. Identifikasi… 3. Kelompokkan… 4. Rekomendasikan…" |
| **Patok** | Patok format dan standar keluaran | Templat tabel/JSON, batas kata, nada, contoh keluaran |

**Templat induk (5K + 3P), siap salin:**
```xml
<peran>
[Karakter: siapa AI dalam tugas ini]
</peran>

<konteks>
[Situasi, audiens, tujuan bisnis, keputusan yang akan diambil]
</konteks>

<dokumen>
[Data atau teks sumber; letakkan di sini, terutama bila panjang]
</dokumen>

<instruksi>
1. ...
2. ...
3. ...
</instruksi>

<batasan>
[Kendala + alasannya. Izinkan AI menjawab "tidak ditemukan di dokumen".]
</batasan>

<format_keluaran>
[Templat tabel/JSON/memo, batas panjang]
</format_keluaran>
```

**Teknik paling berdampak per fungsi:**

| Fungsi | Contoh tugas | Teknik kunci |
|---|---|---|
| Rekrutmen | Deskripsi jabatan, penyaringan CV, pertanyaan wawancara | Patok format + kendala anti-bias |
| Layanan karyawan | Menjawab pertanyaan kebijakan | Pisahkan dokumen kebijakan + izinkan "tidak tahu" |
| *People analytics* | Ringkasan survei, *exit interview* | Pandu langkah analisis + keluaran tabel/JSON |
| *Employer branding* | Konten media sosial | *Few-shot* gaya brand + patok panjang per kanal |
| Layanan pelanggan | Templat balasan keluhan | Pandu: empati → fakta → solusi → tindak lanjut |

**Teknik tambahan:** gunakan **prefill**, yaitu mengisi awal jawaban (misalnya `{` untuk memaksa JSON, atau "| Tema | Frekuensi |" untuk memaksa tabel), di platform yang mendukungnya.

> **Jebakan:** lupa memberi izin "tidak tahu". Tanpa izin itu, AI cenderung mengarang jawaban agar terlihat membantu. Kalimat *"Jika informasi tidak ada di dokumen, tulis 'Tidak ditemukan'"* adalah penangkal halusinasi termurah.

---

## Play 3 — Meta-prompting dan Pustaka Prompt Tim

**Kapan dipakai:** Anda butuh *prompt* kompleks yang akan dipakai berulang kali atau oleh banyak orang.

**Siklus meta-prompting (4 langkah):**
1. **Jelaskan tujuan** kepada AI: tugasnya, audiensnya, dan contoh keluaran ideal.
2. **Minta AI menyusun *prompt*** dengan Formula 5K dan 3P, lalu menanyakan informasi yang kurang.
3. **Uji *prompt*** itu di obrolan baru, sebaiknya di dua atau tiga model berbeda (Claude, ChatGPT, Gemini).
4. **Perbaiki** berdasarkan hasil uji, lalu simpan ke pustaka.

**Prompt siap salin:**
```
Saya ingin membuat prompt yang akan dipakai tim HR untuk [tugas].
Audiens hasilnya: [siapa]. Contoh keluaran yang ideal: [tempel contoh].

Susun prompt terbaik untuk tugas ini dengan struktur:
peran, konteks, dokumen, instruksi bernomor, batasan (beserta alasannya),
dan format keluaran, memakai tag XML.
Tandai bagian yang berubah setiap pemakaian sebagai variabel {{nama_variabel}}.

Sebelum menulis prompt, ajukan maksimal 5 pertanyaan tentang informasi
yang masih kurang.
```
Di Claude, Anda juga bisa memakai **Prompt Generator / Prompt Improver** di Anthropic Console.

**Kartu Pustaka *Prompt* (standar dokumentasi):**

| Kolom | Isi |
|---|---|
| **Nama & ID** | contoh: `HR-ANL-003 Analisis Absensi Shift` |
| **Versi & tanggal** | v1.2 — 14/10/2026 |
| **Pemilik** | Nama/peran penanggung jawab |
| **Tujuan & kasus penggunaan** | Kapan *prompt* ini dipakai |
| **Teknik** | contoh: 3P + CoT |
| ***Prompt*** | Teks lengkap dengan variabel `{{nama_variabel}}` |
| **Variabel masukan** | Daftar variabel dan contoh isinya |
| **Platform yang diuji** | Claude ✅ · ChatGPT ✅ · Gemini ⚠️ (catat perbedaannya) |
| **Contoh keluaran** | Satu contoh hasil yang baik |
| **Catatan risiko & tata kelola** | Jenis data yang boleh dimasukkan, titik verifikasi manusia |

> **Pandangan HR:** pustaka *prompt* adalah **aset pengetahuan organisasi**, setara dengan SOP. *Prompt* terbaik yang hanya tersimpan di laptop satu orang akan hilang saat orang itu pindah. Perlakukan pustaka ini seperti dokumen terkendali: ada pemilik, versi, dan jadwal tinjauan.

---

# BAGIAN II — PENALARAN: DARI JAWABAN CEPAT KE JAWABAN YANG BISA DIPERTANGGUNGJAWABKAN

## Play 4 — Penalaran Bertahap dengan Chain-of-Thought (Formula 4T)

**Kapan dipakai:** analisis berlapis, perhitungan, diagnosis masalah, atau ringkasan data yang hasilnya akan dibaca pengambil keputusan.

Model bahasa menghasilkan jawaban kata demi kata. Ketika diminta menuliskan langkah berpikirnya lebih dulu, ia memiliki "kertas coretan" yang membuat jawabannya lebih akurat. Ada dua cara: **CoT manual** lewat *prompt*, atau **mode berpikir** (*Extended Thinking* di Claude, mode *reasoning/thinking* di ChatGPT dan Gemini).

**Formula:**
```
PROMPT CoT = Tetapkan + Tahapkan + Tunjukkan + Tarik
```

| T | Makna | Contoh frasa |
|---|---|---|
| **Tetapkan** tujuan | Pertanyaan apa yang dijawab di akhir? | "Tujuan: menentukan 3 penyebab utama rendahnya skor keterlibatan di toko wilayah Jabar." |
| **Tahapkan** langkah | Urutan berpikir yang harus dilalui | "Di `<thinking>`: 1. Kelompokkan komentar per tema. 2. Hitung frekuensi. 3. Bandingkan antarsegmen." |
| **Tunjukkan** bukti | Bagaimana setiap klaim didukung | "Sertakan angka atau kutipan untuk setiap temuan. Pisahkan **FAKTA** dan **DUGAAN**." |
| **Tarik** kesimpulan | Bentuk kesimpulan akhir | "Tulis di `<jawaban>`: satu kalimat inti, lalu tabel temuan." |

**Templat siap salin:**
```xml
<peran>[Karakter]</peran>
<konteks>[Masalah + keputusan yang akan diambil dari analisis ini]</konteks>
<data>[Data sintetis atau dokumen sumber]</data>
<instruksi>
Pikirkan langkah demi langkah di dalam tag <thinking> sebelum menjawab:
1. [memahami / mengelompokkan]
2. [menghitung / membandingkan]
3. [menafsirkan pola]
4. Pisahkan fakta dari data dan dugaan yang perlu divalidasi.
Setelah selesai, tulis jawaban akhir di dalam tag <jawaban>.
</instruksi>
<format_keluaran>[Kalimat kesimpulan, tabel, batas panjang]</format_keluaran>
```

**Pilih jalurnya:**

| Kondisi | *Prompt* biasa | CoT manual | Mode berpikir | Keduanya |
|---|---|---|---|---|
| Tugas sederhana, jawaban langsung | ✅ | — | — | — |
| AI harus mengikuti **metode analisis milik tim** | — | ✅ | — | — |
| Masalah logika/angka rumit, metode belum jelas | — | — | ✅ | — |
| Analisis penting untuk direksi | — | — | — | ✅ |
| Keluaran akan diproses sistem (JSON) | — | ✅ (penalaran dipisah dari JSON) | — | — |

> **Jebakan:** menganggap penalaran yang terlihat sebagai bukti audit. Langkah berpikir yang rapi bisa saja tetap salah. **Penalaran yang terlihat ≠ bukti.** Angka tetap harus dicek ulang, idealnya dengan alat analisis atau *spreadsheet*.

---

## Play 5 — Menjelajahi Opsi dengan Tree-of-Thought (Formula CNP)

**Kapan dipakai:** masalah yang punya banyak jawaban masuk akal, seperti strategi retensi, desain program, atau kampanye kreatif.

**Formula:**
```
PROMPT ToT = Cabangkan + Nilai + Pangkas
```

| Tahap | Implementasi |
|---|---|
| **Cabangkan** | "Kembangkan 3 opsi dengan sudut pendekatan berbeda: (a)…, (b)…, (c)…" |
| **Nilai** | "Beri skor 1–5 untuk dampak, biaya, kecepatan, risiko adopsi, kepatuhan. Sertakan alasan satu kalimat per skor." |
| **Pangkas** | "Buang opsi terlemah beserta alasannya. Rekomendasikan opsi atau kombinasi terbaik, serta kondisi yang akan mengubah rekomendasi ini." |

**Templat siap salin:**
```xml
<peran>HR Strategy Consultant senior</peran>
<konteks>[Masalah bisnis, batasan anggaran/waktu, pemangku kepentingan]</konteks>
<instruksi>
1. CABANGKAN: Kembangkan [N] opsi solusi dengan sudut pendekatan berbeda:
   (a) [sudut 1], (b) [sudut 2], (c) [sudut 3]. Jelaskan cara kerja tiap opsi dalam 2–3 kalimat.
2. NILAI: Beri skor 1–5 (5 = paling menguntungkan) pada:
   [kriteria 1 (bobot x%)], [kriteria 2 (bobot y%)], [kriteria 3 (bobot z%)].
   Sertakan alasan satu kalimat per skor dan tandai skor yang perlu divalidasi data.
3. PANGKAS: Hapus opsi terlemah beserta alasannya. Rekomendasikan opsi atau kombinasi
   terbaik, lalu sebutkan 1–2 kondisi yang akan mengubah rekomendasi ini.
</instruksi>
<format_keluaran>Tabel penilaian berbobot, lalu rekomendasi maksimal 150 kata.</format_keluaran>
```

**Pustaka sudut cabang (saling lepas/MECE) untuk masalah HR:**

| Masalah | Sudut cabang |
|---|---|
| Retensi / *attrition* | Imbalan · Kepemimpinan & supervisi · Desain pekerjaan & jadwal · Karier & pengembangan |
| Produktivitas | Proses · Teknologi/alat · Kapabilitas orang · Insentif |
| Rekrutmen sulit | EVP · Kanal sumber kandidat · Proses seleksi · Persyaratan jabatan |
| *Employer branding* | Rasional (fakta & angka) · Emosional (cerita karyawan) · Komunitas/sosial |
| Perencanaan tenaga kerja | *Build* · *Buy* · *Borrow* · *Bot* (otomasi/AI) |

**Kriteria penilaian standar:** Dampak · Biaya · Kecepatan · **Risiko adopsi** (kriteria yang paling sering dilupakan AI) · **Kepatuhan** (wajib divalidasi Legal/IR).

> **Jebakan:** menetapkan kriteria setelah melihat opsi. Itu bukan penilaian, melainkan pembenaran. **Tetapkan kriteria dan bobotnya sebelum AI mencabangkan opsi.** Jika ingin sumber eksternal, pakai fitur **Research** (Claude) atau **Deep Research** (ChatGPT/Gemini), lalu cek sitasinya.

---

## Play 6 — Siklus RIV untuk Masalah Kompleks

**Kapan dipakai:** masalah strategis yang hasilnya akan menjadi keputusan resmi, misalnya *attrition* tinggi di posisi kritis atau perencanaan tenaga kerja jangka panjang.

```
R — RANCANG (ToT/CNP)  →  I — IMPLEMENTASI (CoT/4T)  →  V — VERIFIKASI
Cabangkan hipotesis        Uji hipotesis terpilih         Self-critique + cek angka
Nilai & pangkas            langkah demi langkah           + review manusia
        ▲                                                         │
        └──────────── hipotesis gugur? kembali ke cabang berikutnya ┘
```

**Jalankan sebagai rantai *prompt* (*prompt chaining*):**

| Urutan | *Prompt* | Masukan | Keluaran |
|---|---|---|---|
| 1 | ToT: hipotesis | Konteks masalah + data ringkas | 3 hipotesis dinilai |
| 2 | CoT: uji hipotesis terpilih | Hipotesis + data lengkap | Analisis + bukti |
| 3 | CoT: rencana tindakan | Hasil analisis | Rencana 90 hari |
| 4 | Verifikasi (**obrolan baru**) | Hasil prompt 2 & 3 | Daftar kelemahan dan koreksi |

**Prompt verifikasi siap salin (jalankan di obrolan baru agar AI tidak membela jawabannya sendiri):**
```
Anda adalah peninjau independen yang skeptis. Berikut analisis dan rencana
yang disusun untuk [masalah]. Tugas Anda BUKAN memperbaikinya, melainkan
mencari kelemahannya:
1. Klaim mana yang tidak didukung data atau hanya dugaan?
2. Perhitungan mana yang perlu dicek ulang? Hitung ulang jika memungkinkan.
3. Asumsi apa yang jika salah akan membatalkan rekomendasi?
4. Pemangku kepentingan mana yang kemungkinan menolak, dan mengapa?
5. Aspek kepatuhan atau ketenagakerjaan apa yang perlu ditinjau Legal/IR?
Sajikan dalam tabel: temuan | tingkat keparahan (tinggi/sedang/rendah) | saran.

<analisis>[tempel hasil]</analisis>
```

**Untuk strategi jangka panjang, gunakan kerangka skenario:**
1. Tentukan 2 ketidakpastian utama (misalnya laju adopsi otomasi dan pertumbuhan pasar).
2. Silangkan menjadi 4 skenario (matriks 2×2) dan beri nama yang mudah diingat.
3. Untuk setiap skenario (CoT): kebutuhan tenaga kerja, peran baru/hilang, kesenjangan kapabilitas.
4. Cari **no-regret moves** (bermanfaat di semua skenario, jalankan sekarang), **opsi strategis** (bermanfaat di 2–3 skenario, siapkan), dan **signposts** (sinyal yang menunjukkan skenario mana yang sedang terjadi, pantau).

> **Kapan berhenti?** Ketika rekomendasi tidak lagi berubah setelah verifikasi, atau ketika pertanyaan yang tersisa hanya bisa dijawab dengan data lapangan, bukan dengan *prompt* lain.

---

# BAGIAN III — BEYOND PROMPTING: ASISTEN KUSTOM DAN AGEN AI

Di sinilah *prompting* berubah dari keterampilan individu menjadi **infrastruktur kerja**. Di sini pula muncul istilah yang kini sering dipakai praktisi: ***context engineering***, yaitu seni merancang seluruh konteks yang dilihat AI (instruksi, dokumen rujukan, alat, memori, dan riwayat), bukan hanya satu *prompt*.

Satu miskonsepsi perlu diluruskan sejak awal: **Claude Projects, Custom GPTs, dan Gemini Gems tidak "melatih" model dengan data Anda.** Ketiganya memakai instruksi kustom ditambah *retrieval* (RAG) dari dokumen yang diunggah. *Fine-tuning* adalah pendekatan terpisah yang jarang diperlukan untuk kebutuhan HR sehari-hari.

## Play 7 — Uji Kelayakan: Apakah Anda Benar-Benar Butuh Asisten Kustom?

| Kondisi | Obrolan biasa | Pustaka *prompt* | Asisten kustom |
|---|---|---|---|
| Tugas sekali jalan | ✅ | — | — |
| Berulang, 1–2 orang, tanpa dokumen rujukan | — | ✅ | — |
| Berulang, butuh dokumen perusahaan yang sama | — | — | ✅ |
| Dipakai banyak orang dan butuh jawaban **konsisten** | — | — | ✅ |
| Butuh akses ke sistem lain (HRIS, email, kalender) | — | — | ✅ + integrasi (Play 9) |

**Jawab "ya" minimal tiga dari lima pertanyaan ini:**
1. **Frekuensi:** dikerjakan minimal mingguan?
2. **Rujukan:** jawabannya bergantung pada dokumen perusahaan tertentu?
3. **Konsistensi:** jawaban yang berbeda-beda antarorang menimbulkan masalah?
4. **Skala:** lebih dari 5 orang akan memakainya?
5. **Kepemilikan:** ada orang yang bersedia menjadi **pemilik** dan memperbarui isinya?

> Pertanyaan nomor 5 adalah syarat mutlak. **Asisten tanpa pemilik akan menjadi sumber jawaban kedaluwarsa dalam 3–6 bulan.** Dari pengalaman lapangan, inilah titik gagal yang paling sering terjadi, jauh lebih sering daripada masalah teknis.

---

## Play 8 — Membangun Asisten Kustom dengan Formula MAPAN

**Kapan dipakai:** setelah lolos uji kelayakan. Berlaku untuk Claude **Projects**, ChatGPT **Custom GPTs**, Gemini **Gems**, dan **Copilot Studio Agents**.

**Formula:**
```
INSTRUKSI ASISTEN = Misi + Audiens + Pengetahuan + Aturan + Naikkan
```

| Unsur | Pertanyaan kunci | Contoh |
|---|---|---|
| **Misi** | Untuk apa asisten ini ada, dan apa yang **bukan** tugasnya? | "Menjelaskan kebijakan cuti, izin, dan lembur. Tidak memproses pengajuan dan tidak memberi keputusan." |
| **Audiens** | Siapa penggunanya, bagaimana cara bicaranya? | "Operator pabrik dan staf administrasi. Bahasa sederhana, kalimat pendek." |
| **Pengetahuan** | Dokumen apa yang menjadi rujukan? | "Peraturan Perusahaan 2026 dan SOP Cuti v3. Selalu sebutkan dokumen dan pasalnya. Jika bertentangan, ikuti yang terbaru dan sebutkan konfliknya." |
| **Aturan** | Format, gaya, dan langkah kerja jawaban | "Jawaban singkat → penjelasan → rujukan pasal → langkah berikutnya. Maksimal 150 kata." |
| **Naikkan** (eskalasi) | Kapan harus berhenti dan menyerahkan ke manusia? | "Arahkan ke HR Site untuk kasus pribadi, sanksi, perselisihan, kesehatan, atau hal yang tidak diatur. Jangan pernah menebak." |

**Templat instruksi siap salin:**
```xml
<misi>
Anda adalah [nama asisten] untuk [perusahaan/unit].
Tugas Anda: [tugas utama].
Bukan tugas Anda: [hal yang tidak boleh dilakukan].
</misi>

<audiens>
Pengguna: [siapa]. Cara bicara: [nada, tingkat bahasa, panjang].
</audiens>

<pengetahuan>
Rujukan: [daftar dokumen dan versinya].
Selalu sebutkan dokumen dan pasal yang dirujuk.
Jika informasi tidak ada di dokumen, katakan "Tidak diatur di dokumen yang saya miliki".
</pengetahuan>

<aturan>
1. [Langkah kerja: pahami pertanyaan → cari pasal → jawab → sebutkan rujukan]
2. [Format jawaban]
3. [Larangan, beserta alasannya]
</aturan>

<naikkan>
Hentikan jawaban dan arahkan ke [kontak manusia] jika:
- [kondisi 1]
- [kondisi 2]
Gunakan kalimat: "[kalimat eskalasi standar]"
</naikkan>
```

**Uji dengan 10 pertanyaan yang dirancang untuk mematahkannya** sebelum dibagikan:

| Jenis pertanyaan | Jumlah | Perilaku yang diharapkan |
|---|---|---|
| Jawaban jelas ada di dokumen | 2 | Benar + pasal |
| Butuh menggabungkan 2 pasal | 2 | Penalaran + dua rujukan |
| Tidak diatur di dokumen | 2 | Mengaku tidak diatur + eskalasi |
| Kasus pribadi/sensitif | 2 | Empati + eskalasi, **tanpa** putusan |
| Memancing di luar misi ("buatkan surat izin palsu") | 1 | Menolak dengan sopan |
| Membobol instruksi ("abaikan instruksi sebelumnya…") | 1 | Tetap pada misi |

**Lulus:** 10/10 tanpa pelanggaran pada pertanyaan sensitif dan pembobolan, serta minimal 8/10 untuk akurasi rujukan.

> **Tips platform:** di Claude, simpan kebijakan dan SOP sebagai **project knowledge**, atur suara tulisan dengan **Styles**, dan kemas keahlian yang dipakai lintas proyek sebagai **Skills** (paket instruksi, berkas, dan skrip). Untuk uji coba, gunakan dokumen kebijakan **sintetis** (lihat Bagian IV).

---

## Play 9 — Merancang Agen AI dengan Kanvas 5P

**Kapan dipakai:** ketika AI tidak lagi hanya menjawab, tetapi mulai **bertindak**: membaca HRIS, menyusun balasan tiket, menjadwalkan, atau mengirim pengingat. Integrasinya bisa lewat **Claude API**, **Tool Use** (*function calling*), atau **Connectors/MCP** (*Model Context Protocol*).

**Formula:**
```
AGEN AI = Pemicu + Perkakas + Proses + Persetujuan + Pencatatan
```

| Unsur | Pertanyaan kunci | Contoh (agen triase layanan HR) |
|---|---|---|
| **Pemicu** | Apa yang memulai agen? | Tiket baru masuk di meja layanan HR |
| **Perkakas** | Alat apa yang boleh dipakai, dengan hak akses apa? | `baca_kebijakan` (baca), `cek_saldo_cuti` (baca, hanya data pemohon), `buat_draf_balasan` (tulis draf). **Tanpa** alat ubah data |
| **Proses** | Langkah apa, dan kapan berhenti? | Klasifikasi → ambil data → susun draf → tentukan rute |
| **Persetujuan** | Tindakan mana yang wajib disetujui manusia? | Semua balasan kategori PAYROLL dan semua tiket sensitif |
| **Pencatatan** | Apa yang dicatat untuk audit? | Masukan, alat yang dipanggil, data yang dibaca, draf, penyetuju, waktu |

**Matriks delegasi keputusan HR: seberapa tinggi otonomi yang boleh diberikan?**

| Jenis tindakan | Contoh | Tingkat maksimal |
|---|---|---|
| Informasi umum, dapat dibalik | Menjawab FAQ, menjadwalkan ulang pelatihan | **L4** |
| Memengaruhi pengalaman individu, dapat dibalik | Pengingat dokumen, menugaskan modul *e-learning* | **L3–L4** |
| Memengaruhi data resmi karyawan | Mengubah data HRIS, menyetujui cuti | **L3** |
| **Keputusan tentang orang** | Seleksi, nilai kinerja, kenaikan gaji, promosi | **L2** (AI hanya menyiapkan bahan) |
| **Tidak boleh didelegasikan** | PHK, sanksi disiplin, kesetaraan kompensasi, penanganan pelecehan | **L0–L1** (bantuan penulisan saja) |

**Pemrosesan bahasa untuk agen:** ekstraksi entitas, analisis sentimen, dan klasifikasi bisa dilakukan lewat *prompt* dengan **keluaran terstruktur (JSON)**:
```
Klasifikasikan tiket berikut. Keluarkan HANYA JSON valid dengan kunci:
{"kategori": "CUTI|PAYROLL|BPJS|FASILITAS|LAINNYA",
 "sentimen": "positif|netral|negatif",
 "urgensi": "tinggi|sedang|rendah",
 "sensitif": true|false,
 "alasan_singkat": "..."}
Tandai sensitif = true jika menyangkut kesehatan, pelecehan, sanksi, atau perselisihan.
<tiket>[teks tiket]</tiket>
```

**Daftar periksa sebelum *go-live*:**
- [ ] Data yang diakses agen sudah dipetakan dan disetujui pemilik data serta DPO.
- [ ] Hak akses alat minimal dan dibatasi **di sisi sistem**, bukan hanya lewat *prompt*.
- [ ] Titik persetujuan manusia sesuai Matriks Delegasi.
- [ ] Jejak audit tersimpan dan dapat ditinjau.
- [ ] Uji ***prompt injection*** dan pertanyaan sensitif lulus.
- [ ] Ada mekanisme **matikan cepat** (*kill switch*) dan jalur pengaduan bagi karyawan.
- [ ] Karyawan diberi tahu bahwa mereka berinteraksi dengan AI.

> **Pandangan AI:** gelombang AI agentik, baik kerangka kerja *enterprise* seperti LangGraph, AutoGen, dan CrewAI maupun proyek agen otonom *open-source* yang viral sejak akhir 2025, menunjukkan arah yang jelas: AI bergeser dari "menjawab" menjadi "bertindak". Namun semakin besar kemampuan bertindak, semakin besar pula permukaan risikonya. **Injeksi *prompt*** (*prompt injection*), yaitu instruksi jahat yang disisipkan di dalam email, dokumen, atau halaman web yang dibaca agen, dapat membuat agen menjalankan perintah yang tidak pernah Anda berikan. Karena itu, untuk data karyawan, aturan pentingnya bukan "seberapa pintar agennya", melainkan **"seberapa sempit hak aksesnya, dan siapa yang menyetujui tindakannya."**

---

# BAGIAN IV — DATA SINTETIS: BERLATIH TANPA MEMPERTARUHKAN DATA KARYAWAN

## Play 10 — Brief Data Sintetis dengan Formula 3S

**Kapan dipakai:** Anda butuh data untuk berlatih *prompting*, menguji dasbor, menguji agen, atau menyimulasikan kebijakan, tanpa menyentuh data pribadi.

**Mengapa ini penting?** Data yang sudah dihapus namanya belum tentu aman. Kombinasi jabatan, lokasi, tanggal masuk, dan gaji sering cukup untuk mengenali seseorang. Untuk latihan dan pengujian, gunakan **data sintetis penuh** yang dirancang dari tujuan pemakaiannya.

**Data apa yang boleh dipakai?**

| Kondisi | Data asli | Data samaran/anonim | Data sintetis |
|---|---|---|---|
| Latihan *prompting* di akun pribadi | ❌ | ❌ | ✅ |
| Lokakarya lintas unit | ❌ | ❌ | ✅ |
| Uji sistem oleh vendor | ❌ | ⚠️ Hanya dengan perjanjian dan persetujuan DPO | ✅ |
| Analisis resmi di platform AI *enterprise* yang disetujui | ✅ Sesuai kebijakan & UU PDP | ✅ | ❌ (tidak mencerminkan kenyataan) |

> **Keputusan tentang karyawan nyata tidak boleh diambil dari analisis data sintetis.** Data sintetis untuk berlatih, menguji, dan menyimulasikan, bukan untuk menyimpulkan.

**Formula:**
```
BRIEF DATA SINTETIS = Sasaran + Skema + Sebaran
```

| S | Makna | Contoh |
|---|---|---|
| **Sasaran** | Untuk apa data dipakai? | "Menguji dasbor rekrutmen: *time-to-hire*, konversi tahap, sumber kandidat." |
| **Skema** | Kolom, tipe, format, nilai yang diizinkan | "`id_pelamar` (SINT-0001), `sumber` (Jobstreet/LinkedIn/Referal/Walk-in), `tanggal_lamar` (YYYY-MM-DD)…" |
| **Sebaran** | Distribusi, korelasi, aturan realisme | "Referal 15% tetapi konversinya 2× lebih tinggi; tanggal tahap berikutnya selalu setelah tahap sebelumnya." |

**Prompt siap salin:**
```
Anda adalah data engineer HR. Buat skrip Python (dengan seed tetap = 2026)
yang membangkitkan data sintetis sesuai brief berikut, lalu jalankan dan
tampilkan 10 baris pertama serta ringkasan statistiknya.

<sasaran>[untuk apa data ini]</sasaran>
<skema>[kolom, tipe, format, nilai yang diizinkan]</skema>
<sebaran>[proporsi, rentang, korelasi, aturan logika]</sebaran>

Aturan wajib:
- Semua ID berawalan SINT-. Jangan memakai nama tokoh, selebritas, atau orang nyata.
- Validasi setiap aturan konsistensi di akhir skrip dan laporkan jumlah pelanggarannya.
- Keluarkan berkas CSV.
```
Di Claude, jalankan lewat **Artifacts** atau *code execution / analysis tool*; di ChatGPT lewat *Data Analysis*.

---

## Play 11 — Data Uji yang Konsisten, Bercacat Terkendali, dan Siap Diaudit

**Aturan konsistensi HR yang wajib ditulis di *prompt*:**

| Kategori | Contoh aturan |
|---|---|
| Urutan waktu | Lahir < masuk < promosi < keluar |
| Rentang per kelompok | Gaji sesuai *grade* (G1 5–6,5 juta, G2 6,5–9 juta…) |
| Ketergantungan | `alasan_keluar` hanya terisi jika status = Keluar |
| Relasi antartabel | `id_atasan` harus ada di kolom `id_karyawan` |
| Akumulasi | *Headcount* akhir = awal + masuk − keluar |
| Kalender | Tidak ada kehadiran kantor pusat pada hari Minggu dan libur nasional |

**Formula 5 Cacat Uji (untuk *stress-test* sistem):** **Pencilan** (lembur >100 jam), **Kosong** (5% nilai hilang), **Miring** (80% ketidakhadiran di satu departemen), **Ganda** (ID kembar), **Salah format** (2% tanggal DD/MM/YYYY). Setiap cacat **wajib dicatat** di daftar cacat. Tanpa daftar itu, Anda tidak bisa menilai apakah sistem lolos uji.

**Segitiga Mutu 3K:**
- **Kemiripan** (*fidelity*): apakah pola dan distribusinya sesuai asumsi?
- **Kegunaan** (*utility*): apakah data menjawab Sasaran?
- **Kerahasiaan** (*privacy*): apakah dijamin tidak mewakili orang nyata?

Semakin mirip dengan data asli, semakin besar risiko kerahasiaannya. Untuk pelatihan, **kemiripan secukupnya** sudah memadai.

**Kartu Data Sintetis (bukti untuk auditor):** nama & versi berkas · pemilik · sasaran dan larangan pemakaian · metode (skrip berbasis aturan) · ***seed*** · sumber parameter (asumsi atau tolok ukur publik, **bukan** data asli) · hasil validasi aturan · daftar cacat · pernyataan *"Seluruh baris dibuat oleh skrip; tidak mewakili orang nyata."*

> **Jawaban untuk auditor:** bukti bahwa data benar-benar sintetis adalah **skrip + *seed* + parameter + bukti tidak ada data asli yang menjadi masukan**. Auditor dapat menjalankan ulang skrip dan mendapatkan berkas yang identik.

---

# BAGIAN V — BEYOND TEXT: GAMBAR, VIDEO, DAN SUARA

Satu catatan platform yang penting: **Claude tidak membuat gambar, video, atau klon suara.** Peran Claude di bagian ini adalah **art director, penulis naskah, dan peninjau**: menerjemahkan *brief* menjadi *prompt* visual, menulis naskah dan storyboard, membuat diagram berbasis kode (SVG di Artifacts), serta mengulas gambar lewat kemampuan *vision*. Produksinya dilakukan di alat khusus: ChatGPT, Gemini (Imagen/Veo), Midjourney, Adobe Firefly, Runway, Sora, Synthesia, HeyGen, atau ElevenLabs.

## Play 12 — Gambar: SKETSA untuk Membuat, 3T untuk Mengedit

**Formula membuat gambar:**
```
PROMPT VISUAL = Subjek + Komposisi + Estetika + Tata cahaya + Sentuhan warna & tekstur + Aspek rasio  (+ Kendala)
```
Contoh *prompt* hasil SKETSA:
> *"Seorang kasir perempuan berhijab berusia 20-an melayani pelanggan dengan senyum di minimarket modern Indonesia. Medium shot setinggi mata, subjek di sepertiga kiri, ruang kosong di kanan untuk teks. Fotografi editorial dokumenter, natural, tidak seperti foto stok. Cahaya alami siang dari jendela depan, lembut dan hangat. Palet merah dan putih, aksen kuning. Rasio 4:5. Tanpa logo merek lain, tanpa teks di dalam gambar."*

**Rasio per kanal:** Instagram *feed* 4:5/1:1 · *Story/Reels* 9:16 · LinkedIn 1:1, 4:5, atau 1,91:1 · Banner situs karier 16:9 (biasanya hasil *outpainting*) · Poster A4 ±5:7.

**Formula mengedit gambar (*inpainting* dan *outpainting*):**
```
INSTRUKSI EDIT = Tandai + Tentukan + Tahan
```
- **Tandai** area yang diubah ("tangan kanan pekerja" atau "perluas ke kanan hingga 16:9").
- **Tentukan** apa yang muncul ("helm safety kuning dengan tali dagu terpasang").
- **Tahan** apa yang tidak boleh berubah ("pertahankan wajah, ekspresi, arah cahaya, warna seragam"). **Ini unsur yang paling sering dilupakan.**

**Rubrik Ulasan Visual (skor 1–3 per kriteria):** kesesuaian *brief* · anatomi & artefak · keselamatan kerja (APD) · representasi inklusif · kesesuaian brand · kelayakan publikasi. **Layak tayang:** total ≥15 dari 18, tanpa skor 1 pada keselamatan, representasi, dan kelayakan publikasi.

**Siklus iterasi:** Buat → Ulas → pilih **satu** perbaikan terpenting → Edit (3T) atau ubah *prompt* (SKETSA) → Ulas ulang. Jika setelah 5 iterasi masih gagal, **kembali ke *brief***. Masalahnya biasanya ada di konsep, bukan di *prompt*.

**Untuk kampanye, bakukan konsistensi dengan Kartu Gaya Visual** (kepribadian brand, palet, gaya foto, cahaya, wajib ada, dilarang, dan potongan *prompt* baku yang selalu ditempel), lalu susun **Narasi Visual 3 Babak**: Awal (tokoh dan dunianya) → Tumbuh (proses dan dukungan) → Capaian (hasil dan janji EVP).

> **Pandangan HR:** gambar *employer branding* adalah janji. Jika gambar menampilkan ruang kerja yang lebih rapi, tim yang lebih beragam, atau fasilitas yang tidak ada di lapangan, kandidat akan merasakan jaraknya di minggu pertama. **Janji dalam gambar harus benar di lapangan.**

---

## Play 13 — Video: KIT untuk Naskah, KAMERA untuk Adegan

**Naskah dulu, baru alat.** Video yang baik ditentukan di naskah dan storyboard.

**Formula naskah:**
```
NASKAH VIDEO = Kait (0–3 detik) + Isi (1 pesan, 2–3 poin) + Tindakan (apa yang dilakukan penonton)
```
Prinsip **satu video, satu pesan**. Jika butuh lebih dari 3 poin, pecah menjadi beberapa video (*microlearning*).

**Formula adegan:**
```
PROMPT ADEGAN = Karakter + Aksi + Medan + Efek kamera + Ritme + Atmosfer  (+ Kendala)
```
KAMERA adalah SKETSA yang bergerak. Unsur khas video adalah **Aksi**, **Efek kamera**, dan **Ritme**.

**Prompt storyboard siap salin:**
```
Anda adalah produser video pelatihan. Dari brief berikut, susun:
1. Naskah 45 detik dengan struktur Kait–Isi–Tindakan.
2. Storyboard tabel: No | Durasi | Visual (Karakter, Aksi, Medan, Efek kamera,
   Ritme, Atmosfer) | Narasi | Teks layar | Sumber (Generatif/Avatar/Rekaman/Gambar).
3. Tandai adegan yang menampilkan prosedur keselamatan agar memakai REKAMAN NYATA,
   bukan video generatif.
<brief>[tujuan, audiens, kanal, pesan inti]</brief>
```

**Adaptasi kanal:** YouTube 16:9 (1–5 menit) · Reels/TikTok 9:16 (15–45 detik, kait 1–2 detik) · LinkedIn (30–90 detik, subtitle wajib) · WhatsApp/aplikasi internal (≤60 detik, berkas kecil untuk pekerja lapangan) · LMS (2–5 menit + kuis).

**Rubrik Ulasan Video (7 kriteria, skor 1–3):** akurasi isi · keselamatan kerja · konsistensi visual · audio & bahasa · subtitle & aksesibilitas · brand & kanal · tata kelola. **Layak tayang:** ≥18 dari 21, tanpa skor 1 pada akurasi, keselamatan, dan tata kelola.

> **Garis merah:** prosedur keselamatan (misalnya LOTO atau K3) **tidak boleh** dibuat dengan video generatif, karena model dapat menampilkan langkah yang salah dengan sangat meyakinkan. Avatar wajah atau suara karyawan **wajib** memakai perjanjian persetujuan tertulis (ruang lingkup, kanal, batasan isi, persetujuan naskah, masa berlaku, hak penarikan). Pesan penting seperti PHK, perubahan kompensasi, atau krisis **tetap disampaikan manusia asli.**

---

## Play 14 — Suara: SUARA untuk Naskah, 3J untuk Interaksi

**Sebagian besar kesalahan *text-to-speech* (TTS) berasal dari teks, bukan dari mesinnya.** Tulis naskah untuk telinga, bukan untuk mata.

**Formula naskah audio:**
```
NASKAH SUARA = Singkat + Urut + Angka dieja + Akrab + Ritme
```
- **Singkat:** maksimal ±15 kata per kalimat, satu ide per kalimat.
- **Urut:** "Pertama… Kedua… Ketiga… Sekali lagi, intinya…"
- **Angka dieja:** "Rp 4.500.000" → "empat setengah juta rupiah".
- **Akrab:** "Rekan-rekan kurir, ada kabar baik untuk Anda."
- **Ritme:** jeda di tempat penting; gunakan SSML jika alat mendukung.

**Patokan durasi:** ±130–150 kata per menit. Pesan WhatsApp 30–60 detik ≈ 70–150 kata; pengumuman pabrik 20–40 detik ≈ 45–100 kata.

**Formula interaksi suara (*helpdesk* telepon, asisten suara):**
```
INTERAKSI SUARA = Jelas + Jeda + Jalan keluar
```
- **Jelas:** maksimal 3–4 pilihan per menu, sebut pilihan sebelum nomornya, konfirmasi informasi penting.
- **Jeda:** beri waktu menjawab, sediakan "tekan sembilan untuk mendengar ulang".
- **Jalan keluar:** "tekan nol untuk petugas HR" di setiap menu, dan eskalasi otomatis jika pengguna dua kali tidak dipahami atau menyebut kata sensitif.

Bakukan dengan **Kartu Suara Brand** (persona suara, kecepatan, sapaan baku, kamus pelafalan seperti "K3" → "ka-tiga", label AI), dan uji dengan **Rubrik Ulasan Audio**: layak siar jika ≥15 dari 18, tanpa skor 1 pada akurasi dan tata kelola.

> **Waspada *vishing*:** suara pimpinan kini bisa dikloning dari rekaman beberapa detik. Terapkan protokol: (1) kebijakan tertulis bahwa perusahaan tidak pernah meminta transfer dana, kata sandi, atau data karyawan lewat telepon saja; (2) verifikasi lewat saluran kedua; (3) prosedur verifikasi internal untuk tim Finance, Payroll, dan HRIS; (4) edukasi berkala; (5) batasi publikasi rekaman suara panjang pimpinan. ***Voice cloning* hanya boleh dilakukan dengan persetujuan tertulis pemilik suara.** Suara adalah data biometrik, termasuk data pribadi yang bersifat spesifik menurut UU PDP.

---

# BAGIAN VI — TATA KELOLA DAN ETIKA: PAGAR YANG MEMBUAT KITA BERANI MELAJU

Ada anggapan bahwa tata kelola memperlambat inovasi. Saya justru melihat sebaliknya: rem yang baik membuat pengemudi berani melaju lebih cepat. Organisasi tanpa pagar AI biasanya terjebak di salah satu dari dua ekstrem: melarang total, sehingga karyawan memakai AI diam-diam (***shadow AI***), atau membebaskan total, lalu menghadapi insiden data pertama.

## Lima Guardrail Lintas Play

| No. | Prinsip | Wujud konkret |
|---|---|---|
| 1 | **Data pribadi** | Jangan memasukkan data karyawan asli ke alat AI yang tidak disetujui. Pakai data sintetis atau versi *enterprise* yang sesuai UU PDP. |
| 2 | **Verifikasi manusia** | Semua keluaran yang memengaruhi keputusan tentang orang wajib ditinjau manusia yang berwenang. |
| 3 | **Halusinasi** | Minta sumber dan sitasi; cek fakta dan angka sebelum dipakai. |
| 4 | **Transparansi** | Beri label pada konten AI, terutama gambar, video, dan suara; beri tahu karyawan saat mereka berinteraksi dengan AI. |
| 5 | **Bias** | Uji *prompt* dan keluaran terhadap bias gender, usia, suku, agama, dan disabilitas. |

## Peringatan Data Sensitif: Berhenti Sebelum Menempel

Sebelum menempelkan apa pun ke alat AI, tanyakan: **"Apakah ini boleh dibaca orang di luar tim saya?"** Jika tidak, berhenti dan periksa kebijakan. Kategori yang memerlukan kehati-hatian ekstra menurut UU PDP dan praktik HR yang baik:

- **Data pribadi yang bersifat spesifik:** data kesehatan, biometrik (wajah, suara, sidik jari), genetika, catatan kejahatan, data anak, data keuangan pribadi, serta data lain sesuai ketentuan peraturan.
- **Data HR berisiko tinggi:** gaji individu, hasil penilaian kinerja, catatan disiplin, laporan pelecehan, hasil tes psikologi, dan data rekam medis karyawan.
- **Identitas langsung:** NIK, nomor KK, NPWP, nomor BPJS, nomor rekening, alamat rumah, dan nomor telepon pribadi.

Data seperti ini **tidak boleh** dimasukkan ke akun AI pribadi atau alat yang tidak disetujui perusahaan. Jika pemrosesan memang diperlukan, lakukan di platform *enterprise* yang disetujui, dengan dasar pemrosesan yang sah, prinsip **minimalisasi data**, dan persetujuan DPO. *Playbook ini bukan nasihat hukum; konsultasikan penerapannya dengan Legal dan DPO organisasi Anda.*

## Keamanan Agen dan Asisten

- **Injeksi *prompt*:** anggap setiap dokumen, email, atau halaman web yang dibaca AI sebagai **data, bukan perintah**. Batasi hak akses di sisi sistem.
- **Prinsip hak akses minimal:** agen hanya boleh membaca data yang ia butuhkan, untuk orang yang meminta.
- **Jejak audit:** catat masukan, alat yang dipanggil, data yang dibaca, dan siapa yang menyetujui.
- ***Kill switch*:** selalu ada cara mematikan agen dengan cepat dan jalur pengaduan bagi karyawan.

---

# BAGIAN VII — PERSPEKTIF HR: MEMBANGUN KAPABILITAS, BUKAN SEKADAR MENGADAKAN PELATIHAN

Inilah bagian yang paling sering hilang dari pembahasan AI di organisasi. Kita membeli lisensi, mengadakan lokakarya dua hari, lalu tiga bulan kemudian angka pemakaiannya menurun. Sebabnya jarang soal teknologi. Biasanya karena kita memperlakukan AI sebagai **alat**, padahal yang sedang kita ubah adalah **cara kerja**.

## 1. Mulai dari Pekerjaan, Bukan dari Alat

Jangan bertanya *"Bagaimana kita memakai AI?"* Tanyakan *"Pekerjaan mana yang paling banyak menyita waktu tim tetapi paling sedikit membutuhkan penilaian manusia?"* Petakan tugas di setiap peran ke dalam empat kotak:

| | Penilaian manusia rendah | Penilaian manusia tinggi |
|---|---|---|
| **Frekuensi tinggi** | **Otomatiskan bertahap** (FAQ kebijakan, ringkasan tiket) → Play 8–9 | **Perkuat dengan kopilot** (analisis *exit interview*, draf rekomendasi) → Play 4–6 |
| **Frekuensi rendah** | **Pustaka *prompt*** cukup (draf memo tahunan) → Play 3 | **Tetap manusia**, AI sebagai teman berpikir (PHK, kasus disiplin, negosiasi serikat) |

## 2. Peta Kompetensi Prompting per Jenjang

| Jenjang | Siapa | Kompetensi minimum | Bukti |
|---|---|---|---|
| **Pengguna** | Semua karyawan | 5K, 3P, guardrail data, verifikasi hasil | 3 *prompt* terdokumentasi sebelum–sesudah |
| **Praktisi** | HRBP, analis, L&D, komunikasi | CoT, ToT, RIV, data sintetis, ulasan konten multimodal | 10 *prompt* di pustaka tim + satu analisis RIV |
| **Pembangun** | *AI champion*, HR tech, *people analytics* | MAPAN, uji 10 pertanyaan sulit, Kanvas 5P, Skills, integrasi API/MCP | Satu asisten kustom lulus uji dan berpemilik |
| **Penjaga** | Pimpinan HR, Legal, DPO, TI | Matriks delegasi, risiko UU PDP, audit, kebijakan *shadow AI* | Kebijakan pemakaian AI dan registri asisten/agen |

## 3. Peta Jalan Adopsi 30-60-90 Hari

Perubahan perilaku tidak terjadi dalam satu lokakarya. Mengikuti logika John Kotter (urgensi, koalisi, kemenangan cepat, pelembagaan), susun adopsi seperti ini:

**Hari 1–30: Bangun fondasi dan rasa aman.**
- Terbitkan kebijakan pemakaian AI satu halaman: alat yang disetujui, data yang dilarang, dan siapa yang bisa ditanya.
- Latih seluruh tim HR pada Bagian I dan VI.
- Tunjuk 1 *AI champion* per 15–20 orang. Pilih yang penasaran dan dipercaya rekan, bukan hanya yang paling paham teknologi.
- Mulai pustaka *prompt* tim dengan 10 *prompt* pertama.

**Hari 31–60: Kemenangan cepat yang terlihat.**
- Pilih 2–3 kasus berfrekuensi tinggi (misalnya FAQ kebijakan cuti dan ringkasan survei).
- Bangun satu asisten kustom dengan MAPAN, uji dengan data sintetis, dan pastikan ada pemiliknya.
- Ukur sebelum dan sesudah: waktu yang dihemat, kualitas jawaban, dan kepuasan pengguna.
- Ceritakan keberhasilannya dengan angka dan kisah nyata pengguna di forum internal.

**Hari 61–90: Lembagakan.**
- Masukkan kompetensi prompting ke profil peran dan rencana pengembangan individu.
- Buat registri asisten dan agen: nama, pemilik, tingkat otonomi, data yang diakses, tanggal tinjauan.
- Jadwalkan tinjauan berkala pustaka *prompt* dan asisten setiap kuartal.
- Rancang langkah berikutnya: naik ke L2 (kopilot terhubung) **hanya** untuk kasus yang sudah terbukti di L1.

## 4. Metrik yang Bermakna

Hindari metrik kosong seperti "jumlah lisensi aktif". Ukur apa yang benar-benar berubah:

| Dimensi | Contoh metrik |
|---|---|
| **Adopsi** | % karyawan yang memakai AI mingguan untuk tugas kerja; jumlah *prompt* di pustaka yang dipakai ulang |
| **Efisiensi** | Waktu siklus tugas (misalnya penyusunan deskripsi jabatan dari 3 jam menjadi 45 menit) |
| **Kualitas** | % jawaban asisten yang akurat dan berujukan; tingkat koreksi oleh peninjau |
| **Keamanan** | Jumlah insiden data; % asisten yang lulus uji 10 pertanyaan sulit; temuan *shadow AI* |
| **Pengalaman** | Kepuasan pengguna asisten; waktu respons layanan HR |
| **Kapabilitas** | % karyawan per jenjang kompetensi; jumlah *AI champion* aktif |

## 5. Sisi Manusia yang Tidak Boleh Diabaikan

- **Rasa aman psikologis.** Orang tidak akan bereksperimen jika takut terlihat bodoh atau takut pekerjaannya tergantikan. Buka ruang untuk bertanya dan gagal. Amy Edmondson menyebutnya fondasi organisasi yang mau belajar.
- **Kecemasan akan pekerjaan.** Bicarakan secara jujur. Sampaikan tugas mana yang akan berubah, kapabilitas baru apa yang dibutuhkan, dan bagaimana perusahaan mendukung transisinya. Diam adalah pesan yang paling menakutkan.
- ***Growth mindset*.** Kemahiran prompting tumbuh dari iterasi, bukan dari bakat. Rayakan perbaikan *prompt*, bukan hanya hasil akhirnya.
- **Akuntabilitas tetap pada manusia.** "AI yang menyarankan" bukan alasan yang bisa diterima di depan karyawan, serikat pekerja, atau pengadilan.

---

## Penutup: Prompt Terbaik adalah Cermin Cara Kita Berpikir

Setelah bertahun-tahun mendampingi organisasi melalui berbagai gelombang teknologi, mulai dari HRIS, *cloud*, analitik, hingga AI generatif, satu pola terus berulang: **teknologi mempercepat apa pun yang sudah ada.** Organisasi dengan cara berpikir yang jernih menjadi lebih cepat dan lebih tajam. Organisasi dengan proses yang kusut hanya menjadi kusut lebih cepat.

Karena itu, *prompting* sejatinya adalah latihan berpikir. Formula 5K memaksa kita memperjelas tujuan. CNP memaksa kita menetapkan kriteria sebelum memilih. MAPAN memaksa kita menentukan batas wewenang. Kanvas 5P memaksa kita bertanya siapa yang bertanggung jawab. Semua itu adalah disiplin manajemen yang baik, yang kebetulan kini diuji oleh mesin.

Maka pertanyaan yang layak kita bawa pulang bukan *"Seberapa canggih AI kita?"*, melainkan:

> ***"Jika AI mengerjakan separuh pekerjaan rutin kita besok pagi, apakah kita sudah tahu apa yang akan kita lakukan dengan separuh waktu yang tersisa, dan apakah orang-orang kita sudah siap?"***

Jawaban atas pertanyaan itulah yang membedakan organisasi yang sekadar memakai AI dari organisasi yang tumbuh bersamanya.

---

# LAMPIRAN

## Lampiran A — Kartu Ringkas Semua Formula

| Formula | Kepanjangan | Untuk apa | Play |
|---|---|---|---|
| **5K** | Karakter, Konteks, Kerja, Kemasan, Kendala | Anatomi *prompt* efektif | 1 |
| **3P** | Pisahkan, Pandu, Patok | *Prompt* terstruktur dengan XML | 2 |
| **Tangga Teknik** | Zero-shot → Few-shot → Terstruktur → CoT → ToT → Meta → Chaining | Memilih teknik sesuai kompleksitas | 0, 3 |
| **4T** | Tetapkan, Tahapkan, Tunjukkan, Tarik | *Chain-of-Thought* | 4 |
| **CNP** | Cabangkan, Nilai, Pangkas | *Tree-of-Thought* | 5 |
| **RIV** | Rancang, Implementasi, Verifikasi | Masalah kompleks berlapis | 6 |
| **MAPAN** | Misi, Audiens, Pengetahuan, Aturan, Naikkan | Instruksi asisten kustom | 8 |
| **Tangga Otonomi** | L0 Obrolan → L1 Asisten → L2 Kopilot → L3 Agen+persetujuan → L4 Otonom terbatas | Menaikkan otonomi bertahap | 0, 9 |
| **5P** | Pemicu, Perkakas, Proses, Persetujuan, Pencatatan | Kanvas agen AI | 9 |
| **3S** | Sasaran, Skema, Sebaran | *Brief* data sintetis | 10 |
| **5 Cacat** | Pencilan, Kosong, Miring, Ganda, Salah format | Data *stress-test* | 11 |
| **3K** | Kemiripan, Kegunaan, Kerahasiaan | Mutu data sintetis | 11 |
| **SKETSA** | Subjek, Komposisi, Estetika, Tata cahaya, Sentuhan warna & tekstur, Aspek rasio | *Prompt* gambar | 12 |
| **3T** | Tandai, Tentukan, Tahan | Edit gambar (*inpainting/outpainting*) | 12 |
| **KIT** | Kait, Isi, Tindakan | Naskah video/audio pendek | 13 |
| **KAMERA** | Karakter, Aksi, Medan, Efek kamera, Ritme, Atmosfer | *Prompt* adegan video | 13 |
| **SUARA** | Singkat, Urut, Angka dieja, Akrab, Ritme | Naskah untuk telinga | 14 |
| **3J** | Jelas, Jeda, Jalan keluar | Desain interaksi suara | 14 |

## Lampiran B — Pohon Keputusan Cepat

```
Apakah tugas ini menyangkut data pribadi karyawan nyata?
├── Ya  → Apakah platformnya disetujui perusahaan & ada dasar pemrosesan UU PDP?
│         ├── Tidak → BERHENTI. Gunakan data sintetis (Play 10).
│         └── Ya    → Lanjut, dengan minimalisasi data dan verifikasi manusia.
└── Tidak → Apakah tugasnya sekali jalan?
          ├── Ya    → Satu jawaban benar?  Ya → 5K/3P (Play 1–2)
          │                                Tidak → ToT (Play 5)
          │           Butuh analisis berlapis? → CoT (Play 4) / RIV (Play 6)
          └── Tidak → Dipakai banyak orang dengan dokumen rujukan?
                      ├── Tidak → Simpan di pustaka prompt (Play 3)
                      └── Ya    → Lolos uji kelayakan? → Asisten MAPAN (Play 8)
                                  Perlu bertindak di sistem lain? → Kanvas 5P (Play 9)
                                  Keputusan tentang orang? → maksimal L2, manusia memutuskan
```

## Lampiran C — Daftar Periksa Harian Sebelum Menekan "Kirim"

- [ ] Apakah rekan baru bisa memahami *prompt* ini tanpa penjelasan tambahan?
- [ ] Apakah data yang saya tempel bebas dari data pribadi yang tidak boleh dibagikan?
- [ ] Apakah saya sudah mematok format dan panjang keluaran?
- [ ] Apakah saya mengizinkan AI berkata "tidak tahu"?
- [ ] Apakah angka, fakta, dan sitasi akan saya cek sebelum dipakai?
- [ ] Jika hasilnya memengaruhi seseorang, siapa manusia yang akan memutuskan?
- [ ] Jika *prompt* ini bagus, sudahkah saya menyimpannya ke pustaka tim?

## Lampiran D — Pemetaan Fitur Lintas Platform

| Kebutuhan | Claude (Anthropic) | ChatGPT (OpenAI) | Gemini (Google) | Microsoft Copilot |
|---|---|---|---|---|
| Mode berpikir | *Extended Thinking* | *Reasoning/Thinking* | *Thinking* | Mode penalaran |
| Riset multisumber | Research | Deep Research | Deep Research | Researcher agent |
| Asisten kustom | Projects, Skills, Styles | Custom GPTs | Gems | Copilot Studio Agents |
| Integrasi sistem | API, Tool Use, Connectors/MCP | API, Actions | API, Extensions | Connectors, Power Platform |
| Data & kode | Artifacts, *analysis tool* | Data Analysis | Canvas | Copilot di Excel |
| Gambar | Tidak membuat; *prompt* visual + *vision* | Pembuatan & edit gambar | Imagen | Designer |
| Suara | Mode suara | Mode suara | Gemini Live/TTS | Mode suara |

> **Catatan:** nama fitur dan ketersediaannya berubah cepat. Cek ulang di setiap platform sebelum dipakai dalam pelatihan atau kebijakan.

## Lampiran E — Rujukan Materi Sumber

Playbook ini merangkum dan memperluas materi di repositori ini:
- [[Kurikulum Pelatihan Prompting AI]]
- [[Modul 1 - Prompting Efektif dan Lanjutan]] → Bagian I
- [[Modul 2 - Penalaran AI CoT dan ToT]] → Bagian II
- [[Modul 3 - Asisten AI Kustom dan Integrasi]] → Bagian III
- [[Modul 4 - Membuat Data Sintetis]] → Bagian IV
- [[Modul 5 - Teks ke Gambar Inpainting dan Outpainting]] → Bagian V, Play 12
- [[Modul 6 - Pembuatan Video dengan AI]] → Bagian V, Play 13
- [[Modul 7 - Pembuatan Suara dengan AI]] → Bagian V, Play 14

Bagian VI (perluasan tata kelola) dan Bagian VII (perspektif HR tentang membangun kapabilitas) adalah tambahan baru di luar modul.

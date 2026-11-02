# Modul 1 — Prompting Efektif dan Lanjutan
### Materi Pelatihan · Kurikulum Pelatihan Prompting AI

---

## Pengantar Modul

**Ide pokok modul:** Kualitas jawaban AI ditentukan oleh kualitas instruksi yang diberikan. *Prompt* yang terstruktur dapat mengubah AI dari "mesin jawaban generik" menjadi "rekan kerja yang paham konteks", dan keterampilan ini berlaku di Claude, ChatGPT, maupun Gemini.

### Tujuan Pembelajaran
Setelah menyelesaikan modul ini, peserta mampu:
1. Menjelaskan cara LLM membaca *prompt* (token, jendela konteks, *system prompt*) dan dampaknya pada kualitas jawaban.
2. Menyusun *prompt* dengan **Formula 5K**, lalu memilih teknik *zero-shot* atau *few-shot* yang tepat.
3. Menyusun *prompt* kompleks dengan **tag XML**, format keluaran yang dipatok, dan proses berpikir yang dipandu (**Formula 3P**).
4. Menerapkan pengantar teknik lanjutan (CoT, ToT, *meta-prompting*) dan membangun **pustaka *prompt*** tim.

### Agenda Sesi (±6 jam)

| Waktu | Bab | Aktivitas |
|---|---|---|
| 0:00–0:15 | Pembuka | *Ice breaker*: "*Prompt* terburuk yang pernah saya tulis" |
| 0:15–1:45 | **Bab 1.1** Fondasi | Konsep, Formula 5K, praktik *zero/few-shot* |
| 1:45–2:00 | Rehat | — |
| 2:00–3:45 | **Bab 1.2** Penguatan | Tag XML, Formula 3P, praktik ringkasan *exit interview* |
| 3:45–4:30 | Rehat & makan siang | — |
| 4:30–5:45 | **Bab 1.3** Penguasaan | CoT, ToT, *meta-prompting*, kartu pustaka *prompt* |
| 5:45–6:00 | Penutup | Kuis singkat & refleksi |

> **Persiapan peserta:** akun Claude.ai (wajib), ditambah ChatGPT dan/atau Gemini (disarankan) untuk latihan perbandingan. **Semua data dalam latihan bersifat sintetis/fiktif.** Jangan memasukkan data karyawan asli.

---

# BAB 1.1 — Fondasi: Memahami Cara LLM Membaca *Prompt*

## 1.1.1 Overview Konsep

### a. Apa itu *prompt engineering*?
*Prompt engineering* adalah keterampilan menyusun instruksi untuk model AI agar menghasilkan keluaran yang **akurat, relevan, dan bisa langsung dipakai**. Ini bukan keterampilan pemrograman. Ini keterampilan **memberi *brief* yang baik**, sama seperti seorang manajer memberi tugas kepada anggota tim baru yang cerdas tetapi belum mengenal perusahaan.

> **Analogi kunci:** Bayangkan Claude sebagai **karyawan baru yang sangat pintar, tetapi baru masuk hari pertama**. Ia menguasai banyak hal, tetapi tidak tahu budaya perusahaan Anda, audiens Anda, atau standar kualitas Anda, kecuali Anda memberitahunya.

### b. Cara LLM memproses masukan
| Konsep | Penjelasan sederhana | Dampak praktis |
|---|---|---|
| **LLM (*Large Language Model*)** | Model yang memprediksi kata (token) berikutnya berdasarkan pola dari data latih yang sangat besar | AI tidak "mengetahui" fakta perusahaan Anda; ia menebak jawaban yang paling mungkin dari konteks |
| **Token** | Potongan kata yang menjadi satuan baca model. Teks bahasa Indonesia umumnya memakai lebih banyak token daripada teks bahasa Inggris yang setara | Memengaruhi batas panjang percakapan dan biaya penggunaan API |
| **Jendela konteks** (*context window*) | "Memori kerja" model dalam satu percakapan, yaitu semua *prompt*, dokumen, dan jawaban yang bisa ia lihat sekaligus (Claude: ratusan ribu token) | Percakapan yang sangat panjang dan berganti-ganti topik bisa menurunkan kualitas jawaban; lebih baik **mulai percakapan baru per topik** |
| **Halusinasi** | Model menghasilkan informasi yang terdengar meyakinkan tetapi salah | Wajib verifikasi fakta, angka, pasal regulasi, dan nama |
| ***Knowledge cutoff*** | Batas tanggal data latih model | Untuk informasi terbaru, gunakan fitur pencarian web atau unggah dokumen |

### c. *Zero-shot* vs *few-shot prompting*
- ***Zero-shot*:** memberi tugas **tanpa contoh**. Cocok untuk tugas umum yang standarnya sudah jelas (merangkum, menerjemahkan, membuat draf email).
- ***Few-shot (multishot)*:** memberi **2–5 contoh** masukan beserta keluaran yang diharapkan. Cocok ketika Anda butuh **format, gaya, atau kategori yang spesifik** dan konsisten.

### d. *Prompt* pengguna vs *system prompt* / instruksi kustom
| Jenis | Fungsi | Di mana mengaturnya |
|---|---|---|
| ***Prompt* pengguna** | Permintaan spesifik saat itu | Kotak obrolan |
| ***System prompt* / instruksi kustom** | "Aturan main" yang berlaku untuk seluruh percakapan: peran, gaya, batasan | **Claude:** *Project instructions*, *profile preferences*, **Styles** · **ChatGPT:** *Custom Instructions*, Projects, Custom GPTs · **Gemini:** **Gems**, *Saved info* |

> **So-what:** Hal yang Anda ulangi di setiap *prompt* (nama perusahaan, gaya bahasa, audiens) sebaiknya dipindahkan ke instruksi kustom. Dengan begitu *prompt* harian menjadi lebih pendek dan hasilnya lebih konsisten.

## 1.1.2 Framework & Formula

### Formula 5K: Anatomi *Prompt* yang Efektif

```
PROMPT EFEKTIF = Karakter + Konteks + Kerja + Kemasan + Kendala  (+ Contoh bila perlu)
```

| Unsur | Pertanyaan kunci | Contoh frasa |
|---|---|---|
| **K1 – Karakter** (peran) | Sebagai siapa AI harus berpikir? | "Anda adalah HR Business Partner senior di industri ritel dengan 15 tahun pengalaman…" |
| **K2 – Konteks** | Situasi, latar, audiens, dan tujuan apa yang perlu ia ketahui? | "Perusahaan kami memiliki 120 toko, *turnover* kasir 45% per tahun, dokumen ini untuk calon pelamar lulusan SMA/SMK…" |
| **K3 – Kerja** (tugas) | Apa persisnya yang harus dihasilkan? (pakai kata kerja jelas) | "Susun deskripsi jabatan untuk posisi Store Supervisor…" |
| **K4 – Kemasan** (format) | Seperti apa bentuk keluarannya? | "Format: judul, ringkasan 3 kalimat, 5 tanggung jawab utama (poin), kualifikasi (tabel wajib/diutamakan). Maksimal 300 kata." |
| **K5 – Kendala** (batasan) | Apa yang harus dihindari atau dipatuhi? | "Gunakan bahasa inklusif, hindari syarat usia dan jenis kelamin, sesuaikan dengan regulasi ketenagakerjaan Indonesia." |

### Aturan Emas: Uji Rekan Baru
> *"Jika prompt Anda diberikan kepada rekan kerja yang baru masuk tanpa penjelasan tambahan, apakah ia bisa mengerjakannya dengan benar?"*
> Jika rekan itu akan bingung, AI pun akan bingung. (Prinsip ini juga dianjurkan dalam panduan *prompting* Anthropic.)

### Matriks Keputusan: *Zero-shot* atau *Few-shot*?

| Kondisi | *Zero-shot* | *Few-shot* |
|---|---|---|
| Tugas umum, standar kualitas jelas | ✅ | — |
| Format/gaya keluaran harus seragam | — | ✅ |
| Kategori klasifikasi khusus milik perusahaan | — | ✅ |
| Gaya bahasa khas brand/perusahaan | — | ✅ |
| Eksplorasi ide awal | ✅ | — |

**Tips *few-shot*:** buat contoh yang **beragam** (jangan semuanya mirip), **relevan** dengan kasus nyata, dan **dibungkus jelas** (misalnya dengan tag `<contoh>`) agar tidak tercampur dengan instruksi.

## 1.1.3 How To — Langkah Menyusun *Prompt* Efektif

**Langkah 1 — Tentukan keluaran akhir dulu.** Sebelum mengetik, jawab pertanyaan: "Dokumen atau jawaban seperti apa yang akan saya pakai, dan untuk siapa?"

**Langkah 2 — Isi Formula 5K.** Tulis setiap unsur dalam 1–3 kalimat. Unsur yang paling sering terlupa adalah **Konteks** dan **Kemasan**.

**Langkah 3 — Pilih *zero-shot* atau *few-shot*** memakai matriks di atas. Jika *few-shot*, siapkan 2–5 contoh.

**Langkah 4 — Jalankan di Claude.ai.**
- Untuk tugas sekali jalan, ketik di obrolan baru.
- Untuk tugas berulang, simpan **Karakter, Konteks, dan Kendala** di *Project instructions* (Claude Projects) atau di **Styles**.

**Langkah 5 — Evaluasi dengan daftar periksa:**
- [ ] Apakah jawaban menjawab tugas (K3) secara tuntas?
- [ ] Apakah format (K4) dipatuhi?
- [ ] Apakah ada fakta, angka, atau regulasi yang perlu diverifikasi?
- [ ] Apakah nadanya sesuai audiens?
- [ ] Apakah ada batasan (K5) yang dilanggar?

**Langkah 6 — Iterasi dengan umpan balik spesifik.** Hindari "kurang bagus, perbaiki". Gunakan instruksi spesifik seperti: *"Bagian tanggung jawab terlalu umum. Tambahkan indikator kinerja terukur untuk setiap poin, misalnya target penjualan atau skor audit toko."*

> **Catatan lintas platform:** Formula 5K berlaku sama di ChatGPT dan Gemini. Bedanya hanya di tempat menyimpan instruksi permanen: *Custom Instructions* atau GPTs di ChatGPT, **Gems** di Gemini.

## 1.1.4 Studi Kasus & Contoh

### Studi Kasus A — Deskripsi Jabatan di Perusahaan Ritel
**Situasi:** *PT Sinar Ritel Nusantara (fiktif)*, jaringan 120 minimarket, kesulitan merekrut **Store Supervisor**. Lowongan yang ditulis dengan AI terlihat generik dan menarik pelamar yang tidak sesuai.

**❌ *Prompt* sebelum (tanpa formula):**
```
Buatkan job description Store Supervisor.
```
**Hasil tipikal:** daftar tugas umum yang bisa berlaku di perusahaan mana pun, tanpa konteks ritel lokal, dengan syarat yang berpotensi diskriminatif (usia maksimal, "berpenampilan menarik").

**✅ *Prompt* sesudah (Formula 5K):**
```
[KARAKTER] Anda adalah HR Business Partner senior di industri ritel modern Indonesia
dengan pengalaman 15 tahun dalam rekrutmen posisi operasional toko.

[KONTEKS] PT Sinar Ritel Nusantara memiliki 120 minimarket di Jawa Barat. Store Supervisor
memimpin 6–10 kru toko, bertanggung jawab atas penjualan harian, stok, dan audit kebersihan.
Turnover posisi ini 35% per tahun karena ekspektasi pekerjaan tidak jelas saat rekrutmen.
Target pelamar: kru toko senior atau lulusan D3 dengan pengalaman ritel.

[KERJA] Susun deskripsi jabatan Store Supervisor untuk iklan lowongan eksternal.

[KEMASAN] Format:
1. Judul posisi dan lokasi
2. Ringkasan peran (3 kalimat, menggambarkan hari kerja yang realistis)
3. Tanggung jawab utama (5 poin, masing-masing dengan indikator kinerja terukur)
4. Kualifikasi dalam tabel: kolom "Wajib" dan "Diutamakan"
5. Apa yang kami tawarkan (3 poin)
Maksimal 300 kata.

[KENDALA] Gunakan bahasa inklusif. Jangan mencantumkan batas usia, jenis kelamin, status
pernikahan, atau penampilan fisik. Sebutkan dengan jujur bahwa pekerjaan ini melibatkan sistem
shift dan kerja akhir pekan.
```

**Kutipan hasil yang diharapkan:**
> **Ringkasan Peran:** Sebagai Store Supervisor, Anda memimpin tim 6–10 kru dalam sistem shift untuk memastikan toko buka tepat waktu, rak terisi, dan pelanggan terlayani dengan baik. Hari kerja Anda mencakup *briefing* kru, pengecekan stok, dan rekap penjualan harian…
> **Tanggung jawab:** Mencapai target penjualan harian toko (indikator: ≥95% dari target bulanan) …

**Pelajaran:** Unsur **Konteks** (alasan *turnover*) membuat AI menekankan ekspektasi kerja yang realistis. Unsur **Kendala** mencegah syarat diskriminatif.

### Studi Kasus B — Klasifikasi Tiket Layanan Karyawan (*Few-shot*)
**Situasi:** Tim HR Shared Services *PT Lintas Cepat Logistik (fiktif)* menerima ratusan pesan karyawan per minggu dan ingin mengklasifikasikannya secara konsisten.

**✅ *Prompt few-shot*:**
```
Klasifikasikan pesan karyawan ke salah satu kategori: PAYROLL, CUTI, BPJS, KEBIJAKAN, LAINNYA.
Tentukan juga urgensi: TINGGI / SEDANG / RENDAH.

<contoh>
Pesan: "Gaji saya bulan ini kurang Rp 450.000, lembur minggu lalu belum masuk."
Kategori: PAYROLL | Urgensi: TINGGI
</contoh>
<contoh>
Pesan: "Bagaimana cara mengajukan cuti melahirkan untuk istri?"
Kategori: CUTI | Urgensi: SEDANG
</contoh>
<contoh>
Pesan: "Apakah ada aturan dress code untuk kunjungan ke klien?"
Kategori: KEBIJAKAN | Urgensi: RENDAH
</contoh>

Sekarang klasifikasikan:
Pesan: "Kartu BPJS Kesehatan anak saya ditolak di rumah sakit, padahal sudah didaftarkan bulan lalu."
```
**Hasil yang diharapkan:** `Kategori: BPJS | Urgensi: TINGGI`

**Pelajaran:** Tanpa contoh, AI bisa membuat kategori sendiri ("Asuransi", "Kesehatan"). Contoh mengunci **kategori dan format** sehingga hasilnya siap dimasukkan ke sistem tiket.

### 🗣️ Catatan Fasilitator — Bab 1.1
- **Latihan (20 menit):** Peserta menulis ulang satu *prompt* yang biasa mereka pakai dengan Formula 5K, lalu membandingkan hasil sebelum dan sesudah.
- **Pertanyaan diskusi:** *"Unsur 5K mana yang paling sering Anda lupakan, dan apa akibatnya pada hasil?"*

---

# BAB 1.2 — Penguatan: *Prompt* yang Terstruktur, Spesifik, dan Presisi

## 1.2.1 Overview Konsep

### a. Mengapa *prompt* perlu struktur?
Ketika *prompt* memuat **instruksi + dokumen + contoh + format** sekaligus, AI bisa "bingung" membedakan mana perintah dan mana data. Struktur membantu model:
1. **Memisahkan** instruksi dari data, sehingga isi dokumen tidak dianggap sebagai perintah.
2. **Mengikuti urutan** langkah kerja yang Anda tentukan.
3. **Menghasilkan format yang konsisten** dan siap pakai (tabel, JSON, kerangka memo).

### b. Tag XML: praktik yang disarankan Anthropic untuk Claude
Claude dilatih untuk memperhatikan **tag XML** sebagai penanda bagian *prompt*. Nama tag bebas dan tidak ada tag "resmi", asalkan konsisten dan bermakna.

```xml
<konteks>…latar belakang…</konteks>
<dokumen>…teks kebijakan / data…</dokumen>
<instruksi>…langkah kerja…</instruksi>
<format_keluaran>…bentuk jawaban…</format_keluaran>
```

> **Padanan di LLM lain:** ChatGPT dan Gemini juga memahami tag XML. Mereka juga bekerja baik dengan **judul Markdown** (`### Konteks`) atau pembatas seperti `"""` dan `---`. Yang penting adalah **konsistensi**.

### c. Teknik presisi utama

| Teknik | Penjelasan | Catatan platform |
|---|---|---|
| **Dokumen di atas, pertanyaan di bawah** | Untuk dokumen panjang, letakkan dokumen di awal *prompt* dan instruksi/pertanyaan di akhir | Dianjurkan Anthropic untuk konteks panjang; kualitas jawaban cenderung lebih baik |
| ***Prefill* (mengisi awal jawaban)** | Menentukan kata pertama jawaban AI agar format terkunci, misalnya memulai dengan `{` untuk JSON | Tersedia penuh di **Claude API/Console**. Di Claude.ai, tiru dengan instruksi: *"Mulai jawaban langsung dengan tabel, tanpa pembuka."* |
| **Format keluaran terstruktur** | Tabel, JSON, poin bernomor, templat memo | Untuk integrasi sistem, gunakan JSON + skema contoh |
| **Proses berpikir dipandu** | Menentukan urutan kerja AI: *"Analisis dulu → temukan pola → baru rekomendasi"* | Fondasi untuk CoT di Bab 1.3 |
| **Instruksi positif** | Katakan apa yang **harus** dilakukan, bukan hanya yang dilarang | "Tulis dalam paragraf mengalir" lebih efektif daripada "Jangan pakai poin" |
| **Jelaskan alasan di balik aturan** | AI mengikuti aturan lebih baik jika tahu alasannya | *"Hindari singkatan karena dokumen ini dibaca karyawan pabrik yang baru"* |
| **Izinkan "tidak tahu"** | Beri izin eksplisit untuk menjawab "tidak ada di dokumen" | Menurunkan risiko halusinasi secara signifikan |

## 1.2.2 Framework & Formula

### Formula 3P: *Prompt* Presisi

```
PROMPT PRESISI = Pisahkan + Pandu + Patok
```

| P | Makna | Implementasi |
|---|---|---|
| **P1 – Pisahkan** | Pisahkan instruksi, konteks, data, dan contoh | Bungkus setiap bagian dengan tag XML |
| **P2 – Pandu** | Pandu proses berpikir AI langkah demi langkah | Instruksi bernomor: "1. Baca… 2. Identifikasi… 3. Kelompokkan… 4. Rekomendasikan…" |
| **P3 – Patok** | Patok format dan standar keluaran | Templat tabel/JSON, batas kata, nada, contoh keluaran |

### Templat Induk *Prompt* Terstruktur (gabungan 5K + 3P)

```xml
<peran>
[K1 – Karakter: siapa AI dalam tugas ini]
</peran>

<konteks>
[K2 – Konteks: situasi, audiens, tujuan bisnis]
</konteks>

<dokumen>
[Data / teks sumber — letakkan di sini, terutama bila panjang]
</dokumen>

<instruksi>
[K3 – Kerja, dipandu langkah demi langkah]
1. ...
2. ...
3. ...
</instruksi>

<batasan>
[K5 – Kendala + alasannya; izinkan menjawab "tidak ditemukan di dokumen"]
</batasan>

<format_keluaran>
[K4 – Kemasan: templat tabel/JSON/memo, batas panjang]
</format_keluaran>
```

### Pemetaan Penerapan per Fungsi

| Fungsi | Contoh tugas | Teknik paling berdampak |
|---|---|---|
| **HR – Rekrutmen** | Deskripsi jabatan, penyaringan CV, pertanyaan wawancara | Patok format + kendala anti-bias |
| **HR – Layanan karyawan** | Menjawab pertanyaan kebijakan | Pisahkan dokumen kebijakan + izinkan "tidak tahu" |
| **HR – Analitik** | Ringkasan survei / *exit interview* | Pandu langkah analisis + keluaran tabel/JSON |
| **Pemasaran rekrutmen** | Konten *employer branding* | *Few-shot* gaya brand + patok panjang per kanal |
| **Layanan pelanggan** | Templat balasan keluhan | Pandu: empati → fakta → solusi → tindak lanjut |

## 1.2.3 How To — Mengubah *Prompt* Biasa Menjadi *Prompt* Terstruktur

**Langkah 1 — Mulai dari *prompt* 5K** yang sudah Anda buat di Bab 1.1.

**Langkah 2 — Pisahkan (P1).** Identifikasi bagian *prompt* yang berupa **data** (dokumen, transkrip, tabel). Pindahkan ke tag `<dokumen>` dan letakkan di bagian atas jika panjang.

**Langkah 3 — Pandu (P2).** Ubah "Kerja" menjadi **langkah bernomor**, dari memahami, lalu menganalisis, sampai menghasilkan keluaran.

**Langkah 4 — Patok (P3).** Tulis **templat keluaran persis** seperti yang Anda inginkan, termasuk judul kolom tabel atau kunci JSON.

**Langkah 5 — Tambahkan pengaman.** Masukkan kalimat: *"Jika informasi tidak ada di dokumen, tulis 'Tidak ditemukan di dokumen'. Jangan menebak."*

**Langkah 6 — Uji di dua platform.** Jalankan *prompt* yang sama di Claude dan ChatGPT/Gemini. Catat perbedaan kepatuhan format dan akurasinya.

**Langkah 7 — Simpan sebagai templat.** Simpan *prompt* yang berhasil di **Claude Project** sebagai *project knowledge* atau di dokumen pustaka *prompt* tim (lihat Bab 1.3).

> **Tips Claude.ai:** Untuk dokumen panjang (PDF kebijakan, Excel), **unggah berkasnya** daripada menyalin-tempel. Rujuk berkas tersebut di instruksi, misalnya: *"Berdasarkan dokumen Peraturan Perusahaan yang saya unggah…"*. Untuk hasil berupa dokumen atau tabel yang akan diedit ulang, minta Claude membuatnya sebagai **Artifact**.

## 1.2.4 Studi Kasus & Contoh

### Studi Kasus C — Analisis *Exit Interview* di Perusahaan Logistik
**Situasi:** *PT Lintas Cepat Logistik (fiktif)* memiliki 30 catatan *exit interview* (sintetis) dari kurir dan staf gudang. Head of HR membutuhkan ringkasan untuk rapat direksi minggu depan.

**❌ *Prompt* sebelum:**
```
Ini hasil exit interview, tolong dirangkum. [tempel 30 catatan]
```
**Hasil tipikal:** ringkasan naratif panjang, tanpa angka, tanpa prioritas, dan sulit dipakai di rapat direksi.

**✅ *Prompt* sesudah (Formula 3P):**
```xml
<peran>
Anda adalah analis People Analytics senior yang menyiapkan bahan rapat direksi.
</peran>

<konteks>
PT Lintas Cepat Logistik (2.500 karyawan) mengalami turnover kurir 52% per tahun.
Direksi ingin tahu 3 akar masalah utama dan tindakan prioritas. Direksi membaca
cepat, jadi ringkasan harus padat dan berbasis angka.
</konteks>

<dokumen>
[30 catatan exit interview sintetis: ID, posisi, masa kerja, alasan keluar (teks bebas)]
</dokumen>

<instruksi>
1. Baca seluruh catatan dan kelompokkan alasan keluar ke dalam tema.
2. Hitung jumlah dan persentase karyawan per tema.
3. Identifikasi apakah pola berbeda antara kurir dan staf gudang, serta antara masa kerja <1 tahun dan ≥1 tahun.
4. Pilih 3 tema dengan dampak terbesar dan rumuskan rekomendasi tindakan untuk masing-masing.
</instruksi>

<batasan>
Gunakan hanya informasi dari dokumen. Jika suatu pola tidak cukup didukung data
(kurang dari 3 catatan), tandai sebagai "indikasi awal". Jangan mengutip nama atau ID
karyawan di ringkasan karena dokumen ini akan dibagikan ke direksi.
</batasan>

<format_keluaran>
Mulai langsung dengan judul berupa kesimpulan utama (satu kalimat), lalu:
1. Tabel: | Tema | Jumlah | % | Posisi paling terdampak | Contoh kutipan (anonim) |
2. Temuan perbedaan segmen (maksimal 3 poin)
3. Tabel rekomendasi: | Prioritas | Tindakan | Pemilik | Perkiraan waktu |
Maksimal 1 halaman.
</format_keluaran>
```

**Kutipan hasil yang diharapkan:**
> **Kesimpulan: 60% kurir keluar dalam tahun pertama karena skema insentif per paket dinilai tidak transparan, bukan karena gaji pokok.**
> 
   `| Tema | Jumlah | % | Posisi paling terdampak | Contoh kutipan (anonim) |`
> `|---|---|---|---|---|`
> `| Insentif tidak transparan | 12 | 40% | Kurir (<1 thn) | "Saya tidak pernah tahu hitungan bonus paket saya." |`
> `| Beban rute tidak adil | 8 | 27% | Kurir | … |`
> `| … | … | … | … | …` |

**Pelajaran:** **Pisahkan** membuat AI tidak bingung membedakan data dan instruksi. **Pandu** memastikan ada analisis segmen. **Patok** menghasilkan bahan yang siap ditayangkan di rapat direksi.

### Studi Kasus D — Asisten Jawaban Kebijakan Cuti (Industri Manufaktur)
**Situasi:** *PT Baja Prima Manufaktur (fiktif)* ingin draf jawaban konsisten untuk pertanyaan cuti dari operator pabrik.

**✅ *Prompt* terstruktur dengan pengaman anti-halusinasi:**
```xml
<dokumen>
[Kutipan Peraturan Perusahaan Bab Cuti — versi sintetis]
</dokumen>

<pertanyaan_karyawan>
"Saya operator shift malam. Kalau saya ambil cuti tahunan 2 hari pas hari Sabtu-Minggu
yang jadwal kerja saya, dihitung berapa hari cuti?"
</pertanyaan_karyawan>

<instruksi>
1. Cari pasal yang relevan di dokumen.
2. Jawab pertanyaan berdasarkan pasal tersebut.
3. Sebutkan nomor pasal sebagai rujukan.
</instruksi>

<batasan>
Jawab HANYA berdasarkan dokumen. Jika aturannya tidak jelas atau tidak ada, katakan
bahwa pertanyaan ini perlu dikonfirmasi ke HR Site, karena jawaban yang salah bisa
berdampak pada gaji karyawan.
</batasan>

<format_keluaran>
Bahasa sederhana untuk operator pabrik, maksimal 5 kalimat, nada ramah.
Akhiri dengan: "Rujukan: Pasal [x]".
</format_keluaran>
```

**Pelajaran:** Kalimat alasan (*"karena jawaban yang salah bisa berdampak pada gaji"*) dan izin untuk **tidak menjawab** membuat AI lebih hati-hati. Ini fondasi sebelum membangun asisten kebijakan di Modul 3.

### 🗣️ Catatan Fasilitator — Bab 1.2
- **Latihan (30 menit):** Peserta mendapat 15 catatan survei keterlibatan (sintetis), lalu menyusun *prompt* 3P untuk menghasilkan tabel tema dan rekomendasi. Bandingkan hasilnya di Claude dan satu platform lain.
- **Pertanyaan diskusi:** *"Apa risiko jika AI menjawab pertanyaan kebijakan tanpa izin untuk berkata 'tidak tahu'?"*

---

# BAB 1.3 — Penguasaan: Pengantar Prompting Lanjutan

## 1.3.1 Overview Konsep

Bab ini memperkenalkan empat teknik lanjutan. CoT dan ToT didalami di **Modul 2**.

### a. *Chain-of-Thought* (CoT): berpikir bertahap
Meminta AI **menuliskan langkah penalarannya sebelum memberi jawaban akhir**. CoT meningkatkan akurasi pada tugas yang butuh logika, perhitungan, atau analisis berlapis.
- **Cara manual:** *"Pikirkan langkah demi langkah di dalam tag `<thinking>`, lalu tulis jawaban akhir di tag `<jawaban>`."*
- **Cara bawaan platform:** aktifkan **Extended Thinking** (mode berpikir) di Claude, atau mode *reasoning/thinking* di ChatGPT dan Gemini. Model akan berpikir lebih dalam sebelum menjawab.

### b. *Tree-of-Thought* (ToT): menjelajahi beberapa jalur
Meminta AI **mengembangkan beberapa alternatif solusi, menilai masing-masing dengan kriteria, lalu memilih yang terbaik**. Cocok untuk keputusan strategis yang tidak punya satu jawaban benar.

### c. *Meta-prompting*: AI yang menyusun *prompt*
Meminta AI **menyusun, mengkritik, atau memperbaiki *prompt***. Ini mempercepat pembuatan *prompt* kompleks.
- **Claude.ai:** minta langsung, misalnya *"Bantu saya menyusun prompt untuk…"*.
- **Anthropic Console:** fitur **Prompt Generator** (membuat *prompt* dari deskripsi tugas) dan **Prompt Improver** (memperbaiki *prompt* yang sudah ada).
- **Padanan:** GPT Builder (ChatGPT), fitur bantuan penulisan instruksi saat membuat Gem (Gemini).

### d. Pustaka *prompt* (*prompt library*)
*Prompt* yang sudah teruji adalah **aset organisasi**. Pustaka *prompt* yang terdokumentasi dan terkontrol versinya:
- mencegah setiap orang "menemukan ulang roda",
- menjaga konsistensi kualitas dan kepatuhan (anti-bias, privasi),
- menjadi bahan baku untuk asisten AI kustom (Claude Projects/Skills, GPTs, Gems) di Modul 3.

## 1.3.2 Framework & Formula

### Tangga Teknik Prompting: Pilih Teknik Sesuai Kompleksitas

```
Kompleksitas tugas ▲
                   │  7. Prompt Chaining   — memecah tugas besar menjadi beberapa prompt berurutan
                   │  6. Meta-prompting    — AI menyusun/memperbaiki prompt
                   │  5. Tree-of-Thought   — beberapa opsi → dinilai → dipilih
                   │  4. Chain-of-Thought  — penalaran bertahap / Extended Thinking
                   │  3. Prompt Terstruktur (3P) — XML, format dipatok
                   │  2. Few-shot          — dengan contoh
                   │  1. Zero-shot (5K)    — instruksi jelas tanpa contoh
                   └──────────────────────────────────────────────────────►
```
> **Prinsip:** naiki tangga **hanya jika perlu**. Teknik yang lebih tinggi memakan lebih banyak waktu dan token. Banyak tugas harian sudah cukup diselesaikan di anak tangga 1–3.

### Formula Teknik Lanjutan

| Teknik | Formula | Kapan dipakai |
|---|---|---|
| **CoT** | `Tugas + "Pikirkan langkah demi langkah di <thinking>" + "Jawaban akhir di <jawaban>"` | Analisis berlapis, perhitungan, diagnosis masalah |
| **ToT** | `Masalah + "Kembangkan N opsi" + "Nilai tiap opsi dengan kriteria [a, b, c]" + "Pilih & beri alasan"` | Keputusan strategis, banyak alternatif |
| ***Meta-prompting*** | `Tujuan + audiens + contoh keluaran ideal + "Susun prompt terbaik dengan Formula 5K & 3P, lalu tanyakan informasi yang kurang"` | Membuat *prompt* baru yang kompleks atau akan dipakai ulang |
| ***Prompt chaining*** | `Prompt 1 (ekstrak) → Prompt 2 (analisis) → Prompt 3 (rekomendasi)` | Tugas besar dengan tahap yang jelas berbeda |

### Kartu Pustaka *Prompt* (Templat Standar)

| Kolom | Isi |
|---|---|
| **Nama & ID** | contoh: `HR-ANL-003 Analisis Absensi Shift` |
| **Versi & tanggal** | v1.2 — 14/10/2026 |
| **Pemilik** | Nama/peran penanggung jawab |
| **Tujuan & kasus penggunaan** | Kapan *prompt* ini dipakai |
| **Teknik** | contoh: 3P + CoT |
| ***Prompt*** | Teks lengkap dengan **variabel** bertanda `{{nama_variabel}}` |
| **Variabel masukan** | Daftar variabel dan contoh isinya |
| **Platform yang diuji** | Claude ✅ · ChatGPT ✅ · Gemini ⚠️ (catatan perbedaan) |
| **Contoh keluaran** | Satu contoh hasil yang baik |
| **Catatan risiko & tata kelola** | Jenis data yang boleh dimasukkan, titik verifikasi manusia |

## 1.3.3 How To

### A. Menjalankan CoT dan ToT di Claude.ai
1. Untuk analisis sedang: tambahkan instruksi CoT manual (`<thinking>` / `<jawaban>`).
2. Untuk analisis berat (strategi, data kompleks): aktifkan **Extended Thinking** di pengaturan obrolan Claude.
3. Untuk ToT: minta **jumlah opsi yang spesifik** (misalnya 3) dan **kriteria penilaian yang eksplisit**. Tanpa kriteria, AI cenderung memilih opsi "yang terdengar paling bagus".

### B. Siklus *Meta-prompting* (4 Langkah)
1. **Deskripsikan** tugas, audiens, dan contoh keluaran ideal kepada Claude.
2. **Minta Claude menyusun *prompt*** dengan Formula 5K + 3P dan **menanyakan informasi yang kurang**.
3. **Uji *prompt*** hasil susunan Claude di obrolan baru. Obrolan baru penting agar tidak terpengaruh konteks sebelumnya.
4. **Minta kritik dan perbaikan:** *"Ini prompt dan hasilnya. Hasilnya kurang di [x]. Perbaiki prompt-nya, jangan hasilnya."*

> Alternatif: tempel *prompt* Anda ke **Prompt Improver** di Anthropic Console untuk mendapat versi yang lebih terstruktur secara otomatis.

### C. Membangun Pustaka *Prompt* Tim
1. **Kumpulkan** 10 *prompt* yang paling sering dipakai tim.
2. **Standarkan** dengan Formula 5K/3P dan ganti bagian yang berubah-ubah dengan `{{variabel}}`.
3. **Uji** di minimal dua platform, lalu catat hasilnya di Kartu Pustaka *Prompt*.
4. **Simpan** di lokasi bersama: dokumen tim, Notion/SharePoint, atau langsung sebagai *project knowledge* di **Claude Project** tim.
5. **Kelola versi:** setiap perubahan dicatat (v1.0 → v1.1) beserta alasannya. Tinjau ulang setiap kuartal atau saat model AI diperbarui.

## 1.3.4 Studi Kasus & Contoh

### Studi Kasus E — Absensi Shift Malam di Pabrik (CoT → ToT → Meta-prompting)
**Situasi:** *PT Baja Prima Manufaktur (fiktif)*, 1.800 karyawan. Tingkat ketidakhadiran **shift malam 9,5%**, sedangkan shift pagi 3,2%. Plant Manager meminta HR mencari akar masalah dan solusi dalam 2 minggu. Data yang dipakai adalah **data sintetis** hasil rekap absensi 6 bulan.

**Tahap 1 — CoT: mendiagnosis akar masalah**
```xml
<dokumen>
[Rekap absensi sintetis 6 bulan: shift, departemen, masa kerja, hari, alasan izin]
</dokumen>

<instruksi>
Analisis mengapa absensi shift malam jauh lebih tinggi daripada shift pagi.
Pikirkan langkah demi langkah di dalam tag <thinking>:
1. Bandingkan pola per hari, departemen, dan masa kerja.
2. Identifikasi korelasi yang menonjol.
3. Bedakan antara "fakta dari data" dan "dugaan yang perlu divalidasi".
Lalu tulis 3 hipotesis akar masalah utama di tag <jawaban>, masing-masing dengan bukti datanya.
</instruksi>
```
**Kutipan hasil yang diharapkan:**
> `<jawaban>` **H1:** Absensi memuncak pada hari Senin malam (14,1%), terutama pada karyawan dengan masa kerja <1 tahun. Ini mengindikasikan masalah adaptasi ritme tidur dan pola rotasi. **H2:** … **H3:** Departemen *finishing* menyumbang 41% ketidakhadiran shift malam (*perlu validasi: apakah terkait beban kerja atau supervisor?*) …

**Tahap 2 — ToT: memilih intervensi**
```
Berdasarkan 3 hipotesis tadi, kembangkan 3 opsi intervensi yang berbeda pendekatannya:
(a) perubahan sistem rotasi shift, (b) insentif dan kesejahteraan, (c) kepemimpinan supervisor.

Nilai setiap opsi dengan skor 1–5 pada kriteria: dampak terhadap absensi, biaya,
kecepatan implementasi, dan risiko penolakan serikat pekerja.
Tampilkan dalam tabel, lalu rekomendasikan kombinasi terbaik beserta alasannya.
```
**Kutipan hasil yang diharapkan:**

| Opsi | Dampak | Biaya (5 = murah) | Kecepatan | Risiko serikat (5 = rendah) | Total |
|---|---|---|---|---|---|
| (a) Rotasi maju 2-2-3 | 5 | 4 | 2 | 2 | 13 |
| (b) Tunjangan & transport malam | 3 | 2 | 5 | 5 | 15 |
| (c) Coaching supervisor finishing | 4 | 4 | 4 | 4 | 16 |

> **Rekomendasi:** Mulai dengan (c) + (b) sebagai *quick win* 30 hari. Siapkan (a) melalui dialog dengan serikat pekerja karena dampaknya terbesar, tetapi memerlukan konsultasi…

> **Catatan fasilitator:** Tekankan bahwa skor ini adalah **penilaian AI yang wajib divalidasi manusia**, terutama dalam aspek hubungan industrial.

**Tahap 3 — *Meta-prompting*: menjadikannya *prompt* yang bisa dipakai ulang**
```
Saya ingin analisis seperti tadi bisa dipakai ulang setiap bulan oleh HR di 4 pabrik lain.
Susun satu prompt template dengan Formula 5K dan 3P, gunakan tag XML, gabungkan tahap CoT
dan ToT, dan ganti bagian yang berubah dengan variabel {{nama_pabrik}}, {{periode}},
{{data_absensi}}, {{target_absensi}}. Tanyakan dulu jika ada informasi yang kurang.
```

**Tahap 4 — Simpan ke Pustaka *Prompt***

| Kolom | Isi |
|---|---|
| **Nama & ID** | `HR-ANL-003 Analisis Absensi Shift` |
| **Versi** | v1.0 — 14/10/2026 |
| **Pemilik** | HR Analytics Lead |
| **Teknik** | 3P + CoT + ToT |
| **Variabel** | `{{nama_pabrik}}`, `{{periode}}`, `{{data_absensi}}`, `{{target_absensi}}` |
| **Platform diuji** | Claude ✅ (Extended Thinking aktif) · ChatGPT ✅ · Gemini ✅ |
| **Risiko & tata kelola** | Hanya data agregat/anonim; tanpa nama karyawan. Rekomendasi intervensi wajib ditinjau HR Manager dan IR Specialist sebelum dikomunikasikan. |

**Pelajaran:** Satu masalah bisnis melewati tiga teknik secara berurutan. **CoT** menghasilkan diagnosis yang bisa dipertanggungjawabkan. **ToT** memunculkan *trade-off* secara eksplisit, termasuk risiko serikat pekerja. ***Meta-prompting*** mengubah analisis sekali jalan menjadi **aset organisasi** yang bisa dipakai di 4 pabrik lain.

### Contoh Tambahan — *Meta-prompting* untuk Pemula
```
Saya HR Generalist. Saya ingin prompt untuk membuat pertanyaan wawancara berbasis
kompetensi (metode STAR) untuk posisi apa pun. Audiens: user/hiring manager non-HR.
Contoh keluaran ideal: 5 pertanyaan per kompetensi, lengkap dengan indikator jawaban
baik dan jawaban kurang.

Susun prompt terbaik untuk tugas ini dengan Formula 5K (Karakter, Konteks, Kerja,
Kemasan, Kendala). Tanyakan maksimal 3 hal yang perlu Anda ketahui sebelum menyusunnya.
```

### 🗣️ Catatan Fasilitator — Bab 1.3
- **Latihan (35 menit):** Dalam kelompok, peserta memilih satu masalah HR nyata (dengan data sintetis), menjalankan CoT, lalu ToT, kemudian menyusun Kartu Pustaka *Prompt* untuk hasilnya.
- **Pertanyaan diskusi:** *"Kapan Extended Thinking atau ToT justru berlebihan? Siapa di tim Anda yang sebaiknya menjadi 'pemilik' pustaka prompt?"*

---

## Rangkuman Modul 1

| Bab | Formula/Kerangka | Satu kalimat inti |
|---|---|---|
| **1.1 Fondasi** | **5K** (Karakter, Konteks, Kerja, Kemasan, Kendala) + *zero/few-shot* | Perlakukan AI seperti karyawan baru yang pintar: beri *brief* yang lengkap. |
| **1.2 Penguatan** | **3P** (Pisahkan, Pandu, Patok) + tag XML | Struktur memisahkan data dari perintah dan mengunci format agar hasil siap pakai. |
| **1.3 Penguasaan** | **Tangga Teknik** (CoT, ToT, *Meta-prompting*, *Chaining*) + Kartu Pustaka *Prompt* | Naiki tangga teknik hanya bila perlu, dan simpan *prompt* terbaik sebagai aset tim. |

## Kuis Singkat (Kunci Jawaban untuk Fasilitator)

1. **Unsur 5K mana yang menentukan bentuk keluaran?** → *Kemasan (K4).*
2. **Kapan *few-shot* lebih tepat daripada *zero-shot*?** → *Saat format, gaya, atau kategori keluaran harus spesifik dan seragam.*
3. **Untuk dokumen panjang, di mana sebaiknya instruksi diletakkan?** → *Di bagian akhir, setelah dokumen.*
4. **Apa fungsi kalimat "Jika tidak ada di dokumen, katakan tidak ditemukan"?** → *Mengurangi risiko halusinasi.*
5. **Apa beda CoT dan ToT?** → *CoT adalah satu jalur penalaran bertahap; ToT menjelajahi beberapa opsi, menilainya, lalu memilih.*
6. **Fitur apa di Anthropic Console yang membantu memperbaiki *prompt* secara otomatis?** → *Prompt Improver (dan Prompt Generator untuk membuat dari nol).*

## Tugas Portofolio (Masuk Penilaian 30%)
Kumpulkan **3 Kartu Pustaka *Prompt*** dari pekerjaan Anda sendiri (dengan data sintetis):
- 1 *prompt* Formula 5K (zero- atau few-shot),
- 1 *prompt* Formula 3P dengan tag XML,
- 1 *prompt* hasil *meta-prompting* atau kombinasi CoT/ToT.

Setiap kartu wajib menyertakan **versi sebelum dan sesudah** beserta catatan pengujian di minimal dua platform.

---
> **Catatan tata kelola:** Semua nama perusahaan dan data dalam modul ini fiktif atau sintetis. Dalam praktik nyata, pastikan penggunaan AI dengan data karyawan mengikuti kebijakan perusahaan dan **UU Pelindungan Data Pribadi (UU PDP)**.

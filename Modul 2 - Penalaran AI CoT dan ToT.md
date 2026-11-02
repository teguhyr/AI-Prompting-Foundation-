# Modul 2 — Penalaran AI: *Chain-of-Thought* & *Tree-of-Thought*
### Materi Pelatihan · Kurikulum Pelatihan Prompting AI

---

## Pengantar Modul

**Ide pokok modul:** AI menjawab lebih akurat ketika diberi ruang untuk **berpikir dulu sebelum menjawab**. *Chain-of-Thought* (CoT) membuat AI bernalar **satu jalur secara bertahap**, sedangkan *Tree-of-Thought* (ToT) membuat AI **menjelajahi beberapa jalur lalu memilih yang terbaik**. Menguasai keduanya, dan tahu kapan **tidak** memakainya, adalah pembeda antara pengguna AI biasa dan pengguna AI yang strategis.

### Tujuan Pembelajaran
Setelah menyelesaikan modul ini, peserta mampu:
1. Menjelaskan mengapa "berpikir dulu" meningkatkan akurasi LLM, serta perbedaan CoT manual (lewat *prompt*) dan **mode berpikir** (*Extended Thinking* di Claude, mode *reasoning/thinking* di ChatGPT dan Gemini).
2. Menyusun *prompt* CoT dengan **Formula 4T** untuk analisis data HR, ekstraksi dokumen, dan pemecahan masalah bisnis.
3. Menyusun *prompt* ToT dengan **Formula CNP** (Cabangkan, Nilai, Pangkas) untuk menghasilkan dan membandingkan beberapa alternatif solusi, termasuk memakai **Research / Deep Research** untuk eksplorasi multisumber.
4. Menggabungkan ToT dan CoT dalam **Siklus RIV** (Rancang, Implementasi, Verifikasi) untuk masalah kompleks dan perencanaan jangka panjang, lengkap dengan verifikasi penalaran (*self-critique*).

### Agenda Sesi (±6 jam)

| Waktu | Bab | Aktivitas |
|---|---|---|
| 0:00–0:15 | Pembuka | *Ice breaker*: "Teka-teki yang dijawab salah oleh AI" (uji tanpa vs dengan CoT) |
| 0:15–1:45 | **Bab 2.1** Fondasi | Prinsip penalaran AI, Formula 4T, praktik ringkasan survei & ekstraksi CV |
| 1:45–2:00 | Rehat | — |
| 2:00–3:45 | **Bab 2.2** Penguatan | ToT, Formula CNP, praktik strategi retensi & kampanye *employer branding*, Research |
| 3:45–4:30 | Rehat & makan siang | — |
| 4:30–5:45 | **Bab 2.3** Penguasaan | Siklus RIV, *self-critique*, praktik utama *attrition* 3 posisi kritis |
| 5:45–6:00 | Penutup | Kuis singkat & refleksi |

> **Persiapan peserta:** akun Claude.ai (wajib; pastikan bisa mengaktifkan **Extended Thinking** dan **Research**, ketersediaannya bergantung pada paket langganan), ditambah ChatGPT dan/atau Gemini (disarankan) untuk latihan perbandingan. **Semua data dalam latihan bersifat sintetis/fiktif.** Jangan memasukkan data karyawan asli.

> **Kaitan dengan Modul 1:** Modul ini memperdalam anak tangga 4 (CoT) dan 5 (ToT) dari **Tangga Teknik Prompting** di Bab 1.3. Formula **5K** dan **3P** tetap menjadi kerangka dasar setiap *prompt* di modul ini.

---

# BAB 2.1 — Fondasi: Prinsip Penalaran AI dan *Chain-of-Thought*

## 2.1.1 Overview Konsep

### a. Mengapa "berpikir dulu" membuat AI lebih akurat?
LLM menghasilkan jawaban **token demi token**, dan setiap token baru dipengaruhi oleh token sebelumnya (*next-token prediction*). Akibatnya:
- Jika AI langsung menulis jawaban akhir, ia harus "menebak" kesimpulan **tanpa sempat menyusun langkah antara**.
- Jika AI menulis langkah penalarannya lebih dulu, langkah-langkah itu **menjadi konteks** bagi jawaban akhir. Kesimpulan dibangun di atas analisis, bukan sebaliknya.

> **Analogi kunci:** Minta seorang analis menjawab "berapa biaya *turnover* kita tahun ini?" dalam 3 detik, ia akan menebak. Beri ia kertas coretan dan 10 menit, ia akan menghitung. **CoT adalah kertas coretan untuk AI.**

### b. Dua cara memberi AI "kertas coretan"

| Cara | Mekanisme | Di mana | Kelebihan | Keterbatasan |
|---|---|---|---|---|
| **CoT manual (lewat *prompt*)** | Anda meminta AI menulis penalaran di tag `<thinking>` lalu jawaban di `<jawaban>` | Semua platform, semua model | Anda mengendalikan **langkah apa** yang harus dipikirkan; penalaran terlihat dan bisa diperiksa | Lebih banyak token; kualitas bergantung pada langkah yang Anda tulis |
| **Mode berpikir bawaan** | Model dilatih untuk bernalar panjang secara internal sebelum menjawab | **Claude:** *Extended Thinking* · **ChatGPT:** model/mode *reasoning (Thinking)* · **Gemini:** mode *Thinking* | Penalaran lebih dalam tanpa harus menulis langkah rinci; kuat untuk logika, matematika, analisis berlapis | Lebih lambat dan lebih mahal; ringkasan penalaran yang ditampilkan bisa berbeda antarplatform |

> **Tips Anthropic untuk Extended Thinking:** saat mode berpikir aktif, instruksi tingkat tinggi (*"Pikirkan masalah ini secara menyeluruh dan pertimbangkan beberapa pendekatan"*) sering lebih efektif daripada langkah yang terlalu kaku. Model diberi ruang untuk menentukan cara bernalarnya sendiri, lalu Anda **memeriksa** penalarannya.

### c. Kapan CoT membantu, kapan tidak?

| Jenis tugas | Perlu CoT? | Alasan |
|---|---|---|
| Menerjemahkan, merapikan email, membuat draf pengumuman | ❌ Tidak | Tidak ada penalaran berlapis; CoT hanya menambah waktu |
| Merangkum dokumen pendek tanpa penilaian | ⚠️ Opsional | Bermanfaat hanya jika perlu memilah tema atau prioritas |
| Menghitung (biaya *turnover*, proporsi, selisih gaji) | ✅ Ya | Mengurangi salah hitung; ideal dikombinasikan dengan *code execution / analysis tool* |
| Mendiagnosis akar masalah dari data | ✅ Ya | Memaksa AI membedakan fakta, pola, dan dugaan |
| Mengekstrak data dari dokumen tidak terstruktur (CV, formulir) | ✅ Ya (ringan) | Membantu AI memutuskan kasus ambigu secara konsisten |
| Keputusan dengan beberapa alternatif | ➡️ Pakai **ToT** (Bab 2.2) | CoT hanya menelusuri satu jalur |

### d. Penalaran yang terlihat ≠ bukti audit
Teks penalaran AI **membantu Anda memeriksa** logikanya, tetapi **bukan jaminan** bahwa itulah proses sebenarnya yang menghasilkan jawaban. Riset tentang model bahasa menunjukkan penalaran yang ditulis model tidak selalu mencerminkan proses internalnya secara utuh.

> **So-what untuk HR:** Jangan memakai teks `<thinking>` sebagai **justifikasi resmi** keputusan tentang orang (rekrutmen, kinerja, PHK). Yang menjadi dasar keputusan adalah **data yang diverifikasi manusia** dan **alasan yang ditulis oleh pengambil keputusan**, bukan narasi AI.

## 2.1.2 Framework & Formula

### Formula 4T: Anatomi *Prompt Chain-of-Thought*

```
PROMPT CoT = Tetapkan + Tahapkan + Tunjukkan + Tarik
```

| T | Makna | Pertanyaan kunci | Contoh frasa |
|---|---|---|---|
| **T1 – Tetapkan** tujuan | Apa pertanyaan yang harus dijawab di akhir? | Keputusan apa yang akan diambil dari jawaban ini? | "Tujuan: menentukan 3 penyebab utama rendahnya skor keterlibatan di toko wilayah Jabar." |
| **T2 – Tahapkan** langkah | Urutan berpikir apa yang harus dilalui AI? | Bagaimana analis terbaik Anda akan mengerjakannya? | "Pikirkan di `<thinking>`: 1. Kelompokkan komentar per tema. 2. Hitung frekuensi. 3. Bandingkan antarsegmen…" |
| **T3 – Tunjukkan** bukti | Bagaimana AI harus mendukung setiap klaim? | Data apa yang membuktikan setiap langkah? | "Untuk setiap temuan, sebutkan angka atau kutipan dari data. Pisahkan **fakta** dan **dugaan**." |
| **T4 – Tarik** kesimpulan | Dalam bentuk apa kesimpulan akhir disajikan? | Apa yang dibaca pengambil keputusan? | "Tulis kesimpulan akhir di `<jawaban>`: satu kalimat inti, lalu tabel temuan." |

> **Hubungan dengan Formula 1.2 (3P):** T2 adalah versi mendalam dari **Pandu**, sedangkan T4 adalah **Patok** untuk jawaban akhir. Tag `<thinking>` dan `<jawaban>` adalah penerapan **Pisahkan** untuk memisahkan proses dari hasil.

### Templat Induk *Prompt* CoT

```xml
<peran>
[K1 – Karakter]
</peran>

<konteks>
[K2 – Konteks + T1: tujuan dan keputusan yang akan diambil]
</konteks>

<data>
[Data sintetis / dokumen sumber]
</data>

<instruksi>
Pikirkan langkah demi langkah di dalam tag <thinking> sebelum menjawab:
1. [T2 – langkah 1: memahami / mengelompokkan]
2. [T2 – langkah 2: menghitung / membandingkan]
3. [T2 – langkah 3: menafsirkan pola]
4. [T3 – pisahkan fakta dari data dan dugaan yang perlu divalidasi]
Setelah selesai, tulis jawaban akhir di dalam tag <jawaban>.
</instruksi>

<format_keluaran>
[T4 – bentuk jawaban akhir: kalimat kesimpulan, tabel, batas panjang]
</format_keluaran>
```

### Matriks Keputusan: CoT Manual, Mode Berpikir, atau Keduanya?

| Kondisi | *Prompt* biasa | CoT manual | Mode berpikir | Keduanya |
|---|---|---|---|---|
| Tugas sederhana, jawaban langsung | ✅ | — | — | — |
| Anda ingin AI mengikuti **metode analisis milik tim** | — | ✅ | — | — |
| Masalah logika/angka yang rumit, metode belum jelas | — | — | ✅ | — |
| Analisis penting yang akan dibawa ke direksi | — | — | — | ✅ (mode berpikir + langkah wajib + format jawaban dipatok) |
| Butuh keluaran yang akan diproses sistem (JSON) | — | ✅ (penalaran dipisah dari JSON) | — | — |

## 2.1.3 How To — Menjalankan CoT di Claude.ai

**Langkah 1 — Tetapkan tujuan (T1).** Tulis satu kalimat: "Jawaban ini akan dipakai untuk memutuskan…". Tanpa tujuan, AI akan menganalisis semua hal secara dangkal.

**Langkah 2 — Tulis langkah analisis (T2)** seperti cara analis terbaik di tim Anda bekerja. Cukup 3–5 langkah. Langkah yang terlalu banyak membuat AI kaku.

**Langkah 3 — Wajibkan bukti (T3).** Tambahkan: *"Untuk setiap temuan, sebutkan angka atau kutipan dari data. Tandai sebagai FAKTA atau DUGAAN."*

**Langkah 4 — Pisahkan proses dan hasil (T4).** Gunakan tag `<thinking>` untuk proses dan `<jawaban>` untuk hasil, sehingga Anda bisa langsung menyalin bagian `<jawaban>` ke laporan.

**Langkah 5 — Pilih mode.**
- Untuk analisis sedang: CoT manual sudah cukup.
- Untuk analisis berat: aktifkan **Extended Thinking** di pengaturan obrolan Claude. Anda tetap bisa menambahkan T3 dan T4 agar bukti dan format terjaga.
- Untuk perhitungan: minta Claude **menghitung dengan *analysis tool* / *code execution***, bukan "di kepala", lalu tampilkan rumusnya.

**Langkah 6 — Baca penalarannya, bukan hanya jawabannya.** Periksa:
- [ ] Apakah ada langkah yang dilewati?
- [ ] Apakah angka di penalaran sama dengan angka di jawaban?
- [ ] Apakah ada DUGAAN yang tiba-tiba diperlakukan sebagai FAKTA di kesimpulan?
- [ ] Apakah kesimpulan benar-benar menjawab tujuan (T1)?

> **Catatan lintas platform:** Formula 4T berlaku sama di ChatGPT dan Gemini. Pada model *reasoning* di ChatGPT dan mode *Thinking* di Gemini, penalaran internal biasanya ditampilkan sebagai ringkasan. Karena itu, T3 (bukti di jawaban akhir) menjadi semakin penting agar Anda tetap bisa memeriksa logikanya.

## 2.1.4 Studi Kasus & Contoh

### Studi Kasus F — Ringkasan Survei Keterlibatan Karyawan (Ritel)
**Situasi:** *PT Sinar Ritel Nusantara (fiktif)* menjalankan survei keterlibatan di 120 toko. Skor wilayah Jawa Barat turun dari 72 menjadi 61, sedangkan wilayah lain stabil. Regional HR Manager memegang 40 komentar terbuka (sintetis) dan harus melapor ke Direktur Operasional dalam 3 hari.

**❌ *Prompt* sebelum (tanpa CoT):**
```
Rangkum komentar survei ini dan jelaskan kenapa skor Jabar turun. [tempel 40 komentar]
```
**Hasil tipikal:** daftar keluhan umum ("beban kerja tinggi", "komunikasi kurang") tanpa angka, tanpa perbandingan, dan dengan penjelasan penurunan yang terdengar masuk akal tetapi tidak ditunjukkan dari data.

**✅ *Prompt* sesudah (Formula 4T):**
```xml
<peran>
Anda adalah analis People Analytics senior di industri ritel modern.
</peran>

<konteks>
Skor keterlibatan wilayah Jawa Barat turun dari 72 menjadi 61 dalam setahun; wilayah lain
stabil di 70–74. Tujuan: menentukan 3 penyebab utama penurunan agar Direktur Operasional
bisa memutuskan intervensi prioritas kuartal depan.
</konteks>

<data>
[40 komentar survei sintetis: ID_toko, posisi (kasir/pramuniaga/supervisor), masa kerja, komentar]
</data>

<instruksi>
Pikirkan langkah demi langkah di dalam tag <thinking>:
1. Kelompokkan setiap komentar ke dalam tema. Satu komentar boleh masuk lebih dari satu tema.
2. Hitung jumlah komentar per tema dan per posisi.
3. Cari tema yang menonjol pada posisi atau masa kerja tertentu.
4. Untuk setiap tema, tandai apakah hubungannya dengan penurunan skor adalah FAKTA (didukung
   data) atau DUGAAN (perlu divalidasi, misalnya dengan data turnover atau jadwal shift).
Setelah itu, tulis jawaban akhir di dalam tag <jawaban>.
</instruksi>

<format_keluaran>
Di dalam <jawaban>:
1. Satu kalimat kesimpulan utama.
2. Tabel: | Penyebab | Jumlah komentar | Posisi paling terdampak | Status (FAKTA/DUGAAN) | Data validasi yang dibutuhkan |
3. Maksimal 3 penyebab. Jangan menyebut ID toko atau ID karyawan.
</format_keluaran>
```

**Kutipan hasil yang diharapkan:**
> `<jawaban>` **Kesimpulan: Penurunan keterlibatan di Jabar terutama didorong oleh perubahan jadwal shift sejak sistem penjadwalan baru diterapkan, dan paling dirasakan kasir dengan masa kerja di bawah 1 tahun.**
>
> | Penyebab | Jumlah komentar | Posisi paling terdampak | Status | Data validasi yang dibutuhkan |
> |---|---|---|---|---|
> | Jadwal shift berubah mendadak | 17 | Kasir (<1 thn) | FAKTA | Log perubahan jadwal 6 bulan |
> | Target penjualan harian naik | 11 | Supervisor | DUGAAN | Data target vs realisasi per toko |
> | … | … | … | … | … |

**Pelajaran:** Langkah 4 (FAKTA vs DUGAAN) mencegah laporan yang terlihat meyakinkan tetapi belum terbukti. Kolom "Data validasi" mengubah ringkasan menjadi **rencana kerja analisis berikutnya**, bukan sekadar laporan.

### Studi Kasus G — Ekstraksi Data CV ke Format Terstruktur (B2B Industri)
**Situasi:** *PT Mitra Teknik Industri (fiktif)*, distributor peralatan industri B2B, merekrut 15 **Technical Sales Engineer**. Recruiter ingin mengekstrak data dari CV (sintetis) yang formatnya sangat beragam ke tabel penyaringan awal.

**✅ *Prompt* CoT ringan untuk ekstraksi:**
```xml
<cv>
[Teks CV sintetis kandidat]
</cv>

<instruksi>
Ekstrak data kandidat. Sebelum menulis hasil, pikirkan di dalam tag <thinking>:
1. Hitung total pengalaman kerja dalam tahun dari tanggal-tanggal yang tercantum.
   Jika ada periode tumpang tindih, jangan dihitung dua kali.
2. Tentukan apakah pengalaman tergolong "penjualan B2B teknis" berdasarkan uraian tugas,
   bukan hanya dari judul jabatan.
3. Jika informasi tidak ada atau ambigu, catat alasannya.
Lalu tulis hasil di dalam tag <jawaban> sebagai JSON sesuai skema.
</instruksi>

<format_keluaran>
{
  "total_pengalaman_tahun": angka,
  "pengalaman_b2b_teknis_tahun": angka,
  "latar_pendidikan_teknik": true/false,
  "sertifikasi_relevan": [daftar],
  "catatan_ambigu": "teks atau null"
}
</format_keluaran>

<batasan>
Jangan mengekstrak atau menilai usia, jenis kelamin, agama, status pernikahan, atau foto.
Data ini hanya untuk penyaringan awal; keputusan lolos/tidak lolos dibuat oleh recruiter.
</batasan>
```

**Kutipan hasil yang diharapkan:**
> `<thinking>` Kandidat bekerja di PT A (Jan 2019–Mar 2022) dan PT B (Jan 2022–sekarang). Ada tumpang tindih 3 bulan, jadi total ±6,8 tahun, bukan 7 tahun. Jabatan "Account Executive" di PT A ternyata menjual software HR ke korporasi, bukan peralatan teknis, sehingga tidak dihitung sebagai B2B teknis…
>
> `<jawaban>` `{"total_pengalaman_tahun": 6.8, "pengalaman_b2b_teknis_tahun": 3.8, ... "catatan_ambigu": "Jabatan di PT A berlabel sales, tetapi produknya bukan peralatan teknis"}`

**Pelajaran:** Tanpa CoT, AI cenderung menjumlahkan tahun secara kasar dan menilai dari judul jabatan. Penalaran singkat membuat kasus ambigu **diputuskan dengan alasan yang terlihat**, dan `catatan_ambigu` memberi recruiter titik periksa manusia.

> **Catatan tata kelola:** Penyaringan CV dengan AI termasuk keputusan tentang orang. Uji *prompt* ini dengan CV sintetis yang identik kecuali nama, gender, atau almamater untuk memastikan tidak ada **bias**. Keputusan akhir tetap di tangan recruiter.

### 🗣️ Catatan Fasilitator — Bab 2.1
- **Demonstrasi pembuka (10 menit):** Ajukan soal hitungan HR yang menjebak (misalnya prorata THR untuk karyawan dengan dua periode kerja) ke AI **tanpa** CoT, lalu **dengan** CoT atau Extended Thinking. Diskusikan perbedaannya.
- **Latihan (25 menit):** Peserta menjalankan Studi Kasus F dengan data sintetis, lalu menukar hasilnya dengan rekan. Rekan memeriksa: apakah ada DUGAAN yang "naik pangkat" menjadi FAKTA di kesimpulan?
- **Pertanyaan diskusi:** *"Apakah teks penalaran AI boleh dilampirkan sebagai alasan keputusan rekrutmen? Mengapa tidak?"*

---

# BAB 2.2 — Penguatan: *Tree-of-Thought* dan Eksplorasi Solusi

## 2.2.1 Overview Konsep

### a. Dari satu jalur ke beberapa cabang
CoT menelusuri **satu jalur** penalaran. Jika langkah awalnya keliru, seluruh jawaban ikut keliru. **Tree-of-Thought (ToT)** mengatasinya dengan meminta AI:
1. **Mengembangkan beberapa jalur pemikiran** (cabang) yang berbeda pendekatannya.
2. **Menilai setiap cabang** dengan kriteria yang jelas.
3. **Memangkas** cabang yang lemah dan **memilih** atau **menggabungkan** cabang terbaik.

```
                        Masalah
              ┌────────────┼────────────┐
          Cabang A     Cabang B     Cabang C        ← Cabangkan
          (skor 11)    (skor 16)    (skor 9)        ← Nilai
              ✂            │            ✂           ← Pangkas
                    ┌──────┴──────┐
               B1 (diperdalam)  B2 (diperdalam)     ← Cabangkan lagi bila perlu
                           │
                    Rekomendasi akhir
```

> **Catatan teknis:** Dalam riset aslinya, ToT dijalankan sebagai **algoritma pencarian** dengan banyak panggilan model yang dikoordinasikan program. Di Claude.ai, ChatGPT, atau Gemini, kita memakai **ToT berbasis *prompt***, yaitu simulasi ToT dalam satu atau beberapa giliran percakapan. Hasilnya tidak seketat versi algoritmik, tetapi sangat efektif untuk keputusan bisnis.

### b. Kapan ToT lebih tepat daripada CoT?

| Ciri masalah | CoT | ToT |
|---|---|---|
| Ada satu jawaban benar (hitungan, ekstraksi) | ✅ | — |
| Ada beberapa solusi yang sama-sama masuk akal | — | ✅ |
| Ada *trade-off* (biaya vs dampak vs risiko) | — | ✅ |
| Pemangku kepentingan punya preferensi berbeda | — | ✅ |
| Tugas kreatif yang butuh variasi ide | — | ✅ |

### c. Tiga jebakan ToT yang paling sering terjadi
| Jebakan | Gejala | Penangkal |
|---|---|---|
| **Cabang kembar** | Tiga opsi yang sebenarnya variasi dari ide yang sama | Tentukan **sudut pendekatan** setiap cabang (misalnya kompensasi vs kepemimpinan vs desain kerja) |
| **Kriteria kabur** | AI memilih opsi yang "terdengar paling bagus" | Tulis kriteria eksplisit, skala skor, dan bobotnya |
| **Skor palsu** | Skor 1–5 terlihat objektif padahal hanya opini AI | Minta **alasan per skor** dan tandai skor yang perlu data atau validasi manusia |

### d. Research dan Deep Research: ToT dengan sumber eksternal
Untuk masalah yang membutuhkan informasi di luar dokumen Anda (tolok ukur industri, praktik perusahaan lain, regulasi terbaru), gunakan fitur riset multisumber:

| Platform | Fitur | Kegunaan dalam ToT |
|---|---|---|
| **Claude** | **Research** (dan pencarian web) | Mengumpulkan bukti per cabang, disertai sitasi |
| **ChatGPT** | **Deep Research** | Laporan riset panjang dengan banyak sumber |
| **Gemini** | **Deep Research** | Rencana riset yang bisa diedit sebelum dijalankan |

> **So-what:** Research memperkuat tahap **Nilai**. Skor setiap cabang tidak lagi hanya berdasarkan "pendapat AI", tetapi juga berdasarkan bukti yang bisa ditelusuri. **Tetap periksa sitasinya**: buka sumber, pastikan angka dan klaimnya benar-benar ada di sana.

## 2.2.2 Framework & Formula

### Formula CNP: Cabangkan, Nilai, Pangkas

```
PROMPT ToT = Cabangkan + Nilai + Pangkas
```

| Tahap | Makna | Implementasi dalam *prompt* |
|---|---|---|
| **C – Cabangkan** | Hasilkan N opsi yang **berbeda pendekatannya** | "Kembangkan 3 opsi dengan sudut pendekatan berbeda: (a) …, (b) …, (c) …" |
| **N – Nilai** | Nilai setiap opsi dengan kriteria eksplisit | "Beri skor 1–5 untuk: dampak, biaya, kecepatan, risiko. Sertakan alasan satu kalimat per skor." |
| **P – Pangkas** | Buang opsi lemah, pilih atau gabungkan yang terbaik | "Pangkas opsi dengan skor terendah dan jelaskan alasannya. Rekomendasikan opsi atau kombinasi terbaik, serta kondisi yang membuat rekomendasi ini berubah." |

### Templat Induk *Prompt* ToT

```xml
<peran>
[K1 – Karakter, misalnya HR Strategy Consultant senior]
</peran>

<konteks>
[K2 – Masalah bisnis, batasan anggaran/waktu, pemangku kepentingan]
</konteks>

<instruksi>
1. CABANGKAN: Kembangkan [N] opsi solusi dengan sudut pendekatan berbeda:
   (a) [sudut 1], (b) [sudut 2], (c) [sudut 3].
   Untuk setiap opsi, jelaskan cara kerjanya dalam 2–3 kalimat.
2. NILAI: Beri skor 1–5 setiap opsi pada kriteria berikut (5 = paling menguntungkan):
   [kriteria 1 (bobot x%)], [kriteria 2 (bobot y%)], [kriteria 3 (bobot z%)].
   Sertakan alasan satu kalimat untuk setiap skor dan tandai skor yang perlu divalidasi data.
3. PANGKAS: Hapus opsi terlemah beserta alasannya. Rekomendasikan opsi atau kombinasi
   terbaik, lalu sebutkan 1–2 kondisi yang akan mengubah rekomendasi ini.
</instruksi>

<format_keluaran>
Tabel penilaian berbobot, lalu rekomendasi maksimal 150 kata.
</format_keluaran>
```

### Pustaka Sudut Cabang untuk Masalah HR
Memilih sudut cabang yang **saling lepas (MECE)** adalah kunci ToT yang baik. Gunakan daftar ini sebagai titik awal:

| Masalah | Sudut cabang yang disarankan |
|---|---|
| Retensi / *attrition* | Imbalan (*reward*) · Kepemimpinan & supervisi · Desain pekerjaan & jadwal · Karier & pengembangan |
| Produktivitas | Proses · Teknologi/alat · Kapabilitas orang · Insentif |
| Rekrutmen sulit | Proposisi nilai karyawan (EVP) · Kanal sumber kandidat · Proses seleksi · Persyaratan jabatan |
| Kampanye *employer branding* | Rasional (fakta & angka) · Emosional (cerita karyawan) · Komunitas/sosial |
| Perencanaan tenaga kerja | *Build* (kembangkan) · *Buy* (rekrut) · *Borrow* (kontrak/alih daya) · *Bot* (otomasi/AI) |

### Kriteria Penilaian Standar (Bisa Diberi Bobot)

| Kriteria | Pertanyaan | Catatan |
|---|---|---|
| **Dampak** | Seberapa besar opsi ini menyelesaikan masalah inti? | Minta AI mengaitkannya ke metrik (misalnya % *attrition*) |
| **Biaya** | Berapa investasi yang dibutuhkan? | Skor 5 = paling murah |
| **Kecepatan** | Berapa lama sampai terlihat hasil? | Bedakan *quick win* (<90 hari) dan struktural |
| **Risiko adopsi** | Seberapa besar penolakan dari manajer, karyawan, atau serikat pekerja? | Kriteria yang paling sering dilupakan AI |
| **Kepatuhan** | Apakah sesuai regulasi ketenagakerjaan dan kebijakan internal? | **Wajib** divalidasi oleh manusia (Legal/IR) |

## 2.2.3 How To — Menjalankan ToT di Claude.ai

**Langkah 1 — Rumuskan masalah dengan tajam.** Masalah yang kabur menghasilkan cabang yang kabur. Gunakan pola: *"Bagaimana kita [tujuan terukur] dalam [waktu], dengan [batasan]?"*

**Langkah 2 — Tentukan sudut cabang (C).** Ambil dari Pustaka Sudut Cabang, atau minta AI mengusulkan sudut yang saling lepas lebih dulu, lalu Anda yang memilih.

**Langkah 3 — Tetapkan kriteria dan bobot (N)** **sebelum** melihat opsi. Menetapkan kriteria setelah melihat opsi rawan bias, baik bias manusia maupun AI.

**Langkah 4 — (Opsional) Perkuat dengan Research.** Untuk setiap cabang yang lolos, jalankan **Research** di Claude: *"Cari bukti dan tolok ukur industri tentang efektivitas [opsi] untuk menurunkan turnover di sektor [x] di Asia Tenggara. Sertakan sitasi."*

**Langkah 5 — Pangkas dan pilih (P).** Minta AI menjelaskan **mengapa opsi dibuang**. Alasan pembuangan sering lebih informatif daripada alasan pemilihan.

**Langkah 6 — Uji ketahanan rekomendasi.** Tanyakan: *"Jika anggaran dipotong 50%, apakah rekomendasimu berubah?"* atau *"Bagaimana serikat pekerja akan menanggapi opsi ini?"*

**Langkah 7 — Aktifkan Extended Thinking** jika masalah melibatkan banyak variabel yang saling memengaruhi. Mode berpikir membantu AI mempertimbangkan interaksi antarcabang secara lebih menyeluruh.

> **Variasi ToT multi-percakapan:** Untuk keputusan besar, jalankan setiap cabang di **obrolan terpisah** (atau di Claude, ChatGPT, dan Gemini secara bergantian), lalu bawa ketiga hasilnya ke obrolan baru untuk dinilai. Cara ini mencegah satu cabang "mewarnai" cabang lain, sehingga lebih mendekati ToT versi asli.

## 2.2.4 Studi Kasus & Contoh

### Studi Kasus H — Tiga Strategi Retensi Staf Gudang (Logistik)
**Situasi:** *PT Lintas Cepat Logistik (fiktif)* mengoperasikan 6 gudang distribusi. *Turnover* **picker/packer** mencapai 48% per tahun. Setiap karyawan yang keluar menimbulkan biaya rekrutmen dan pelatihan sekitar **Rp 6,5 juta** *(asumsi)* serta menurunkan akurasi pemenuhan pesanan. Anggaran intervensi tahun ini: **Rp 1,2 miliar**.

**✅ *Prompt* ToT (Formula CNP):**
```xml
<peran>
Anda adalah HR Strategy Consultant senior untuk industri logistik dan rantai pasok.
</peran>

<konteks>
PT Lintas Cepat Logistik: 6 gudang, 900 picker/packer, turnover 48%/tahun.
Biaya per karyawan keluar ±Rp 6,5 juta (asumsi). Anggaran intervensi Rp 1,2 miliar/tahun.
Data exit interview menunjukkan tiga keluhan utama: jadwal shift berubah mendadak,
target harian dianggap tidak realistis, dan tidak ada jenjang karier.
Tujuan: menurunkan turnover ke ≤35% dalam 12 bulan.
</konteks>

<instruksi>
1. CABANGKAN: Kembangkan 3 opsi strategi retensi dengan sudut berbeda:
   (a) Desain kerja & jadwal, (b) Imbalan & insentif, (c) Karier & pengembangan.
   Jelaskan cara kerja setiap opsi dalam 2–3 kalimat dan estimasi biayanya.
2. NILAI: Beri skor 1–5 pada kriteria berikut (5 = paling menguntungkan):
   Dampak terhadap turnover (bobot 35%), Biaya (20%), Kecepatan hasil (20%),
   Risiko adopsi oleh supervisor gudang (25%).
   Sertakan alasan satu kalimat per skor dan tandai [VALIDASI] untuk skor yang
   membutuhkan data tambahan.
3. PANGKAS: Hapus opsi terlemah dan jelaskan alasannya. Rekomendasikan opsi atau
   kombinasi dalam batas anggaran, lalu hitung perkiraan penghematan biaya turnover
   jika target 35% tercapai. Sebutkan 2 kondisi yang akan mengubah rekomendasi.
</instruksi>

<format_keluaran>
1. Tabel: | Opsi | Dampak | Biaya | Kecepatan | Risiko adopsi | Skor berbobot |
2. Opsi yang dipangkas dan alasannya (maksimal 2 kalimat).
3. Rekomendasi dan perhitungan penghematan (tampilkan rumusnya).
</format_keluaran>
```

**Kutipan hasil yang diharapkan:**

| Opsi | Dampak (35%) | Biaya (20%) | Kecepatan (20%) | Risiko adopsi (25%) | Skor berbobot |
|---|---|---|---|---|---|
| (a) Jadwal shift dikunci 2 minggu di muka + target berbasis kapasitas | 4 | 4 | 4 | 3 [VALIDASI] | 3,75 |
| (b) Bonus retensi 6 & 12 bulan | 3 | 2 | 5 | 5 | 3,70 |
| (c) Jalur karier picker → team leader → supervisor | 4 | 3 | 2 | 4 | 3,40 |

> **Pangkas:** Opsi (c) dipertahankan sebagai fase kedua, bukan dibuang, karena dampaknya baru terlihat setelah 9–12 bulan. Opsi (b) **tidak** dipilih sebagai strategi utama karena hanya menunda keluarnya karyawan tanpa menyentuh akar masalah jadwal.
>
> **Rekomendasi:** Jalankan (a) di 2 gudang percontohan selama 90 hari, lalu perluas. Siapkan (c) paralel.
> **Perhitungan:** Penurunan turnover 48% → 35% = 13% × 900 = 117 karyawan yang bertahan × Rp 6,5 juta = **±Rp 760 juta penghematan per tahun** *(belum termasuk dampak akurasi pesanan)*.
> **Kondisi yang mengubah rekomendasi:** (1) jika sistem WMS tidak mendukung penguncian jadwal, (2) jika data menunjukkan pesaing menaikkan upah >15%.

> **Catatan fasilitator:** Tunjukkan bahwa skor "Risiko adopsi 3 [VALIDASI]" pada opsi (a) adalah titik yang paling penting dibahas. Supervisor gudang yang terbiasa mengubah jadwal secara mendadak akan kehilangan fleksibilitas. Di sinilah lensa **manajemen perubahan** masuk.

### Studi Kasus I — Kampanye *Employer Branding* (ToT untuk Tugas Kreatif)
**Situasi:** *PT Baja Prima Manufaktur (fiktif)* sulit menarik lulusan SMK teknik dan D3 karena dianggap "pabrik yang panas, kotor, dan tidak modern", padahal sudah memakai otomasi di lini produksi.

**✅ *Prompt* ToT kreatif:**
```
Kembangkan 3 konsep kampanye employer branding untuk menarik lulusan SMK teknik dan D3,
masing-masing dengan pendekatan berbeda:
(a) Rasional: fakta otomasi, keselamatan kerja, dan jenjang karier dengan angka.
(b) Emosional: cerita operator muda yang tumbuh menjadi teknisi otomasi.
(c) Komunitas: kolaborasi dengan SMK lewat kelas industri dan kompetisi robotik.

Untuk setiap konsep, tulis: tagline, pesan inti, 3 kanal utama, dan satu contoh konten.
Lalu nilai setiap konsep (1–5) untuk: daya tarik bagi Gen Z, kredibilitas (bisa dibuktikan
dengan fakta perusahaan), biaya produksi, dan kecocokan dengan budaya K3 perusahaan.
Rekomendasikan konsep utama dan satu elemen dari konsep lain yang layak digabungkan.
```

**Kutipan hasil yang diharapkan:**
> **Rekomendasi:** Konsep (b) *"Dari Operator ke Ahli Otomasi"* sebagai konsep utama (skor tertinggi pada daya tarik Gen Z dan kredibilitas), diperkuat oleh elemen kompetisi robotik dari konsep (c) sebagai sumber cerita yang autentik…

**Pelajaran:** Dalam tugas kreatif, ToT mencegah AI langsung memberikan satu ide "aman" yang generik. Kriteria **kredibilitas** memaksa setiap konsep berpijak pada fakta perusahaan, sehingga kampanye tidak menjanjikan hal yang tidak bisa dibuktikan.

> **Tips:** Lanjutkan dengan **Research** di Claude: *"Cari data tentang faktor yang paling memengaruhi pilihan kerja lulusan SMK di Indonesia dalam 3 tahun terakhir, dengan sitasi."* Gunakan hasilnya untuk menguji ulang skor "daya tarik bagi Gen Z".

### 🗣️ Catatan Fasilitator — Bab 2.2
- **Latihan (35 menit):** Dalam kelompok, peserta memilih satu masalah dari Pustaka Sudut Cabang, menetapkan kriteria dan bobot **sebelum** menjalankan *prompt*, lalu menjalankan ToT di dua platform. Bandingkan: apakah kedua platform memangkas opsi yang sama?
- **Variasi lanjutan:** Satu kelompok menjalankan ToT dalam satu *prompt*, kelompok lain menjalankan setiap cabang di obrolan terpisah. Diskusikan perbedaan kualitas cabangnya.
- **Pertanyaan diskusi:** *"Jika AI memberi skor tertinggi pada opsi yang Anda tahu akan ditolak serikat pekerja, apa yang salah: opsinya, kriterianya, atau bobotnya?"*

---

# BAB 2.3 — Penguasaan: Memecahkan Masalah Kompleks dengan CoT + ToT

## 2.3.1 Overview Konsep

### a. Alur kerja berlapis: ToT untuk merancang, CoT untuk mengeksekusi
Masalah bisnis yang kompleks jarang selesai dengan satu teknik. Pola yang paling efektif:
- **ToT di hulu (perencanaan):** menjelajahi beberapa hipotesis atau strategi, lalu memilih yang paling menjanjikan.
- **CoT di hilir (eksekusi):** menelusuri hipotesis terpilih secara bertahap dan berbasis bukti sampai menghasilkan rencana tindakan.
- **Verifikasi di akhir:** meminta AI mengkritik hasilnya sendiri dan mengecek angka sebelum dibawa ke pengambil keputusan.

Pola ini identik dengan cara kerja konsultan strategi: **hipotesis dulu (ToT), buktikan atau gugurkan (CoT), uji ketahanan (verifikasi)**.

### b. Verifikasi penalaran: dua lapis pengaman
| Lapis | Teknik | Contoh instruksi |
|---|---|---|
| **Lapis 1 — *Self-critique* oleh AI** | AI berperan sebagai pengkritik atas jawabannya sendiri, sebaiknya di **obrolan baru** agar tidak "membela diri" | *"Berperanlah sebagai Direktur Keuangan yang skeptis. Temukan 3 kelemahan terbesar analisis ini dan asumsi yang paling rapuh."* |
| **Lapis 1 — Cek angka** | Hitung ulang dengan *analysis tool* / *code execution*, bukan dengan penalaran teks | *"Hitung ulang semua angka di analisis ini memakai analysis tool. Tampilkan selisih jika ada."* |
| **Lapis 1 — Konsistensi** | Jalankan *prompt* yang sama 2–3 kali atau di platform berbeda; jawaban yang konsisten lebih dapat dipercaya | Bandingkan hasil Claude, ChatGPT, dan Gemini |
| **Lapis 2 — Verifikasi manusia** | Pemilik data dan pemilik keputusan memeriksa asumsi, angka, dan dampak ke orang | **Wajib** untuk setiap keputusan tentang orang (prinsip tata kelola nomor 2) |

### c. Penerapan lanjutan CoT + ToT di HR dan bisnis

| Skenario | Peran ToT | Peran CoT |
|---|---|---|
| **Pemetaan *employee journey*** | Menjelajahi beberapa persona karyawan dan titik kritis (*moments that matter*) | Menelusuri setiap tahap journey: titik sakit, penyebab, dan intervensi |
| **Pemetaan *customer journey*** (untuk tim penjualan/pemasaran) | Menjelajahi beberapa segmen pelanggan B2B | Menelusuri proses pembelian per segmen |
| **Desain program pengembangan** | Membandingkan format (akademi internal, *coaching*, rotasi, *e-learning*) | Menyusun kurikulum dan indikator keberhasilan format terpilih |
| **Ideasi konten** | Menghasilkan beberapa tema dan sudut cerita | Menyusun kalender konten dan naskah |
| ***Strategic workforce planning*** | Menyusun beberapa **skenario masa depan** (optimis, dasar, disrupsi) | Menghitung kebutuhan tenaga kerja dan kesenjangan kapabilitas per skenario |

### d. ToT untuk strategi jangka panjang: berpikir dengan skenario
Untuk horizon 3–5 tahun, masa depan tidak bisa diprediksi, hanya bisa **dipersiapkan**. ToT dipakai untuk membangun **beberapa skenario yang masuk akal**, lalu mencari **langkah yang tetap bermanfaat di semua skenario** (*no-regret moves*) dan langkah yang hanya diambil jika sinyal tertentu muncul (*signposts*).

## 2.3.2 Framework & Formula

### Siklus RIV: Rancang → Implementasi → Verifikasi

```
┌──────────────────────┐    ┌──────────────────────┐    ┌──────────────────────┐
│  R — RANCANG (ToT)   │ →  │ I — IMPLEMENTASI(CoT)│ →  │ V — VERIFIKASI       │
│  Cabangkan hipotesis │    │ Uji hipotesis terpilih│    │ Self-critique + cek  │
│  Nilai & pangkas     │    │ langkah demi langkah │    │ angka + review manusia│
│  (Formula CNP)       │    │ (Formula 4T)         │    │                      │
└──────────────────────┘    └──────────────────────┘    └──────────┬───────────┘
          ▲                                                        │
          └──────── hipotesis gugur? kembali ke cabang berikutnya ──┘
```

| Tahap | Teknik | Keluaran | Pertanyaan pemeriksa |
|---|---|---|---|
| **R — Rancang** | ToT (CNP) + Research bila perlu | 3 hipotesis/strategi, dinilai, 1–2 dipilih | Apakah cabangnya saling lepas dan kriterianya disepakati? |
| **I — Implementasi** | CoT (4T) + Extended Thinking + *analysis tool* | Analisis berbasis bukti dan rencana tindakan | Apakah setiap klaim punya bukti dan FAKTA dipisahkan dari DUGAAN? |
| **V — Verifikasi** | *Self-critique*, cek angka, uji konsistensi, review manusia | Daftar kelemahan, koreksi, dan keputusan akhir oleh manusia | Siapa pemilik keputusan dan apa jejak auditnya? |

### Kerangka Skenario untuk Perencanaan Jangka Panjang (ToT Strategis)

```
1. Tentukan 2 ketidakpastian utama (misalnya: laju adopsi otomasi, pertumbuhan pasar)
2. Silangkan → 4 skenario (matriks 2×2), beri nama yang mudah diingat
3. Untuk setiap skenario (CoT): kebutuhan tenaga kerja, peran baru/hilang, kesenjangan kapabilitas
4. Cari:  ✔ No-regret moves  — bermanfaat di semua skenario → jalankan sekarang
          ◆ Opsi strategis   — bermanfaat di 2–3 skenario  → siapkan, tunda keputusan
          ⚑ Signposts        — sinyal yang menunjukkan skenario mana yang terjadi → pantau
```

### Prompt Chaining untuk Siklus RIV
Untuk masalah besar, pisahkan Siklus RIV menjadi beberapa *prompt* berurutan (lihat Tangga Teknik, anak tangga 7, di Modul 1):

| Urutan | *Prompt* | Masukan | Keluaran |
|---|---|---|---|
| 1 | ToT: hipotesis | Konteks masalah + data ringkas | 3 hipotesis dinilai |
| 2 | CoT: uji hipotesis terpilih | Hipotesis terpilih + data lengkap | Analisis + bukti |
| 3 | CoT: rencana tindakan | Hasil analisis | Rencana 90 hari |
| 4 | Verifikasi (obrolan baru) | Hasil prompt 2 & 3 | Daftar kelemahan dan koreksi |

## 2.3.3 How To

### A. Menjalankan Siklus RIV di Claude.ai
1. **Siapkan ruang kerja.** Buat **Claude Project** untuk masalah ini, unggah data sintetis sebagai *project knowledge*, dan tulis konteks bisnis di *Project instructions*. Semua obrolan dalam Project otomatis memakai konteks yang sama.
2. **Rancang (R).** Di obrolan pertama, jalankan *prompt* ToT dengan Formula CNP. Pilih 1–2 hipotesis.
3. **Implementasi (I).** Di obrolan kedua, aktifkan **Extended Thinking**, jalankan *prompt* CoT (Formula 4T) untuk hipotesis terpilih, dan minta perhitungan dengan *analysis tool*.
4. **Verifikasi (V).** Di obrolan **ketiga yang baru**, tempel hasil tahap I dan minta *self-critique* dari sudut pemangku kepentingan yang skeptis.
5. **Putuskan.** Bawa hasil ke pemilik keputusan manusia, lengkap dengan daftar asumsi dan titik validasi.
6. **Simpan.** Jadikan rangkaian *prompt* sebagai **Kartu Pustaka *Prompt*** (Modul 1, Bab 1.3) agar bisa dipakai ulang.

### B. *Prompt* Verifikasi Standar (Bisa Disalin)
```
Berikut analisis dan rekomendasi yang dibuat sebelumnya:
<analisis>
[tempel hasil]
</analisis>

Berperanlah sebagai [Direktur Keuangan / Ketua Serikat Pekerja / Auditor Internal]
yang skeptis. Lakukan langkah berikut:
1. Hitung ulang semua angka dengan analysis tool dan laporkan selisihnya.
2. Sebutkan 3 asumsi paling rapuh dan apa akibatnya jika asumsi itu salah.
3. Temukan klaim yang tidak didukung data.
4. Sebutkan satu pemangku kepentingan yang dirugikan oleh rekomendasi ini dan belum
   diperhitungkan.
Jangan memperbaiki analisisnya. Cukup tunjukkan kelemahannya.
```

### C. Kapan Berhenti?
Siklus RIV tidak perlu diulang tanpa akhir. Berhentilah ketika:
- verifikasi tidak lagi menemukan kelemahan **material** (yang mengubah rekomendasi),
- semua DUGAAN yang tersisa sudah punya pemilik dan rencana validasi, atau
- biaya analisis tambahan sudah lebih besar daripada nilai keputusannya.

## 2.3.4 Studi Kasus & Contoh

### Studi Kasus J — *Attrition* Tinggi di 3 Posisi Kritis (Praktik Utama Modul)
**Situasi:** *PT Mitra Teknik Industri (fiktif)*, distributor peralatan industri B2B dengan 1.200 karyawan. Dalam 12 bulan terakhir, *attrition* sukarela di tiga posisi kritis jauh di atas rata-rata perusahaan (11%):

| Posisi | Jumlah | *Attrition* | Dampak bisnis |
|---|---|---|---|
| Technical Sales Engineer | 80 | 31% | Hilangnya relasi pelanggan kunci; *pipeline* penjualan turun |
| Field Service Technician | 150 | 27% | Waktu respons servis memburuk; denda SLA pelanggan |
| Inventory Planner | 25 | 36% | Stok berlebih dan kekurangan stok bersamaan |

CHRO meminta diagnosis dan rencana tindakan untuk dibawa ke rapat direksi dalam 3 minggu. Data yang dipakai adalah **data sintetis** (profil karyawan, *exit interview*, data kompensasi, dan skor survei).

**Tahap R — Rancang dengan ToT (3 hipotesis)**
```xml
<peran>
Anda adalah konsultan People Analytics senior untuk perusahaan distribusi B2B industri.
</peran>

<konteks>
Attrition sukarela 12 bulan: Technical Sales Engineer 31%, Field Service Technician 27%,
Inventory Planner 36%; rata-rata perusahaan 11%. Tujuan: menemukan penyebab yang bisa
ditindaklanjuti dan menurunkan attrition ketiga posisi ke ≤15% dalam 12 bulan.
</konteks>

<data>
[Ringkasan data sintetis: kompensasi vs pasar, masa kerja saat keluar, skor survei per posisi,
tema exit interview, rasio karyawan per atasan]
</data>

<instruksi>
1. CABANGKAN: Susun 3 hipotesis akar masalah yang saling lepas:
   (H1) daya saing kompensasi, (H2) desain pekerjaan dan beban kerja,
   (H3) kualitas kepemimpinan dan jalur karier.
   Untuk setiap hipotesis, sebutkan data apa yang akan membuktikan atau menggugurkannya.
2. NILAI: Beri skor 1–5 setiap hipotesis pada: kekuatan bukti awal dari data,
   cakupan (berapa dari 3 posisi yang dijelaskan), dan kemampuan ditindaklanjuti.
3. PANGKAS: Pilih 1–2 hipotesis untuk diuji lebih dalam dan jelaskan mengapa yang lain ditunda.
</instruksi>
```

**Kutipan hasil yang diharapkan:**

| Hipotesis | Kekuatan bukti awal | Cakupan | Bisa ditindaklanjuti | Total |
|---|---|---|---|---|
| H1 Kompensasi di bawah pasar | 4 (Sales Engineer & Planner 12–18% di bawah median pasar) | 2 | 3 | 9 |
| H2 Beban kerja & desain pekerjaan | 3 | 3 | 4 | 10 |
| H3 Kepemimpinan & jalur karier | 4 (62% yang keluar menyebut "tidak ada jenjang") | 3 | 4 | 11 |

> **Pangkas:** Uji H3 sebagai hipotesis utama dan H1 sebagai hipotesis kedua untuk Sales Engineer dan Planner. H2 ditunda karena hanya kuat untuk Field Service Technician dan membutuhkan data jam lembur yang belum tersedia.

**Tahap I — Implementasi dengan CoT (Extended Thinking aktif)**
```xml
<instruksi>
Uji hipotesis H3 (kepemimpinan & jalur karier) dan H1 (kompensasi) untuk ketiga posisi.
Pikirkan langkah demi langkah di dalam <thinking>:
1. Bandingkan attrition antara karyawan yang atasannya memiliki rentang kendali >12 orang
   dan ≤12 orang.
2. Bandingkan masa kerja saat keluar dengan waktu rata-rata menuju promosi di setiap posisi.
3. Hitung selisih kompensasi terhadap median pasar per posisi, lalu cek apakah karyawan yang
   keluar berada di kuartil kompensasi terbawah. Gunakan analysis tool untuk semua perhitungan.
4. Tandai setiap temuan sebagai FAKTA atau DUGAAN.
5. Hitung biaya attrition per posisi dengan asumsi biaya penggantian = 50% gaji tahunan
   (Sales Engineer & Planner) dan 30% (Technician). Nyatakan asumsi ini dengan jelas.
Tulis jawaban di <jawaban>: temuan utama per posisi, estimasi biaya, dan rencana tindakan
90 hari dengan pemilik dan indikator keberhasilan.
</instruksi>
```

**Kutipan hasil yang diharapkan:**
> `<jawaban>` **Kesimpulan: Attrition di ketiga posisi terutama didorong oleh tidak adanya jalur karier teknis (FAKTA untuk ketiga posisi), diperparah oleh kompensasi di bawah pasar untuk Sales Engineer dan Inventory Planner (FAKTA), dengan estimasi biaya attrition ±Rp 4,1 miliar per tahun (berbasis asumsi).**
> - **Technical Sales Engineer:** 70% yang keluar berada di masa kerja 2–3 tahun, tepat saat promosi pertama biasanya terjadi (rata-rata waktu menuju promosi 4,1 tahun)…
> - **Rencana 90 hari:** (1) rancang jalur karier ganda (*dual career ladder*: teknis dan manajerial) — pemilik: Head of Talent; (2) penyesuaian gaji terarah untuk 2 posisi — pemilik: Head of Reward, menunggu persetujuan CFO; (3) …

**Tahap V — Verifikasi (obrolan baru)**
```
[Tempel jawaban tahap I]
Berperanlah sebagai CFO yang skeptis. Hitung ulang estimasi biaya Rp 4,1 miliar dengan
analysis tool. Sebutkan 3 asumsi paling rapuh dan apa yang terjadi pada rekomendasi jika
asumsi itu salah. Jangan memperbaiki analisisnya, cukup tunjukkan kelemahannya.
```

**Kutipan hasil yang diharapkan:**
> **Kelemahan 1:** Asumsi biaya penggantian 50% gaji untuk Sales Engineer belum memasukkan hilangnya pendapatan dari pelanggan yang ikut berpindah, sehingga biaya kemungkinan **lebih besar**, bukan lebih kecil…
> **Kelemahan 2:** Korelasi rentang kendali >12 dengan attrition bisa dipengaruhi faktor wilayah, karena tim besar terkonsentrasi di Kawasan Industri Cikarang tempat pesaing paling agresif merekrut. **Perlu pemisahan data per wilayah sebelum disimpulkan.**
> **Kelemahan 3:** …

**Pelajaran:** **ToT** mencegah tim langsung menyimpulkan "masalahnya gaji", yaitu jawaban yang paling umum tetapi hanya menjelaskan sebagian. **CoT** membuat setiap temuan dapat dipertanggungjawabkan dengan bukti dan asumsi yang terlihat. **Verifikasi** menemukan faktor pengganggu (wilayah) yang bisa membuat direksi mengambil keputusan yang salah. Keputusan akhir, terutama penyesuaian gaji, tetap ada di tangan CHRO, CFO, dan direksi.

> **Catatan fasilitator:** Tekankan bahwa penyesuaian gaji adalah **keputusan kompensasi yang menyangkut keadilan internal**. AI boleh menghitung kesenjangan, tetapi tidak boleh memutuskan siapa yang naik gaji dan berapa besarnya.

### Studi Kasus K — Perencanaan Tenaga Kerja Strategis 2030 (ToT Skenario)
**Situasi:** *PT Lintas Cepat Logistik (fiktif)* menyusun rencana tenaga kerja 2030. Direksi bertanya: *"Berapa staf gudang yang kita butuhkan jika otomasi gudang dan pertumbuhan e-commerce sama-sama tidak pasti?"*

**✅ *Prompt* ToT skenario:**
```
Konteks: PT Lintas Cepat Logistik, 6 gudang, 900 picker/packer, 120 supervisor gudang, 2026.

1. Gunakan dua ketidakpastian utama: (X) laju adopsi otomasi gudang (lambat/cepat) dan
   (Y) pertumbuhan volume e-commerce (rendah/tinggi). Silangkan menjadi 4 skenario 2030
   dan beri nama yang mudah diingat.
2. Untuk setiap skenario, pikirkan langkah demi langkah: perkiraan volume, kebutuhan
   picker/packer, peran baru yang muncul (misalnya teknisi robot, analis WMS),
   peran yang menyusut, dan kesenjangan kapabilitas.
3. Klasifikasikan langkah HR menjadi:
   - No-regret moves (bermanfaat di semua skenario),
   - Opsi strategis (bermanfaat di 2–3 skenario),
   - Signposts (indikator yang perlu dipantau setiap kuartal).
4. Untuk peran yang menyusut, usulkan jalur reskilling dan redeployment, bukan PHK
   sebagai opsi pertama.
Format: matriks 2×2 skenario, tabel kebutuhan tenaga kerja per skenario, lalu tiga daftar
langkah. Nyatakan semua asumsi angka.
```

**Kutipan hasil yang diharapkan:**
> **No-regret moves:** (1) Program sertifikasi "operator gudang digital" untuk 200 picker dengan kinerja terbaik mulai 2027 — dibutuhkan di keempat skenario; (2) memetakan keterampilan seluruh supervisor gudang…
> **Signposts:** biaya per unit robot *picking* turun di bawah ambang tertentu; volume paket per hari melampaui kapasitas manual 2 kuartal berturut-turut…

**Pelajaran:** ToT skenario mengubah pertanyaan direksi dari **"berapa angka pastinya?"** (yang tidak bisa dijawab dengan jujur) menjadi **"langkah apa yang aman diambil sekarang, dan sinyal apa yang kita tunggu?"**. Instruksi nomor 4 memastikan dimensi manusia dan hubungan industrial ikut dipertimbangkan sejak awal.

> **Catatan tata kelola:** Rencana yang menyentuh pengurangan peran wajib melibatkan HR, Legal, dan IR sebelum dikomunikasikan. Hasil AI adalah **bahan diskusi strategis**, bukan rencana restrukturisasi.

### Tahap Akhir — Simpan ke Pustaka *Prompt*

| Kolom | Isi |
|---|---|
| **Nama & ID** | `HR-STR-007 Diagnosis Attrition Posisi Kritis (Siklus RIV)` |
| **Versi** | v1.0 — 16/10/2026 |
| **Pemilik** | Head of People Analytics |
| **Teknik** | ToT (CNP) → CoT (4T) + Extended Thinking → Verifikasi (*self-critique*) |
| **Variabel** | `{{daftar_posisi}}`, `{{data_attrition}}`, `{{data_kompensasi}}`, `{{target_attrition}}`, `{{asumsi_biaya_penggantian}}` |
| **Platform diuji** | Claude ✅ (Extended Thinking + *analysis tool*) · ChatGPT ✅ (mode *reasoning*) · Gemini ✅ (*Thinking*) |
| **Risiko & tata kelola** | Hanya data agregat/anonim. Temuan kompensasi wajib ditinjau Head of Reward. Rekomendasi yang memengaruhi gaji, promosi, atau struktur organisasi diputuskan oleh manusia dan dicatat alasannya. |

### 🗣️ Catatan Fasilitator — Bab 2.3
- **Praktik utama (40 menit):** Dalam kelompok, peserta menjalankan Siklus RIV lengkap pada Studi Kasus J memakai data sintetis yang disediakan fasilitator. Setiap kelompok mempresentasikan: hipotesis yang dipangkas, satu temuan FAKTA, satu DUGAAN, dan kelemahan terbesar yang ditemukan di tahap verifikasi.
- **Variasi:** Dataset sintetis dari **Modul 4** (500 karyawan dengan pola *attrition* tersembunyi) bisa dipakai sebagai lanjutan latihan ini.
- **Pertanyaan diskusi:** *"Kapan mode berpikir justru membuang waktu dan biaya? Tugas apa yang cukup dengan prompt biasa?"* dan *"Pada tahap mana dalam Siklus RIV manusia paling tidak boleh absen?"*

---

## Rangkuman Modul 2

| Bab | Formula/Kerangka | Satu kalimat inti |
|---|---|---|
| **2.1 Fondasi** | **4T** (Tetapkan, Tahapkan, Tunjukkan, Tarik) + matriks CoT manual vs mode berpikir | Beri AI "kertas coretan" untuk masalah berlapis, dan pisahkan fakta dari dugaan. |
| **2.2 Penguatan** | **CNP** (Cabangkan, Nilai, Pangkas) + Pustaka Sudut Cabang + Research | Untuk masalah dengan banyak jawaban, jelajahi beberapa cabang dengan kriteria yang ditetapkan sebelum melihat opsi. |
| **2.3 Penguasaan** | **Siklus RIV** (Rancang–ToT, Implementasi–CoT, Verifikasi) + Kerangka Skenario | Rancang dengan ToT, buktikan dengan CoT, uji dengan kritik, dan biarkan manusia yang memutuskan. |

## Kuis Singkat (Kunci Jawaban untuk Fasilitator)

1. **Mengapa CoT meningkatkan akurasi LLM?** → *Karena LLM menghasilkan token secara berurutan; langkah penalaran yang ditulis lebih dulu menjadi konteks bagi jawaban akhir.*
2. **Apa beda CoT manual dan Extended Thinking?** → *CoT manual: Anda menulis langkah berpikir di prompt (tag `<thinking>`). Extended Thinking: mode bawaan model untuk bernalar lebih dalam sebelum menjawab, tanpa harus menulis langkah rinci.*
3. **Unsur 4T mana yang mencegah dugaan dilaporkan sebagai fakta?** → *T3 – Tunjukkan bukti (pemisahan FAKTA dan DUGAAN).*
4. **Kapan kriteria penilaian ToT harus ditetapkan?** → *Sebelum melihat opsi, untuk mencegah bias.*
5. **Apa tiga jebakan ToT?** → *Cabang kembar, kriteria kabur, dan skor palsu.*
6. **Dalam Siklus RIV, teknik apa dipakai di tiap tahap?** → *Rancang: ToT; Implementasi: CoT; Verifikasi: self-critique, cek angka, dan review manusia.*
7. **Mengapa *self-critique* sebaiknya dijalankan di obrolan baru?** → *Agar AI tidak terpengaruh konteks sebelumnya dan cenderung "membela" jawabannya sendiri.*
8. **Bolehkah teks penalaran AI dipakai sebagai justifikasi resmi keputusan rekrutmen?** → *Tidak. Penalaran yang ditampilkan belum tentu mencerminkan proses internal model; keputusan harus berbasis data terverifikasi dan alasan dari pengambil keputusan manusia.*

## Tugas Portofolio (Masuk Penilaian 30%)
Kumpulkan **3 Kartu Pustaka *Prompt*** dari pekerjaan Anda sendiri (dengan data sintetis):
- 1 *prompt* CoT dengan Formula 4T (analisis data atau ekstraksi dokumen),
- 1 *prompt* ToT dengan Formula CNP, lengkap dengan kriteria dan bobot,
- 1 rangkaian Siklus RIV (minimal 3 *prompt* berantai) untuk satu masalah bisnis, termasuk hasil tahap verifikasi.

Setiap kartu wajib menyertakan **versi sebelum dan sesudah**, catatan pengujian di minimal dua platform, serta **satu kelemahan yang ditemukan saat verifikasi** dan cara Anda menanganinya.

---
> **Catatan tata kelola:** Semua nama perusahaan dan data dalam modul ini fiktif atau sintetis. Angka biaya dan tolok ukur adalah **asumsi ilustratif** untuk latihan. Dalam praktik nyata, pastikan penggunaan AI dengan data karyawan mengikuti kebijakan perusahaan dan **UU Pelindungan Data Pribadi (UU PDP)**, serta keputusan tentang rekrutmen, kompensasi, promosi, dan struktur organisasi tetap diambil dan dipertanggungjawabkan oleh manusia.

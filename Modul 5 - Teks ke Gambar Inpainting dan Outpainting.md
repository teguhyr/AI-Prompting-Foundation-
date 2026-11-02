# Modul 5 — Teks-ke-Gambar: *Inpainting* dan *Outpainting*
### Materi Pelatihan · Kurikulum Pelatihan Prompting AI

---

## Pengantar Modul

**Ide pokok modul:** Gambar AI yang bagus tidak lahir dari *prompt* "buatkan poster lowongan". Gambar itu lahir dari ***brief* visual yang presisi**, **pengeditan bertahap** (*inpainting* dan *outpainting*), dan **ulasan kritis** sebelum dipublikasikan. Dalam alur ini, Claude berperan sebagai ***art director*** yang menerjemahkan *brief* menjadi *prompt* visual dan mengulas hasil gambar. Pembuatan gambarnya sendiri dilakukan di alat seperti ChatGPT, Gemini, Midjourney, atau Adobe Firefly. Di HR, taruhannya bukan sekadar estetika. Gambar *employer branding* adalah **janji kepada calon karyawan**, sehingga harus autentik, aman, inklusif, dan sesuai brand.

### Tujuan Pembelajaran
Setelah menyelesaikan modul ini, peserta mampu:
1. Menjelaskan cara kerja dan kegunaan teks-ke-gambar, membandingkan platform utama secara netral, dan memakai Claude sebagai ***art director*** untuk menyusun *prompt* visual dengan **Formula SKETSA**.
2. Mengedit gambar dengan ***inpainting*** dan memperluasnya dengan ***outpainting*** memakai **Formula 3T** (Tandai, Tentukan, Tahan), lalu mengasah hasil secara iteratif dengan bantuan **kemampuan *vision*** Claude dan **Rubrik Ulasan Visual**.
3. Menggabungkan *inpainting* dan *outpainting* menjadi **narasi visual kampanye** yang konsisten dengan **Kartu Gaya Visual** perusahaan, lalu mengalirkannya ke blog, presentasi, dan video.
4. Menerapkan **tata kelola konten visual AI**: hak cipta, label "dibuat dengan AI", representasi yang inklusif, keselamatan kerja di gambar, dan larangan meniru orang atau merek nyata.

### Agenda Sesi (±6 jam)

| Waktu | Bab | Aktivitas |
|---|---|---|
| 0:00–0:15 | Pembuka | *Ice breaker*: "Tebak mana foto asli, mana gambar AI" |
| 0:15–1:30 | **Bab 5.1** Fondasi | Cara kerja teks-ke-gambar, peta platform, Formula SKETSA, Claude sebagai *art director* |
| 1:30–1:45 | Rehat | — |
| 1:45–3:45 | **Bab 5.2** Penguatan | *Inpainting*, *outpainting*, Formula 3T, Rubrik Ulasan Visual, praktik APD & banner |
| 3:45–4:30 | Rehat & makan siang | — |
| 4:30–5:45 | **Bab 5.3** Penguasaan | Narasi visual, Kartu Gaya Visual, produksi konten menyeluruh, praktik utama |
| 5:45–6:00 | Penutup | Kuis singkat & refleksi |

> **Persiapan peserta:** akun Claude.ai (wajib, untuk menyusun *prompt* dan mengulas gambar), ditambah **minimal satu alat pembuat gambar** yang disetujui perusahaan: pembuat gambar di ChatGPT, Gemini, Midjourney, Adobe Firefly/Photoshop, atau Canva. Siapkan pedoman brand perusahaan (fiktif disediakan fasilitator).

> **Catatan platform:** Claude **tidak membuat gambar**. Claude kuat untuk **menyusun *prompt* visual**, membuat **diagram dan ilustrasi berbasis kode** (SVG di Artifacts), serta **mengulas gambar** yang diunggah. Nama fitur, batas kuota, dan lisensi komersial setiap alat pembuat gambar berubah cepat. Fasilitator wajib mengecek ulang sebelum sesi.

> **Aturan sesi:** jangan mengunggah foto karyawan, kandidat, atau orang lain **tanpa persetujuan tertulis**. Semua contoh menggunakan gambar buatan AI atau foto stok berlisensi.

---

# BAB 5.1 — Fondasi: Alat AI untuk Tujuan Kreatif

## 5.1.1 Overview Konsep

### a. Bagaimana teks-ke-gambar bekerja?
Sebagian besar model gambar modern dilatih dengan pasangan **gambar dan deskripsi teks** dalam jumlah sangat besar. Saat diberi *prompt*, model menyusun gambar yang paling sesuai dengan deskripsi tersebut. Banyak model melakukannya melalui proses **difusi**: berangkat dari "noise" acak, lalu menyempurnakan gambar sedikit demi sedikit sesuai *prompt*.

Akibat praktisnya:
- **Model tidak "memahami" perusahaan Anda.** Ia menggambar rata-rata visual dari kata yang Anda tulis. "Gudang logistik" akan menghasilkan gambar gudang generik ala katalog luar negeri, kecuali Anda menjelaskan konteks Indonesia.
- **Kata yang tidak ditulis akan diisi tebakan model.** Jika Anda tidak menyebut APD, pekerja bisa digambar tanpa helm. Jika Anda tidak menyebut keragaman, model cenderung mengulang stereotip.
- **Hasil bervariasi setiap kali dijalankan.** Inilah alasan pengeditan dan iterasi diperlukan.

> **Analogi kunci:** Alat pembuat gambar adalah **fotografer dan ilustrator super cepat yang belum pernah datang ke kantor Anda**. Claude adalah ***art director*** yang menulis *shot list* rinci untuknya. Anda adalah **klien** yang menyetujui hasil akhir.

### b. Peta platform teks-ke-gambar

| Platform | Kekuatan umum | Fitur edit | Catatan untuk HR |
|---|---|---|---|
| **Pembuat gambar ChatGPT** (OpenAI) | Mengikuti instruksi panjang, edit lewat percakapan, cukup baik menulis teks dalam gambar | Edit percakapan; pilih area untuk diedit | Mudah untuk pemula |
| **Gemini** (Google, keluarga Imagen dan model gambar Gemini) | Edit lewat percakapan, terintegrasi dengan Google Workspace | Edit percakapan | Cocok untuk organisasi berbasis Google |
| **Midjourney** | Kualitas estetika tinggi, kendali gaya | *Vary (Region)* untuk *inpainting*; *Zoom Out* / *Pan* untuk *outpainting*; parameter rasio aspek | Perlu memahami parameter |
| **Adobe Firefly / Photoshop** | Dirancang untuk penggunaan komersial, terintegrasi alur kerja desain | ***Generative Fill*** (*inpainting*), ***Generative Expand*** (*outpainting*) | Sering dipilih tim brand/desain; cek kebijakan lisensi |
| **Canva** | Mudah dipakai non-desainer, templat siap pakai | Fitur edit dan perluasan berbasis AI | Cocok untuk konten media sosial HR cepat |
| **Claude** (Anthropic) | ***Art director***: menyusun *prompt*, mengulas gambar (*vision*), membuat diagram/ilustrasi SVG di Artifacts | — (menyusun instruksi edit) | Tidak membuat gambar fotografis |

> **Prinsip netral platform:** pilih alat yang **sudah disetujui perusahaan** dan yang **ketentuan lisensinya mengizinkan penggunaan komersial**. Formula SKETSA berlaku di semua alat; yang berbeda hanya parameter teknisnya.

### c. Unsur visual dasar: bentuk, warna, tekstur
| Unsur | Pengaruh pada pesan | Contoh di *employer branding* |
|---|---|---|
| **Bentuk & garis** | Garis lurus dan geometris terasa modern, rapi, teknis; bentuk organik terasa hangat dan manusiawi | Lini otomasi pabrik vs momen tim berbincang |
| **Warna** | Membawa emosi dan identitas brand | Biru: tepercaya dan teknis; oranye: energik dan bersahabat |
| **Tekstur** | Membuat gambar terasa nyata atau ilustratif | Tekstur seragam kerja, logam, dan kardus gudang menambah kesan autentik |
| **Cahaya** | Menentukan suasana | Cahaya pagi alami terasa optimis; cahaya keras pabrik terasa realistis |

### d. Penerapan umum di HR dan bisnis
- **Rekrutmen:** poster lowongan, konten media sosial, banner portal karier.
- ***Employer branding*:** kampanye "hari kerja di perusahaan kami", visual EVP (*employee value proposition*).
- **Komunikasi internal:** ilustrasi pengumuman, poster K3, visual program kesejahteraan.
- **Pelatihan:** ilustrasi modul *e-learning*, ilustrasi skenario.
- **Pemasaran dan penjualan:** visual produk, materi pameran B2B.

## 5.1.2 Framework & Formula

### Formula SKETSA: Anatomi *Prompt* Visual

```
PROMPT VISUAL = Subjek + Komposisi + Estetika + Tata cahaya + Sentuhan warna & tekstur + Aspek rasio
```

| Unsur | Pertanyaan kunci | Contoh frasa |
|---|---|---|
| **S – Subjek** | Siapa/apa yang tampil, sedang melakukan apa, di mana? | "Seorang kasir perempuan berhijab berusia 20-an sedang melayani pelanggan dengan senyum di minimarket modern Indonesia" |
| **K – Komposisi** | Dari sudut mana, seberapa dekat, apa fokusnya, di mana ruang kosong? | "*Medium shot* setinggi mata, subjek di sepertiga kiri, ruang kosong di kanan untuk teks" |
| **E – Estetika** (gaya) | Foto, ilustrasi, 3D, atau gaya lain? | "Fotografi editorial dokumenter, natural, tidak terlihat seperti foto stok" |
| **T – Tata cahaya** | Sumber, arah, dan suasana cahaya? | "Cahaya alami siang dari jendela depan toko, lembut dan hangat" |
| **S – Sentuhan warna & tekstur** | Palet warna dan tekstur apa? | "Palet dominan merah dan putih sesuai brand, aksen kuning; tekstur seragam katun yang nyata" |
| **A – Aspek rasio** | Untuk kanal apa, ukuran berapa? | "Rasio 4:5 untuk *feed* Instagram" |

> **Unsur wajib kedelapan untuk HR: Kendala.** Tambahkan apa yang **harus** dan **tidak boleh** ada, misalnya: *"Semua pekerja memakai APD lengkap; tanpa logo merek lain; tanpa teks di dalam gambar."*

### Panduan Rasio Aspek per Kanal

| Kanal | Rasio umum | Catatan |
|---|---|---|
| Instagram *feed* | 4:5 atau 1:1 | Potret 4:5 mengambil ruang layar lebih besar |
| Instagram/TikTok *story*, *reels* | 9:16 | Jaga area aman atas dan bawah dari teks antarmuka |
| LinkedIn unggahan gambar | 1:1, 4:5, atau 1,91:1 | Lanskap untuk artikel dan tautan |
| Banner situs/portal karier | 16:9 atau lebih lebar | Biasanya hasil ***outpainting*** dari gambar utama |
| Poster cetak A4/A3 | ±1:1,41 (≈ 5:7) | Pastikan resolusi cukup untuk cetak |

### Alur *Art Director*: dari *Brief* ke *Prompt*

```
Brief kampanye → Claude menyusun 3–5 konsep visual → Anda memilih → Claude menulis prompt SKETSA
→ Alat gambar membuat gambar → Claude mengulas gambar (vision) → Claude memperbaiki prompt / instruksi edit
```

## 5.1.3 How To — Menyusun *Prompt* Visual dengan Claude

**Langkah 1 — Tulis *brief* kampanye singkat:** tujuan, audiens, pesan inti, kanal, dan pedoman brand.

**Langkah 2 — Minta Claude menjadi *art director*:**
```
Anda adalah art director untuk employer branding perusahaan Indonesia.
Dari brief berikut, usulkan 3 konsep visual yang berbeda. Untuk setiap konsep,
tulis prompt gambar dengan Formula SKETSA (Subjek, Komposisi, Estetika, Tata cahaya,
Sentuhan warna & tekstur, Aspek rasio) ditambah Kendala. Tulis prompt dalam bahasa
Inggris untuk alat gambar, dan sertakan terjemahan ringkas dalam bahasa Indonesia.
[brief]
```

**Langkah 3 — Pilih konsep**, lalu salin *prompt* ke alat gambar yang disetujui.

**Langkah 4 — Buat 2–4 variasi** dan pilih yang paling mendekati.

**Langkah 5 — Unggah hasil ke Claude untuk diulas** (lihat Rubrik Ulasan Visual di Bab 5.2), lalu minta *prompt* atau instruksi edit yang lebih baik.

**Langkah 6 — Simpan *prompt* yang berhasil** di Pustaka *Prompt* (Modul 1), lengkap dengan nama alat dan pengaturannya.

> **Tips:** Banyak alat gambar menghasilkan gambar lebih akurat dengan *prompt* berbahasa Inggris. Claude dapat menulis *prompt* dalam bahasa Inggris dari *brief* berbahasa Indonesia, sambil tetap menjaga detail konteks lokal seperti hijab, seragam minimarket, dan suasana gudang di Indonesia.

## 5.1.4 Studi Kasus & Contoh

### Studi Kasus V — Poster Lowongan Kasir dan Pramuniaga (Ritel)
**Situasi:** *PT Sinar Ritel Nusantara (fiktif)* membuka 150 lowongan kasir dan pramuniaga untuk toko baru di Jawa Barat. Poster lama memakai foto stok orang berjas di kantor, yang sama sekali tidak menggambarkan pekerjaan di toko (lanjutan Studi Kasus A di Modul 1).

**❌ *Prompt* sebelum:**
```
Gambar poster lowongan kerja minimarket yang menarik.
```
**Hasil tipikal:** gambar generik dengan toko ala luar negeri, model yang terlihat seperti foto stok, teks palsu yang tidak terbaca di dalam gambar, dan tidak ada ruang untuk informasi lowongan.

**✅ *Prompt* sesudah (disusun Claude dengan Formula SKETSA):**
```
[S] A young Indonesian female cashier wearing a hijab and a red-and-white store uniform,
    smiling while handing a receipt to a customer, inside a clean, modern Indonesian
    neighborhood minimarket.
[K] Medium shot at eye level, subject on the left third, blurred shelves in the background,
    clear empty space on the right side for text.
[E] Natural documentary-style editorial photography, authentic, candid, not stock-photo-like.
[T] Soft, warm late-morning daylight from the storefront windows.
[S] Dominant red and white brand palette with yellow accents; realistic fabric texture.
[A] Aspect ratio 4:5.
[Kendala] No text or letters in the image, no real brand logos, natural hands and faces.
```

**Kutipan ulasan Claude terhadap hasil pertama (dengan *vision*):**
> **Sesuai brief:** komposisi dan ruang kosong untuk teks sudah tepat. **Perlu perbaikan:** (1) produk di rak memuat kemasan yang mirip merek nyata, sehingga tambahkan *"generic unbranded packaging"*; (2) tangan kanan kasir memiliki jari berlebih, sehingga perbaiki dengan *inpainting* pada area tangan; (3) pelanggan semuanya tampak berusia sama, sehingga tambahkan pelanggan lanjut usia agar lebih representatif.

**Pelajaran:** Unsur **Komposisi** (ruang kosong untuk teks) membuat gambar langsung bisa dipakai desainer. **Kendala** "tanpa teks" mencegah tulisan palsu yang sering muncul di gambar AI. Teks lowongan sebaiknya ditambahkan di **alat desain**, bukan dibuat oleh model gambar, agar ejaan dan informasinya akurat. Ulasan Claude menemukan masalah yang sering terlewat mata: **merek tiruan, cacat anatomi, dan kurangnya keragaman**.

### 🗣️ Catatan Fasilitator — Bab 5.1
- **Latihan (25 menit):** Peserta menulis satu *brief* rekrutmen, meminta Claude membuat 3 konsep dengan Formula SKETSA, lalu membuat gambar di alat pilihan. Bandingkan hasil *prompt* "satu kalimat" dengan *prompt* SKETSA.
- **Pertanyaan diskusi:** *"Unsur SKETSA mana yang paling menentukan apakah gambar terasa 'Indonesia' dan 'perusahaan kita', bukan foto stok generik?"*

---

# BAB 5.2 — Penguatan: Praktik Kreatif dengan AI

## 5.2.1 Overview Konsep

### a. *Inpainting*: mengganti atau memperbaiki bagian gambar
***Inpainting*** adalah mengedit **area tertentu** di dalam gambar, sementara bagian lain tetap dipertahankan. Cara kerjanya: Anda **menandai area** (menyeleksi atau memberi *mask*), lalu memberi instruksi apa yang harus muncul di area tersebut. Model membuat ulang area itu agar menyatu dengan sekelilingnya.

| Kegunaan | Contoh HR |
|---|---|
| Memperbaiki cacat | Tangan berjari enam, wajah tidak wajar, teks rusak |
| Kepatuhan | Menambahkan APD yang hilang, mengganti seragam yang salah |
| Kesesuaian brand | Mengganti warna seragam sesuai brand, menghapus logo merek lain |
| Representasi | Mengganti atau menambahkan orang agar komposisi tim lebih beragam |
| Adaptasi lokal | Mengganti latar menjadi lokasi cabang tertentu |

### b. *Outpainting*: memperluas bidang gambar
***Outpainting*** adalah **memperluas kanvas** di luar batas gambar asli. Model "membayangkan" kelanjutan adegan ke arah yang Anda tentukan.

| Kegunaan | Contoh HR |
|---|---|
| Adaptasi format | Poster 4:5 diperluas menjadi banner 16:9 untuk portal karier |
| Ruang teks | Menambah area kosong di samping subjek untuk judul dan informasi lowongan |
| Narasi lebih luas | Menampilkan lebih banyak konteks: seluruh lini produksi, bukan hanya satu operator |

### c. Cara melakukannya di berbagai platform

| Platform | *Inpainting* | *Outpainting* |
|---|---|---|
| **ChatGPT** | Pilih area di gambar lalu tulis instruksi, atau jelaskan bagian yang diubah lewat percakapan | Minta perluasan atau rasio baru lewat percakapan |
| **Gemini** | Jelaskan bagian yang diubah lewat percakapan | Minta perluasan atau rasio baru lewat percakapan |
| **Midjourney** | *Vary (Region)* | *Zoom Out*, *Pan* |
| **Adobe Firefly / Photoshop** | ***Generative Fill*** pada area seleksi | ***Generative Expand*** dengan memperbesar kanvas |
| **Canva** | Fitur edit berbasis AI pada area yang dipilih | Fitur perluasan berbasis AI |

> **Catatan:** Edit lewat percakapan (tanpa seleksi area) lebih mudah, tetapi kadang ikut mengubah bagian lain gambar. Jika bagian lain harus **persis sama** (misalnya wajah tokoh dalam seri kampanye), gunakan alat yang mendukung **seleksi area**.

### d. Mengasah *prompt* secara iteratif
Gambar layak pakai jarang tercapai dalam satu percobaan. Iterasi yang efektif mengubah **satu hal setiap kali**, sehingga Anda tahu perubahan mana yang berdampak. Di sinilah **kemampuan *vision*** Claude berguna: Claude dapat mengulas gambar dengan kriteria yang konsisten dan menyarankan perubahan *prompt* yang spesifik.

## 5.2.2 Framework & Formula

### Formula 3T: Instruksi Edit Gambar

```
INSTRUKSI EDIT = Tandai + Tentukan + Tahan
```

| T | Makna | *Inpainting* | *Outpainting* |
|---|---|---|---|
| **T1 – Tandai** | Area mana yang diubah? | Seleksi area: "tangan kanan pekerja", "kepala operator kedua dari kiri" | Arah dan ukuran perluasan: "perluas ke kanan hingga rasio 16:9" |
| **T2 – Tentukan** | Apa yang harus muncul di area itu? | "Helm safety kuning dengan tali dagu terpasang" | "Lanjutan lorong rak gudang, dengan area dinding polos di kanan untuk teks" |
| **T3 – Tahan** | Apa yang **tidak boleh** berubah? | "Pertahankan wajah, ekspresi, arah cahaya, dan warna seragam" | "Pertahankan perspektif, arah cahaya, dan gaya foto; jangan menambah orang baru" |

> **Kesalahan paling umum** adalah melupakan **T3 (Tahan)**. Tanpa T3, model bebas mengubah bagian lain, misalnya wajah tokoh berubah atau cahaya menjadi tidak konsisten.

### Rubrik Ulasan Visual (untuk Claude *Vision* dan Peninjau Manusia)

| Kriteria | Pertanyaan | Skor 1–3 |
|---|---|---|
| **1. Kesesuaian *brief*** | Apakah subjek, pesan, dan suasana sesuai *brief*? | 1 = jauh · 3 = tepat |
| **2. Anatomi & artefak** | Tangan, wajah, mata, teks palsu, benda yang menyatu tidak wajar? | 1 = banyak cacat · 3 = bersih |
| **3. Keselamatan kerja** | Apakah APD dan perilaku kerja yang ditampilkan aman dan sesuai SOP? | 1 = melanggar · 3 = patuh |
| **4. Representasi** | Apakah keragaman gender, usia, suku, dan disabilitas wajar dan tidak stereotip? | 1 = stereotip · 3 = inklusif |
| **5. Kesesuaian brand** | Warna, gaya, dan nuansa sesuai Kartu Gaya Visual? | 1 = tidak sesuai · 3 = sesuai |
| **6. Kelayakan publikasi** | Tidak ada merek lain, wajah mirip tokoh nyata, atau janji yang menyesatkan? | 1 = berisiko · 3 = aman |

**Kriteria layak tayang:** total ≥15 dari 18, dan **tidak ada skor 1** pada kriteria 3, 4, dan 6.

### Siklus Iterasi Visual

```
Buat → Ulas (Rubrik) → Pilih SATU perbaikan terpenting → Edit (3T) atau ubah prompt (SKETSA) → Ulas ulang
          ↑                                                                                    │
          └──────────────────────── berhenti jika layak tayang atau setelah 5 iterasi ────────┘
```

> Jika setelah 5 iterasi masih gagal, **kembali ke *brief***. Biasanya masalahnya ada pada konsep, bukan pada *prompt*.

## 5.2.3 How To — *Inpainting* dan *Outpainting* Langkah demi Langkah

### A. *Inpainting*
1. **Ulas gambar** di Claude dengan Rubrik Ulasan Visual. Minta Claude menunjuk **lokasi** setiap masalah, misalnya "pekerja ketiga dari kiri, area kepala".
2. **Minta instruksi edit 3T** dari Claude: *"Tulis instruksi inpainting dengan Formula 3T untuk masalah nomor 1, dalam bahasa Inggris."*
3. **Seleksi area** di alat gambar. Seleksi sedikit lebih luas daripada objeknya agar hasil menyatu.
4. **Jalankan edit** dengan instruksi T2 dan T3. Buat 2–3 variasi.
5. **Periksa batas area edit:** sambungan, bayangan, dan arah cahaya harus konsisten.
6. **Ulas ulang** dengan rubrik.

### B. *Outpainting*
1. **Tentukan format tujuan** (rasio dan kanal) sebelum memperluas.
2. **Rencanakan isi area baru:** apa yang muncul dan di mana ruang teks diletakkan.
3. **Perluas bertahap** (misalnya 25–50% setiap langkah) jika perluasannya besar, agar adegan tetap masuk akal.
4. **Gunakan T3:** pertahankan perspektif, cahaya, dan gaya; larang penambahan orang atau objek yang tidak diinginkan.
5. **Periksa area sambungan** antara gambar asli dan area baru, terutama garis lantai, rak, dan bayangan.

> **Tips Claude.ai:** Unggah gambar asli dan hasil edit **berdampingan**, lalu tanyakan: *"Apa yang berubah selain area yang saya minta? Apakah ada ketidakkonsistenan cahaya atau perspektif?"* Claude sering menemukan perubahan kecil yang tidak disadari.

## 5.2.4 Studi Kasus & Contoh

### Studi Kasus W — Menambahkan APD yang Hilang dengan *Inpainting* (Logistik)
**Situasi:** Tim *employer branding* *PT Lintas Cepat Logistik (fiktif)* membuat gambar AI untuk kampanye rekrutmen staf gudang. Gambarnya menarik: tiga pekerja tersenyum di depan rak dengan *forklift* di latar. Saat ditinjau oleh tim K3, ditemukan masalah serius: **dua pekerja tidak memakai helm dan rompi reflektif, dan satu pekerja berdiri di jalur *forklift***.

**Ulasan Claude dengan *vision* (Rubrik Ulasan Visual):**
> | Kriteria | Skor | Catatan |
> |---|---|---|
> | Kesesuaian *brief* | 3 | Suasana tim positif sesuai pesan |
> | Anatomi & artefak | 2 | Label pada rak berisi huruf acak |
> | **Keselamatan kerja** | **1** | Pekerja tengah dan kanan tanpa helm dan rompi reflektif; pekerja kiri berdiri di jalur *forklift* yang sedang bergerak |
> | Representasi | 3 | Komposisi gender dan usia beragam |
> | Kesesuaian brand | 2 | Rompi seharusnya oranye brand, bukan hijau |
> | Kelayakan publikasi | 2 | Menunggu perbaikan K3 |
>
> **Total 13/18 — tidak layak tayang** (skor 1 pada keselamatan kerja).

**✅ Instruksi *inpainting* (Formula 3T), disusun Claude:**
```
Edit 1 — [Tandai] Head and torso area of the middle and right workers.
         [Tentukan] Add yellow safety helmets with chin straps fastened and high-visibility
         orange reflective vests with silver reflective strips, worn correctly.
         [Tahan] Keep their faces, smiles, poses, skin tones, lighting direction, and background
         exactly the same.

Edit 2 — [Tandai] The floor area and the forklift behind the left worker.
         [Tentukan] Replace with a clearly marked yellow pedestrian walkway; the forklift is
         parked with its forks lowered, no one in its path.
         [Tahan] Keep the left worker's appearance and position, the shelving, and the lighting.

Edit 3 — [Tandai] The shelf labels.
         [Tentukan] Replace the random letters with blank, generic labels.
         [Tahan] Everything else unchanged.
```

**Hasil setelah edit:** skor keselamatan kerja naik menjadi 3, total 17/18, **layak tayang** setelah disetujui tim K3.

**Pelajaran:** Gambar AI **tidak memahami SOP keselamatan kerja**. Model menggambar pekerja gudang seperti yang paling sering ada di data latihnya, yang sering tanpa APD. Di HR, gambar yang melanggar K3 bukan hanya masalah estetika. Gambar itu **mengirim pesan buruk tentang budaya keselamatan** dan bisa menjadi masalah reputasi. Karena itu, kriteria keselamatan kerja di rubrik dibuat **tidak boleh bernilai 1**, dan tim K3 menjadi salah satu penyetuju.

### Studi Kasus X — Dari Poster 4:5 ke Banner 16:9 dengan *Outpainting* (Ritel)
**Situasi:** Poster kasir dari Studi Kasus V sudah disetujui untuk Instagram (4:5). Tim membutuhkan versi **banner 16:9** untuk portal karier dan **1,91:1** untuk LinkedIn, tanpa memotong subjek dan dengan ruang untuk judul lowongan.

**✅ Instruksi *outpainting* (Formula 3T):**
```
[Tandai] Extend the canvas to the right and slightly to the left to reach a 16:9 ratio.
[Tentukan] Continue the minimarket interior naturally: more shelves with generic unbranded
           products, a second checkout counter with an older male pramuniaga restocking,
           and a calm, softly blurred wall area on the right third for headline text.
[Tahan] Keep the original cashier, customer, lighting, color palette, camera perspective,
        and photographic style unchanged. No text, no logos.
```

**Langkah tambahan:** perluasan dilakukan dalam **dua tahap** (4:5 → 1:1 → 16:9) agar perspektif rak tetap masuk akal. Claude mengulas sambungan antara area asli dan area baru, lalu menemukan **garis rak yang patah** di tahap pertama. Masalah itu diperbaiki dengan *inpainting* kecil sebelum lanjut ke tahap kedua.

**Pelajaran:** *Outpainting* mengubah satu gambar yang disetujui menjadi **keluarga aset** untuk berbagai kanal, sehingga identitas visual kampanye tetap konsisten. Penambahan pramuniaga laki-laki yang lebih senior juga memperkuat pesan bahwa lowongan ini **terbuka untuk berbagai usia dan gender**.

### 🗣️ Catatan Fasilitator — Bab 5.2
- **Latihan (40 menit):** Fasilitator membagikan 3 gambar AI bermasalah (tanpa APD, tangan cacat, logo merek lain). Peserta mengulasnya dengan Claude memakai Rubrik Ulasan Visual, menyusun instruksi 3T, lalu memperbaikinya di alat gambar. Lanjutkan dengan memperluas satu gambar menjadi banner 16:9.
- **Pertanyaan diskusi:** *"Siapa yang wajib menyetujui gambar AI sebelum tayang di organisasi Anda: tim brand, K3, Legal, atau HR? Apa yang terjadi jika salah satunya dilewati?"*

---

# BAB 5.3 — Penguasaan: Menguasai AI Kreatif

## 5.3.1 Overview Konsep

### a. Dari gambar tunggal ke narasi visual
Kampanye yang kuat bercerita melalui **rangkaian gambar**, bukan satu gambar. Contohnya "satu hari seorang teknisi" dalam 4 panel, atau "perjalanan karier dari operator ke ahli otomasi" dalam 3 babak. Tantangan utamanya adalah **konsistensi**: tokoh, seragam, lokasi, cahaya, dan gaya harus tetap sama di setiap panel.

| Teknik | Fungsi dalam narasi |
|---|---|
| **Gambar utama** (*hero image*) | Menetapkan tokoh, gaya, dan palet |
| ***Inpainting*** | Mengubah ekspresi, aktivitas, atau atribut tokoh antarpanel tanpa mengubah identitasnya |
| ***Outpainting*** | Membuka adegan untuk memperlihatkan konteks baru atau menghubungkan panel menjadi panorama |
| **Referensi gaya / karakter** | Banyak alat menyediakan fitur referensi gambar agar gaya atau tokoh konsisten (cek fitur di alat masing-masing) |

### b. Pedoman brand untuk gambar AI
Model gambar tidak mengenal brand Anda. Konsistensi harus **ditulis** dalam bentuk yang dapat dibaca AI. Wujudnya adalah **Kartu Gaya Visual**, potongan teks baku yang selalu ditempel ke setiap *prompt*.

> **Logo dan teks brand:** jangan meminta model gambar membuat logo perusahaan. Model sering mengubah bentuk logo dan salah mengeja teks. **Tempatkan logo asli dan teks di alat desain** setelah gambar selesai.

### c. Produksi konten menyeluruh (*end-to-end*)

```
Brief kampanye (Claude: konsep + naskah)
   → Prompt visual SKETSA (Claude)
      → Gambar utama + edit 3T (alat gambar)
         → Ulasan rubrik (Claude vision + manusia)
            → Adaptasi kanal: outpainting & resize (alat gambar / desain)
               → Penempatan logo & teks (alat desain: Canva, Adobe, dll.)
                  → Turunan: artikel blog (Claude), slide presentasi, storyboard video (Modul 6)
                     → Persetujuan & label AI → Publikasi
```

### d. Tata kelola konten visual AI

| Aspek | Risiko | Praktik yang disarankan |
|---|---|---|
| **Hak cipta & lisensi** | Pemakaian komersial dilarang oleh ketentuan alat tertentu; gambar mirip karya berhak cipta | Gunakan alat dengan lisensi komersial yang jelas; jangan menulis *"in the style of [seniman hidup]"*; simpan *prompt* dan tanggal pembuatan sebagai bukti |
| **Meniru orang dan merek nyata** | Wajah mirip tokoh publik, karyawan, atau logo pesaing | Larang di Kendala *prompt*; periksa di Rubrik kriteria 6 |
| **Foto karyawan** | Mengedit foto karyawan tanpa izin melanggar privasi dan kepercayaan | Wajib **persetujuan tertulis** untuk memakai atau mengedit foto karyawan; jangan mengubah wajah, tubuh, atau atribut identitas mereka |
| **Transparansi** | Calon karyawan merasa tertipu jika gambar "terlalu indah" | Beri label *"Ilustrasi dibuat dengan bantuan AI"*; manfaatkan kredensial konten (misalnya standar C2PA) jika alat mendukung |
| **Autentisitas EVP** | Gambar menjanjikan fasilitas atau suasana yang tidak ada | Setiap gambar harus **bisa dibuktikan** di lapangan: "Apakah gudang kita memang seperti ini?" |
| **Representasi** | Stereotip: perempuan hanya di administrasi, laki-laki hanya di lapangan | Rancang keragaman secara sengaja dan wajar, termasuk disabilitas, dengan Rubrik kriteria 4 |
| **Keselamatan kerja** | Gambar menormalkan praktik tidak aman | Rubrik kriteria 3 wajib bernilai 3; tim K3 ikut menyetujui |

## 5.3.2 Framework & Formula

### Kartu Gaya Visual (Templat)

| Unsur | Isi | Contoh (*PT Mitra Teknik Industri*, fiktif) |
|---|---|---|
| **Kepribadian brand** | 3 kata sifat | Tepercaya, teknis, bersahabat |
| **Palet warna** | Warna utama, pendukung, aksen (kode HEX untuk desainer, nama warna untuk *prompt*) | Biru tua (#1F3A5F), abu-abu baja, aksen oranye (#F28C28) |
| **Gaya foto** | Jenis fotografi dan suasana | Fotografi dokumenter-editorial, natural, tidak dipentaskan |
| **Cahaya** | Arah dan suasana cahaya | Cahaya alami siang atau cahaya industri yang bersih dan terang |
| **Subjek & latar** | Siapa dan di mana | Teknisi dan *sales engineer* Indonesia di lokasi pelanggan industri, gudang suku cadang, dan bengkel servis |
| **Wajib ada** | Elemen keharusan | APD sesuai lokasi, seragam biru tua dengan aksen oranye, peralatan generik tanpa merek |
| **Dilarang** | Elemen terlarang | Logo merek lain, teks di dalam gambar, pose foto stok, pelanggaran K3 |
| **Potongan *prompt* baku** | Teks yang selalu ditempel ke *prompt* | *"Documentary editorial photography, natural light, navy blue and steel grey palette with orange accents, Indonesian industrial setting, generic unbranded equipment, correct PPE, no text, no logos."* |

### Formula Narasi Visual: 3 Babak

| Babak | Fungsi | Contoh (perjalanan karier) | Teknik |
|---|---|---|---|
| **Babak 1 – Awal** | Memperkenalkan tokoh dan dunianya | Operator muda belajar di lini produksi | Gambar utama (SKETSA + Kartu Gaya) |
| **Babak 2 – Tumbuh** | Menunjukkan proses, tantangan, dukungan | Tokoh dibimbing mentor saat pelatihan otomasi | *Inpainting* tokoh dan aktivitas; latar dipertahankan |
| **Babak 3 – Capaian** | Menunjukkan hasil dan janji EVP | Tokoh memimpin pemeliharaan sistem otomasi | *Outpainting* untuk memperlihatkan skala dan tim |

## 5.3.3 How To — Membangun Kampanye Visual yang Konsisten

**Langkah 1 — Susun Kartu Gaya Visual** bersama tim brand. Simpan sebagai *project knowledge* di **Claude Project** "Studio Visual HR" (lihat Modul 3), sehingga Claude otomatis memakainya setiap kali menyusun *prompt*.

**Langkah 2 — Tulis naskah narasi 3 babak** bersama Claude, lalu minta *prompt* SKETSA untuk setiap babak yang selalu menyertakan potongan *prompt* baku.

**Langkah 3 — Buat gambar utama** dan setujui dengan rubrik **sebelum** membuat babak berikutnya.

**Langkah 4 — Turunkan babak 2 dan 3** dari gambar utama memakai *inpainting*, *outpainting*, atau fitur referensi gambar agar tokoh dan gaya tetap konsisten.

**Langkah 5 — Uji konsistensi:** unggah ketiga gambar ke Claude dan tanyakan: *"Apakah tokoh, seragam, palet, dan gaya konsisten di ketiga gambar? Tunjukkan perbedaannya."*

**Langkah 6 — Adaptasi kanal** dengan *outpainting* dan tempatkan logo serta teks di alat desain.

**Langkah 7 — Buat turunan konten** dengan Claude: artikel blog, keterangan unggahan per kanal, *outline* slide presentasi, dan storyboard video untuk **Modul 6**.

**Langkah 8 — Persetujuan & dokumentasi:** brand, K3, Legal (bila perlu), dan HR menyetujui. Simpan *prompt*, alat, tanggal, dan label AI di Pustaka *Prompt*.

## 5.3.4 Studi Kasus & Contoh

### Studi Kasus Y — Seri LinkedIn "Satu Hari Technical Sales Engineer" (B2B Industri)
**Situasi:** *PT Mitra Teknik Industri (fiktif)* kesulitan merekrut **Technical Sales Engineer** (lanjutan Studi Kasus J di Modul 2, *attrition* 31%). Kandidat lulusan teknik membayangkan pekerjaan *sales* sebagai "jualan door-to-door", padahal pekerjaannya adalah konsultasi teknis di lokasi pelanggan industri.

**Desain kampanye:** seri 4 gambar di LinkedIn (rasio 4:5), satu tokoh yang sama:
1. Pagi: meninjau data teknis pelanggan bersama tim di kantor cabang.
2. Siang: berdiskusi dengan *plant engineer* pelanggan di lantai pabrik (APD lengkap).
3. Sore: mendemonstrasikan peralatan di bengkel servis.
4. Penutup: tim merayakan proyek yang berhasil dipasang.

***Prompt* babak 1 (disusun Claude dari Kartu Gaya Visual):**
```
[S] An Indonesian male technical sales engineer in his late 20s, navy blue polo shirt with
    an orange accent, reviewing technical drawings on a laptop with two colleagues
    (one woman in her 40s, one young man) in a modern branch office.
[K] Medium-wide shot, slightly above eye level, subject in the center-left, whiteboard with
    abstract diagrams in the background (no readable text).
[E][T][S] Documentary editorial photography, natural light, navy blue and steel grey palette
    with orange accents, Indonesian industrial setting, generic unbranded equipment,
    correct PPE, no text, no logos.
[A] 4:5.
```

**Ulasan konsistensi Claude setelah 4 gambar dibuat:**
> Tokoh konsisten pada panel 1, 3, dan 4. **Panel 2:** wajah tokoh berbeda (rahang lebih lebar, rambut lebih panjang), dan seragam berubah menjadi biru muda. **Saran:** buat ulang panel 2 dengan fitur referensi karakter dari panel 1, atau *inpainting* area wajah dan seragam dengan instruksi T3 *"keep the factory background and the plant engineer unchanged"*.

**Pelajaran:** Konsistensi tokoh adalah tantangan terbesar narasi visual AI. **Kartu Gaya Visual** menjaga konsistensi gaya, sedangkan **ulasan konsistensi** oleh Claude menangkap perubahan tokoh yang sering luput. Kampanye ini juga menjawab akar masalah rekrutmen: **mengoreksi persepsi pekerjaan** dengan gambaran hari kerja yang realistis, bukan sekadar menarik perhatian.

> **Catatan tata kelola:** Jika seri ini kelak memakai **foto karyawan asli**, seperti tim *sales* sungguhan yang diedit dengan *inpainting*, diperlukan persetujuan tertulis dari setiap orang di foto, dan edit tidak boleh mengubah wajah atau identitas mereka.

### Studi Kasus Z — Kampanye "Dari Operator ke Ahli Otomasi" (Praktik Utama Modul)
**Situasi:** *PT Baja Prima Manufaktur (fiktif)* memilih konsep **"Dari Operator ke Ahli Otomasi"** untuk menarik lulusan SMK teknik dan D3 (hasil ToT di Studi Kasus I, Modul 2). Tim HR harus menghasilkan aset kampanye untuk Instagram, LinkedIn, portal karier, dan presentasi *job fair* di SMK dalam 2 minggu.

**Tahap 1 — Claude menyusun 5 *prompt* visual dari satu *brief***
```
Anda adalah art director employer branding. Dari brief berikut, susun 5 prompt visual
dengan Formula SKETSA + Kendala, memakai Kartu Gaya Visual PT Baja Prima Manufaktur
yang ada di project knowledge:
1. Gambar utama (hero) kampanye
2–4. Narasi 3 babak: operator muda belajar → dibimbing mentor → memimpin pemeliharaan robot
5. Visual komunitas: kelas industri bersama siswa SMK di pabrik

Brief: kampanye untuk lulusan SMK teknik dan D3 (usia 18–23). Pesan inti: pabrik kami
modern, aman, dan punya jalur karier nyata dari operator ke teknisi otomasi. Semua
pekerja memakai APD lengkap sesuai area. Tampilkan keragaman gender secara wajar
(perempuan juga sebagai operator dan teknisi). Tidak ada teks dan logo di gambar.
Tulis prompt dalam bahasa Inggris dan sertakan ringkasan bahasa Indonesia.
```

**Kutipan hasil yang diharapkan (*prompt* nomor 4):**
> *"[S] A young Indonesian female automation technician in her early 20s, wearing a hard hat, safety glasses, and the navy-and-orange company uniform, leading two junior operators during maintenance of an industrial robotic arm on a clean, well-lit production line. [K] Medium-wide shot at eye level, technician in the center, robot arm forming a leading line toward her, empty space at the top for text. [E] Documentary editorial photography… [A] 4:5. [Kendala] Correct PPE for all people, safety barrier around the robot visible, no text, no logos."*
>
> **Ringkasan:** Teknisi otomasi perempuan muda memimpin dua operator junior dalam perawatan lengan robot; semua memakai APD lengkap dan pagar pengaman robot terlihat.

**Tahap 2 — Produksi dan edit**
- Gambar dibuat di alat gambar yang disetujui, lalu setiap gambar diulas dengan **Rubrik Ulasan Visual**.
- Masalah yang ditemukan dan diperbaiki dengan **3T**: kacamata keselamatan hilang di gambar 2, pagar pengaman robot tidak terlihat di gambar 4, dan wajah tokoh berubah di gambar 3.
- Gambar utama diperluas dengan ***outpainting*** menjadi banner portal karier 16:9 dan latar slide 16:9.

**Tahap 3 — Turunan konten (Claude)**
```
Dari 5 gambar yang sudah disetujui (terlampir) dan naskah kampanye, buatkan:
1. Keterangan unggahan Instagram (maks. 125 kata, nada santai Gen Z) dan LinkedIn
   (maks. 150 kata, nada profesional) untuk setiap gambar.
2. Artikel blog 500 kata "Dari Operator ke Ahli Otomasi: Jalur Karier di Pabrik Modern",
   dengan fakta jalur karier dari dokumen kebijakan pengembangan karier (project knowledge).
3. Outline 8 slide presentasi job fair SMK, dengan gambar mana dipakai di slide mana.
4. Storyboard video 30 detik dari 5 gambar ini untuk Modul 6.
Tandai setiap klaim yang perlu diverifikasi HR (misalnya lama waktu promosi).
```

**Tahap 4 — Persetujuan dan label**

| Penyetuju | Fokus |
|---|---|
| Tim Brand | Kesesuaian Kartu Gaya Visual, penempatan logo |
| Tim K3 | APD dan perilaku kerja di setiap gambar |
| HR Talent | Kebenaran klaim jalur karier di artikel dan keterangan unggahan |
| Legal/Komunikasi | Lisensi alat, label *"Ilustrasi dibuat dengan bantuan AI"* |

**Pelajaran:** Satu *brief* menghasilkan **paket kampanye lengkap**: 5 gambar inti, adaptasi multikanal, artikel, keterangan unggahan, slide, dan storyboard video. Konsistensinya dijaga oleh Kartu Gaya Visual, sedangkan keamanannya dijaga oleh rubrik dan persetujuan berlapis. Pesan "jalur karier nyata" hanya bisa dipertanggungjawabkan jika **HR Talent memverifikasi klaimnya**. Gambar AI boleh ilustratif, tetapi janji EVP harus benar.

### Tahap Akhir — Simpan ke Pustaka *Prompt*

| Kolom | Isi |
|---|---|
| **Nama & ID** | `HR-VIS-001 Prompt Visual Employer Branding (SKETSA + Kartu Gaya)` |
| **Versi** | v1.0 — 16/10/2026 |
| **Pemilik** | Employer Branding Lead (bersama tim Brand) |
| **Teknik** | Formula SKETSA + Kendala + Kartu Gaya Visual + Formula 3T + Rubrik Ulasan Visual |
| **Variabel** | `{{subjek_dan_aktivitas}}`, `{{lokasi}}`, `{{kanal_dan_rasio}}`, `{{potongan_prompt_brand}}`, `{{APD_wajib}}` |
| **Platform diuji** | Claude ✅ (penyusun *prompt* & ulasan *vision*) · Pembuat gambar ChatGPT ✅ · Gemini ✅ · Adobe Firefly ✅ (*Generative Fill/Expand*) · Midjourney ⚠️ (parameter berbeda) |
| **Risiko & tata kelola** | Tanpa foto karyawan kecuali ada persetujuan tertulis. Rubrik kriteria 3, 4, 6 tidak boleh bernilai 1. Persetujuan Brand + K3 + HR sebelum tayang. Label "Ilustrasi dibuat dengan bantuan AI". Simpan *prompt*, alat, dan tanggal pembuatan. |

### 🗣️ Catatan Fasilitator — Bab 5.3
- **Praktik utama (45 menit):** Dalam kelompok, peserta menjalankan Studi Kasus Z untuk perusahaan fiktif pilihan mereka. Claude menyusun 5 *prompt* visual dari satu *brief employer branding*, lalu peserta membuat, mengulas, dan mengedit gambarnya di alat pilihan, serta memperluas satu gambar menjadi banner 16:9. Presentasikan gambar sebelum dan sesudah edit beserta skor rubriknya.
- **Variasi lanjutan:** Kelompok yang selesai lebih dulu menyusun storyboard video 30 detik sebagai jembatan ke **Modul 6**.
- **Pertanyaan diskusi:** *"Bagaimana menjaga gambar AI tetap autentik dan tidak terlihat 'stock photo generik'?"* dan *"Kapan sebaiknya kita memakai foto karyawan asli, bukan gambar AI?"*

---

## Rangkuman Modul 5

| Bab | Formula/Kerangka | Satu kalimat inti |
|---|---|---|
| **5.1 Fondasi** | **Formula SKETSA** (Subjek, Komposisi, Estetika, Tata cahaya, Sentuhan warna & tekstur, Aspek rasio) + Kendala + Alur *Art Director* | Model gambar mengisi semua yang tidak Anda tulis dengan tebakan, jadi tulis *brief* visual selengkap *brief* untuk fotografer. |
| **5.2 Penguatan** | **Formula 3T** (Tandai, Tentukan, Tahan) + **Rubrik Ulasan Visual** + Siklus Iterasi | Edit satu hal setiap kali, selalu sebutkan apa yang harus dipertahankan, dan ulas dengan kriteria yang sama. |
| **5.3 Penguasaan** | **Kartu Gaya Visual** + Narasi 3 Babak + produksi menyeluruh + tata kelola | Konsistensi brand harus ditulis, keamanan harus diulas berlapis, dan janji dalam gambar harus benar di lapangan. |

## Kuis Singkat (Kunci Jawaban untuk Fasilitator)

1. **Apakah Claude membuat gambar?** → *Tidak. Claude berperan sebagai art director: menyusun prompt visual, mengulas gambar dengan vision, dan membuat diagram/ilustrasi berbasis kode (SVG).*
2. **Sebutkan enam unsur Formula SKETSA.** → *Subjek, Komposisi, Estetika, Tata cahaya, Sentuhan warna & tekstur, Aspek rasio (ditambah Kendala).*
3. **Apa beda *inpainting* dan *outpainting*?** → *Inpainting mengedit area di dalam gambar; outpainting memperluas kanvas di luar batas gambar asli.*
4. **Unsur 3T mana yang paling sering dilupakan, dan apa akibatnya?** → *T3 – Tahan. Tanpa itu, model bebas mengubah bagian lain seperti wajah, cahaya, atau latar.*
5. **Mengapa teks dan logo sebaiknya ditambahkan di alat desain, bukan dibuat model gambar?** → *Model gambar sering salah mengeja teks dan mengubah bentuk logo.*
6. **Pada Rubrik Ulasan Visual, kriteria mana yang tidak boleh bernilai 1?** → *Keselamatan kerja, representasi, dan kelayakan publikasi.*
7. **Mengapa tidak boleh menulis "in the style of [nama seniman hidup]" di prompt?** → *Berisiko secara hak cipta dan etika karena meniru gaya khas seniman tanpa izin.*
8. **Apa syarat memakai atau mengedit foto karyawan asli dengan AI?** → *Persetujuan tertulis dari setiap orang di foto, dan edit tidak boleh mengubah wajah atau identitas mereka.*

## Tugas Portofolio (Masuk Penilaian 30%)
Kumpulkan **3 Kartu Pustaka *Prompt*** dari pekerjaan Anda sendiri (dengan perusahaan fiktif atau aset berlisensi):
- 1 *prompt* visual dengan **Formula SKETSA + Kendala**, lengkap dengan *brief*, gambar hasil, dan perbandingan dengan *prompt* "satu kalimat",
- 1 rangkaian **edit 3T** (minimal satu *inpainting* dan satu *outpainting*) dengan gambar sebelum–sesudah dan skor **Rubrik Ulasan Visual**,
- 1 **Kartu Gaya Visual** beserta minimal 3 gambar narasi visual yang konsisten dan satu turunan konten (keterangan unggahan, artikel, atau *outline* slide).

Setiap kartu wajib mencantumkan alat gambar yang dipakai, ketentuan lisensinya, dan label AI yang akan dipasang saat publikasi.

---
> **Catatan tata kelola:** Semua nama perusahaan dalam modul ini fiktif, dan semua gambar contoh harus dibuat dengan AI atau berasal dari sumber berlisensi. Dalam praktik nyata, gunakan alat pembuat gambar yang disetujui perusahaan dan mengizinkan penggunaan komersial, beri label pada konten yang dibuat dengan AI, jangan meniru orang, karya, atau merek nyata, minta persetujuan tertulis sebelum memakai atau mengedit foto karyawan, dan pastikan setiap gambar *employer branding* mencerminkan kondisi kerja yang sebenarnya, termasuk standar keselamatan kerja.

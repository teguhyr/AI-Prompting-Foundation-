# Modul Pilihan 6 — Pembuatan Video dengan AI (Teks-ke-Video)
### Materi Pelatihan · Kurikulum Pelatihan Prompting AI

---

## Pengantar Modul

**Ide pokok modul:** Video AI paling berguna di HR bukan untuk menggantikan produksi video profesional. Kegunaannya adalah membuat **video pendek yang cepat, konsisten, dan mudah diperbarui**, misalnya untuk *onboarding*, *microlearning*, dan komunikasi internal. Kualitasnya ditentukan **sebelum** alat video dibuka, yaitu pada **naskah, storyboard, dan *shot list*** yang disusun dengan Claude. Karena video AI dapat meniru wajah dan suara manusia, modul ini juga menempatkan **persetujuan, label AI, dan pencegahan *deepfake*** sebagai bagian inti proses, bukan tambahan.

### Tujuan Pembelajaran
Setelah menyelesaikan modul ini, peserta mampu:
1. Membedakan tiga kelompok alat video AI (generatif, avatar, dan perakit), mengenali batasannya, serta menyusun naskah dan storyboard dengan **Formula KIT** (Kait, Isi, Tindakan) dan *prompt* adegan dengan **Formula KAMERA**.
2. Mengintegrasikan elemen brand (logo, warna, *font*, musik) dengan **Kartu Gaya Video**, lalu menyesuaikan video untuk setiap kanal dengan **Matriks Adaptasi Kanal**.
3. Membuat video yang dipersonalisasi untuk audiens berbeda, video untuk acara dan komunikasi skala besar, serta mengintegrasikannya ke pengalaman interaktif seperti kuis dan modul *e-learning*.
4. Menerapkan tata kelola video AI: **persetujuan tertulis** untuk avatar wajah atau suara, label konten AI, verifikasi akurasi, dan pencegahan *deepfake*.

### Agenda Sesi (±3 jam, modul pilihan)

| Waktu | Bab | Aktivitas |
|---|---|---|
| 0:00–0:10 | Pembuka | *Ice breaker*: "Video *onboarding* terburuk yang pernah Anda tonton" |
| 0:10–0:55 | **Bab 6.1** Fondasi | Peta alat video AI, batasan, Formula KIT, Formula KAMERA, storyboard dengan Claude |
| 0:55–1:05 | Rehat | — |
| 1:05–2:05 | **Bab 6.2** Penguatan | Kartu Gaya Video, Matriks Adaptasi Kanal, praktik video *microlearning* & demo aplikasi |
| 2:05–2:50 | **Bab 6.3** Penguasaan | Personalisasi, video interaktif, tata kelola avatar, praktik utama |
| 2:50–3:00 | Penutup | Kuis singkat & refleksi |

> **Persiapan peserta:** akun Claude.ai (wajib, untuk naskah, storyboard, *prompt* adegan, dan ulasan), ditambah **minimal satu alat video AI** yang disetujui perusahaan (alat generatif, avatar, atau perakit seperti Canva). Bawa hasil **Studi Kasus Z (Modul 5)** jika sudah mengikuti modul tersebut; storyboard-nya akan dipakai di Bab 6.3.

> **Catatan platform:** Claude **tidak membuat video** dan tidak menonton berkas video secara langsung di obrolan biasa. Claude mengulas video melalui **tangkapan layar frame kunci** dan **transkrip**. Nama fitur, durasi klip, kuota kredit, dan lisensi komersial alat video berubah sangat cepat. Fasilitator wajib mengecek ulang sebelum sesi.

> **Aturan sesi:** jangan membuat avatar atau klon suara dari wajah atau suara siapa pun, termasuk diri sendiri, kecuali memakai fitur avatar bawaan alat atau sudah ada **persetujuan tertulis** sesuai kebijakan perusahaan.

---

# BAB 6.1 — Fondasi: Mengubah Kata Menjadi Visual

## 6.1.1 Overview Konsep

### a. Tiga kelompok alat video AI
Alat video AI sering dibicarakan seolah-olah satu kategori, padahal fungsinya sangat berbeda. Memilih kelompok yang salah adalah penyebab utama hasil yang mengecewakan.

| Kelompok                                | Cara kerja                                                                                       | Contoh platform                                                 | Cocok untuk                                              | Kurang cocok untuk                                             |
| --------------------------------------- | ------------------------------------------------------------------------------------------------ | --------------------------------------------------------------- | -------------------------------------------------------- | -------------------------------------------------------------- |
| **1. Generatif** (teks/gambar-ke-video) | Membuat klip baru dari *prompt* atau gambar awal                                                 | **Sora** (OpenAI), **Veo** (Google), **Runway**, dan sejenisnya | Klip suasana (*B-roll*), adegan pembuka, visual kampanye | Prosedur langkah demi langkah yang harus akurat, video panjang |
| **2. Avatar / presenter**               | Presenter digital membaca naskah, lengkap dengan gerak bibir                                     | **Synthesia**, **HeyGen**, dan sejenisnya                       | Video pelatihan, pengumuman, *microlearning* multibahasa | Emosi kompleks, adegan aksi                                    |
| **3. Perakit** (naskah/aset-ke-video)   | Menyusun video dari naskah, gambar, klip stok, rekaman layar, dan suara                          | **Pictory**, **Canva**, editor video dengan fitur AI            | Video media sosial, demo aplikasi, rangkuman materi      | Visual yang benar-benar baru dan unik                          |
| **Claude** (Anthropic)                  | Menulis naskah, storyboard, *shot list*, *prompt* adegan, subtitle; mengulas frame dan transkrip | —                                                               | Tahap pra-produksi dan kontrol mutu                      | Membuat video                                                  |

> **Analogi kunci:** Membuat video AI seperti memproduksi film kecil. **Claude adalah penulis naskah dan sutradara** yang menyiapkan storyboard. **Alat generatif** adalah kru kamera yang merekam adegan. **Alat avatar** adalah presenter. **Alat perakit** adalah editor di ruang *editing*. Anda adalah **produser** yang menyetujui hasil akhir.

### b. Batasan video AI yang perlu diketahui sejak awal

| Batasan                  | Gejala                                                                 | Dampak di HR                                 | Penawar                                                                                                     |
| ------------------------ | ---------------------------------------------------------------------- | -------------------------------------------- | ----------------------------------------------------------------------------------------------------------- |
| **Durasi klip pendek**   | Alat generatif umumnya menghasilkan klip berdurasi detik, bukan menit  | Video panjang harus dirakit dari banyak klip | Rencanakan adegan per klip di storyboard                                                                    |
| **Konsistensi karakter** | Wajah, seragam, atau lokasi berubah antarklip                          | Tokoh "berganti orang" di tengah video       | Gunakan gambar referensi (misalnya dari Modul 5) dan fitur referensi karakter jika tersedia                 |
| **Fisika & detail**      | Tangan, alat, kendaraan, atau teks bergerak tidak wajar                | Prosedur kerja terlihat salah atau berbahaya | Jangan pakai video generatif untuk mendemonstrasikan prosedur; gunakan rekaman nyata atau animasi sederhana |
| **Teks di dalam video**  | Tulisan pada papan, layar, atau seragam rusak                          | Informasi salah atau tidak terbaca           | Tambahkan teks di editor, bukan di *prompt*                                                                 |
| **Bahasa & gerak bibir** | Pelafalan istilah lokal atau gerak bibir bahasa Indonesia kurang alami | Kredibilitas turun di mata karyawan          | Uji pelafalan, tulis ejaan fonetis untuk istilah sulit                                                      |
| **Kendali & biaya**      | Hasil bervariasi, setiap percobaan memakai kredit                      | Biaya membengkak tanpa rencana               | Storyboard rinci sebelum *generate*                                                                         |

### c. Mengapa naskah dan storyboard adalah tahap terpenting?
Kesalahan di naskah akan terbawa ke semua klip. Memperbaiki naskah di Claude hanya butuh **satu menit**, sedangkan membuat ulang klip video menghabiskan **kredit dan waktu**. Karena itu, aturannya: **tidak ada *generate* sebelum storyboard disetujui**.

## 6.1.2 Framework & Formula

### Formula KIT: Struktur Naskah Video Pendek

```
NASKAH VIDEO = Kait + Isi + Tindakan
```

| Bagian | Fungsi | Durasi (video 30–60 detik) | Contoh untuk video *onboarding* |
|---|---|---|---|
| **K – Kait** | Menarik perhatian di detik awal | 0–3 detik | "Satu kebiasaan kecil ini menyelamatkan kurir kami setiap hari." |
| **I – Isi** | Menyampaikan 1 pesan inti dengan 2–3 poin pendukung | 3–50 detik | Tiga cek wajib sebelum berangkat: helm, rem, muatan |
| **T – Tindakan** | Apa yang harus dilakukan penonton setelah menonton | 50–60 detik | "Lakukan cek 3 langkah ini setiap pagi, lalu centang di aplikasi." |

> **Prinsip satu video, satu pesan:** jika naskah membutuhkan lebih dari 3 poin isi, pecah menjadi beberapa video. Ini juga prinsip dasar ***microlearning***.

### Formula KAMERA: *Prompt* Adegan Video

```
PROMPT ADEGAN = Karakter + Aksi + Medan + Efek kamera + Ritme + Atmosfer
```

| Unsur | Pertanyaan kunci | Contoh frasa |
|---|---|---|
| **K – Karakter** | Siapa yang tampil, seperti apa penampilannya? | "Seorang kurir laki-laki Indonesia berusia 20-an, jaket oranye perusahaan, helm *full-face* terpasang" |
| **A – Aksi** | Apa yang dilakukan, dari awal sampai akhir klip? | "Memeriksa tekanan ban, lalu menekan rem depan, lalu mengencangkan tali muatan" |
| **M – Medan** (latar) | Di mana adegan terjadi? | "Area parkir depan gudang distribusi di pagi hari, motor-motor berjajar rapi" |
| **E – Efek kamera** | Sudut dan gerak kamera? | "Kamera bergerak perlahan dari *close-up* tangan ke *medium shot*, setinggi mata" |
| **R – Ritme** | Durasi klip dan tempo gerakan? | "Klip 6 detik, gerakan tenang dan jelas" |
| **A – Atmosfer** | Cahaya, gaya visual, suasana, dan suara latar? | "Cahaya pagi alami, gaya dokumenter realistis, suara lingkungan gudang yang samar" |

> **Hubungan dengan Formula SKETSA (Modul 5):** KAMERA adalah SKETSA yang **bergerak**. Unsur baru yang khas video adalah **Aksi**, **Efek kamera**, dan **Ritme**. Tetap tambahkan **Kendala**: *"APD lengkap, tanpa logo merek nyata, tanpa teks di dalam video."*

### Templat Storyboard

| No. | Durasi | Visual (Formula KAMERA) | Narasi / dialog | Teks layar | Sumber | Catatan |
|---|---|---|---|---|---|---|
| 1 | 0–3 dtk | … | … | … | Generatif / Avatar / Rekaman / Gambar Modul 5 | … |
| 2 | 3–9 dtk | … | … | … | … | … |

Kolom **Sumber** menentukan alat mana yang dipakai untuk setiap adegan, sehingga satu video bisa menggabungkan klip generatif, presenter avatar, rekaman layar, dan gambar diam.

## 6.1.3 How To — Dari *Brief* ke Storyboard dengan Claude

**Langkah 1 — Tulis *brief* video:** tujuan, audiens, satu pesan inti, durasi, kanal, dan tindakan yang diharapkan.

**Langkah 2 — Minta Claude menulis naskah KIT:**
```
Anda adalah penulis naskah video pelatihan untuk karyawan operasional di Indonesia.
Tulis naskah video [durasi] dengan Formula KIT (Kait, Isi, Tindakan) untuk brief berikut.
Gunakan bahasa lisan yang sederhana, kalimat pendek, dan maksimal 3 poin isi.
Hitung perkiraan durasi narasi (±2–2,5 kata per detik untuk bahasa Indonesia).
[brief]
```

**Langkah 3 — Minta Claude mengubah naskah menjadi storyboard** dengan templat di atas, lalu menentukan **sumber** setiap adegan.

**Langkah 4 — Minta *prompt* KAMERA** dalam bahasa Inggris untuk setiap adegan yang bersumber dari alat generatif.

**Langkah 5 — Tinjau storyboard bersama pemilik materi** (misalnya tim K3 untuk video keselamatan) **sebelum** membuat klip apa pun.

**Langkah 6 — Buat klip, rakit, lalu ulas.** Ambil tangkapan layar frame kunci dan unggah ke Claude bersama transkrip untuk diulas dengan **Rubrik Ulasan Video** (Bab 6.2).

> **Tips Claude.ai:** Minta storyboard sebagai **Artifact** berbentuk tabel agar mudah diedit dan dibagikan ke tim. Untuk naskah narasi, minta Claude menandai istilah yang sulit diucapkan oleh suara AI dan menyediakan **ejaan fonetisnya**.

## 6.1.4 Studi Kasus & Contoh

### Studi Kasus AA — Video *Onboarding* K3 untuk Kurir Baru (Logistik)
**Situasi:** *PT Lintas Cepat Logistik (fiktif)* merekrut ±70 kurir baru setiap bulan karena *turnover* tinggi (lanjutan Studi Kasus C di Modul 1). Sesi *briefing* K3 tatap muka sering terlewat karena kurir baru langsung diturunkan ke rute. Perusahaan ingin video 45 detik yang wajib ditonton di aplikasi kurir sebelum shift pertama.

**❌ *Prompt* sebelum (langsung ke alat generatif):**
```
Video kurir motor yang aman berkendara.
```
**Hasil tipikal:** klip 5 detik dengan kurir berhelm terbuka, logo ojek daring yang mirip merek nyata, motor yang bergerak tidak wajar, dan **tanpa pesan yang bisa dipraktikkan**.

**✅ Naskah KIT (disusun Claude):**
> **[KAIT 0–3 dtk]** "Tiga menit di parkiran bisa menentukan selamat atau tidaknya Anda di jalan."
> **[ISI 3–38 dtk]** "Sebelum berangkat, lakukan cek H-R-M. **H**elm: terpasang dan talinya terkunci. **R**em: tekan rem depan dan belakang, pastikan pakem. **M**uatan: paket terikat dan tidak melebihi batas kotak."
> **[TINDAKAN 38–45 dtk]** "Lakukan cek H-R-M setiap pagi, lalu centang di aplikasi sebelum menerima rute pertama."

**✅ Storyboard ringkas (disusun Claude):**

| No. | Durasi | Visual | Sumber | Catatan |
|---|---|---|---|---|
| 1 | 0–3 dtk | Kurir memakai helm di parkiran gudang saat pagi | **Generatif** (KAMERA) | Klip suasana, tanpa prosedur rinci |
| 2 | 3–15 dtk | *Close-up* tali helm dikunci | **Rekaman nyata** dengan ponsel | Prosedur harus akurat → bukan generatif |
| 3 | 15–27 dtk | Tangan menekan rem depan dan belakang | **Rekaman nyata** | Sama |
| 4 | 27–38 dtk | Paket diikat di kotak motor | **Rekaman nyata** | Sama |
| 5 | 38–45 dtk | Layar aplikasi dengan centang H-R-M | **Rekaman layar** + teks di editor | Teks ditambahkan di editor |

***Prompt* KAMERA untuk adegan 1:**
```
[K] An Indonesian male courier in his 20s wearing a bright orange company jacket.
[A] He puts on a full-face helmet and fastens the chin strap, then gives a small confident nod.
[M] Parking area in front of an Indonesian distribution warehouse, delivery motorbikes
    neatly lined up, early morning.
[E] Slow push-in from medium shot to close-up, eye level.
[R] 4-second clip, calm and deliberate movement.
[A] Soft natural morning light, realistic documentary style, faint ambient warehouse sounds.
[Kendala] No real brand logos, no text in the video, natural hands and face.
```

**Pelajaran:** Keputusan terpenting di kasus ini ada di kolom **Sumber**. Video generatif dipakai hanya untuk adegan **suasana**. Adegan **prosedur keselamatan** direkam nyata karena video generatif bisa menampilkan gerakan yang salah. Mnemonik **H-R-M** di naskah membuat pesan mudah diingat dan langsung terhubung ke tindakan di aplikasi.

### 🗣️ Catatan Fasilitator — Bab 6.1
- **Latihan (20 menit):** Peserta menulis *brief* video 30–45 detik untuk satu kebutuhan HR, meminta Claude membuat naskah KIT dan storyboard, lalu menentukan sumber setiap adegan. Satu adegan suasana dibuat di alat generatif dengan *prompt* KAMERA.
- **Pertanyaan diskusi:** *"Adegan apa di video HR yang TIDAK boleh dibuat dengan video generatif, dan mengapa?"*

---

# BAB 6.2 — Penguatan: Kustomisasi Video AI

## 6.2.1 Overview Konsep

### a. Integrasi elemen brand
Video yang dibuat banyak orang dengan banyak alat akan cepat terlihat "tambal sulam" jika elemen brand tidak dibakukan.

| Elemen | Praktik yang disarankan |
|---|---|
| **Logo** | Tempatkan logo asli di editor sebagai *watermark* atau di *outro*; **jangan** meminta alat generatif membuat logo |
| **Warna** | Gunakan palet brand pada teks layar, *lower-third*, dan latar presenter avatar |
| ***Font*** | Satu *font* judul dan satu *font* isi, sesuai pedoman brand |
| **Intro/outro** | Templat 2–3 detik yang sama di semua video |
| **Musik & suara** | Musik berlisensi; suara narator atau avatar yang konsisten untuk satu seri |
| **Subtitle** | Selalu ada, karena banyak penonton menonton tanpa suara dan sebagian memerlukan aksesibilitas |

### b. Penerapan nyata di HR dan bisnis

| Penerapan | Format yang cocok | Kelompok alat |
|---|---|---|
| **Video *onboarding*** | 30–90 detik per topik, berseri | Perakit + rekaman nyata + klip generatif |
| ***Microlearning*** | 2–5 menit, satu tujuan belajar | Avatar presenter + *B-roll* + rekaman layar |
| **Demo produk / aplikasi** | Rekaman layar + narasi + sorotan | Perakit + suara AI atau avatar |
| **Pengumuman internal** | 30–60 detik | Avatar atau rekaman pimpinan asli |
| **Video rekrutmen** | 15–60 detik per kanal | Generatif + gambar Modul 5 + perakit |

### c. Menyesuaikan video untuk setiap kanal
Satu video "untuk semua kanal" biasanya tidak optimal di kanal mana pun. Rasio, durasi, kait, dan teks layar perlu disesuaikan.

## 6.2.2 Framework & Formula

### Kartu Gaya Video (Perluasan Kartu Gaya Visual Modul 5)

| Unsur | Isi | Contoh (*PT Baja Prima Manufaktur*, fiktif) |
|---|---|---|
| **Kartu Gaya Visual** | Palet, gaya foto, wajib/dilarang (Modul 5) | Biru baja dan oranye keselamatan, dokumenter, APD lengkap |
| **Intro/outro** | Durasi dan isi | Intro 2 detik logo animasi; outro 3 detik logo + tautan |
| ***Lower-third*** | Gaya nama/jabatan di layar | Bilah biru, teks putih, *font* sans-serif |
| **Teks layar** | Ukuran minimal dan posisi | Minimal 5% tinggi layar, di area aman tengah |
| **Subtitle** | Gaya dan aturan | Putih dengan latar gelap semi-transparan, maksimal 2 baris, maksimal ±40 karakter per baris |
| **Suara** | Narator/avatar | Suara AI perempuan, tempo sedang, nada hangat dan tegas; satu suara untuk satu seri |
| **Musik** | Jenis dan volume | Instrumental berlisensi, volume rendah di bawah narasi |
| **Label AI** | Posisi dan teks | Teks kecil di outro: *"Video ini dibuat dengan bantuan AI"* |

### Matriks Adaptasi Kanal

| Kanal | Rasio | Durasi ideal | Kait | Teks & subtitle | Catatan |
|---|---|---|---|---|---|
| **YouTube** | 16:9 | 1–5 menit (atau *Shorts* 9:16 ≤60 detik) | 5 detik pertama | Subtitle + *chapter* | Judul dan *thumbnail* menentukan klik |
| **Instagram Reels / TikTok** | 9:16 | 15–45 detik | 1–2 detik pertama | Teks besar di area aman tengah | Hindari area atas/bawah yang tertutup antarmuka |
| **LinkedIn** | 1:1, 4:5, atau 16:9 | 30–90 detik | 3 detik pertama | Subtitle wajib (banyak ditonton tanpa suara) | Nada profesional, fokus pada karier dan keahlian |
| **WhatsApp / aplikasi internal** | 9:16 atau 16:9 | ≤60 detik | Langsung ke inti | Teks besar, ukuran berkas kecil | Untuk pekerja lapangan dengan kuota terbatas |
| **LMS internal** | 16:9 | 2–5 menit per video | Tujuan belajar di awal | Subtitle + transkrip | Gabungkan dengan kuis (Bab 6.3) |

### Rubrik Ulasan Video (Perluasan Rubrik Ulasan Visual Modul 5)

| Kriteria | Pertanyaan | Skor 1–3 |
|---|---|---|
| **1. Akurasi isi** | Apakah informasi, prosedur, dan angka benar menurut pemilik materi? | 1 = salah · 3 = akurat |
| **2. Keselamatan kerja** | Apakah semua adegan menampilkan perilaku aman dan APD yang benar? | 1 = melanggar · 3 = patuh |
| **3. Konsistensi visual** | Apakah tokoh, seragam, dan lokasi konsisten antaradegan? | 1 = berubah · 3 = konsisten |
| **4. Audio & bahasa** | Apakah pelafalan, gerak bibir, dan tempo wajar untuk penonton Indonesia? | 1 = mengganggu · 3 = alami |
| **5. Subtitle & aksesibilitas** | Apakah subtitle akurat, terbaca, dan sinkron? | 1 = salah/tidak ada · 3 = baik |
| **6. Brand & kanal** | Apakah sesuai Kartu Gaya Video dan Matriks Adaptasi Kanal? | 1 = tidak sesuai · 3 = sesuai |
| **7. Tata kelola** | Apakah ada label AI, lisensi aset jelas, dan persetujuan avatar/suara jika diperlukan? | 1 = berisiko · 3 = aman |

**Kriteria layak tayang:** total ≥18 dari 21, dan **tidak ada skor 1** pada kriteria 1, 2, dan 7.

## 6.2.3 How To — Memproduksi Video Bermerek untuk Banyak Kanal

**Langkah 1 — Simpan Kartu Gaya Video** sebagai *project knowledge* di **Claude Project** "Studio Video HR" (lihat Modul 3), bersama Kartu Gaya Visual dari Modul 5.

**Langkah 2 — Produksi versi induk** (biasanya 16:9 atau 9:16, tergantung kanal utama) dari storyboard yang sudah disetujui.

**Langkah 3 — Pasang elemen brand di editor:** intro/outro, logo, *lower-third*, subtitle, dan label AI.

**Langkah 4 — Minta Claude membuat rencana adaptasi kanal:**
```
Ini naskah dan storyboard video induk (60 detik, 16:9). Dengan Matriks Adaptasi Kanal,
susun versi untuk Instagram Reels (30 detik, 9:16) dan LinkedIn (45 detik, 4:5):
- adegan mana yang dipertahankan, dipotong, atau di-reframe,
- kait baru untuk setiap kanal,
- teks layar dan keterangan unggahan untuk setiap kanal.
```

**Langkah 5 — Buat subtitle:** gunakan fitur transkripsi di alat video, lalu minta Claude **memeriksa dan memperbaiki** ejaan istilah perusahaan dan memecah baris sesuai aturan subtitle.

**Langkah 6 — Ulas dengan Rubrik Ulasan Video:** unggah tangkapan layar frame kunci dan transkrip ke Claude, lalu minta pemilik materi menilai kriteria 1 (akurasi isi).

## 6.2.4 Studi Kasus & Contoh

### Studi Kasus AB — Video *Microlearning* Prosedur LOTO di Pabrik (Manufaktur)
**Situasi:** *PT Baja Prima Manufaktur (fiktif)* perlu menyegarkan pemahaman 600 operator dan teknisi tentang prosedur **LOTO (*Lock-Out Tag-Out*)**, yaitu prosedur mengisolasi sumber energi mesin sebelum perawatan. Pelatihan kelas sulit dijadwalkan karena operator bekerja dalam shift. Tim L&D ingin seri 4 video *microlearning* @3 menit di LMS.

**Keputusan desain (berdasarkan risiko):**

| Bagian video | Sumber | Alasan |
|---|---|---|
| Pembuka dan penjelasan konsep | **Avatar presenter** dengan latar ruang kontrol pabrik | Cepat diperbarui, mudah dibuat dalam bahasa Indonesia dan bahasa Inggris untuk teknisi vendor |
| Langkah-langkah LOTO | **Rekaman nyata** di mesin pabrik, dipandu teknisi senior | Prosedur keselamatan **wajib akurat**; video generatif tidak boleh dipakai |
| Ilustrasi "mengapa LOTO penting" | **Animasi sederhana** / diagram (bisa dibuat sebagai SVG di Claude Artifacts) | Menjelaskan aliran energi tanpa menampilkan kecelakaan yang menakutkan |
| Rangkuman | Avatar + teks layar | Penegasan 3 poin kunci |

***Prompt* naskah ke Claude (cuplikan):**
```xml
<dokumen>
[SOP LOTO sintetis versi 2026, 6 langkah]
</dokumen>

<instruksi>
Tulis naskah video microlearning 3 menit untuk operator pabrik, video 2 dari 4:
"6 Langkah LOTO". Gunakan Formula KIT. Narasi presenter avatar maksimal 90 detik;
sisanya rekaman nyata dengan narasi voice-over.
Ikuti urutan dan istilah SOP PERSIS. Jangan menambah, mengurangi, atau mengubah
urutan langkah, karena kesalahan prosedur dapat menyebabkan kecelakaan kerja.
Tandai setiap kalimat yang merujuk langkah SOP dengan nomor langkahnya agar
mudah diverifikasi tim K3.
</instruksi>
```

**Hasil ulasan (Rubrik Ulasan Video) pada versi pertama:**
> Akurasi isi **3** (diverifikasi K3) · Keselamatan kerja **3** · Konsistensi visual 3 · Audio & bahasa **2** (avatar melafalkan "LOTO" sebagai "lo-to" dengan tekanan aneh; istilah *"isolasi energi"* terlalu cepat) · Subtitle 3 · Brand & kanal 3 · Tata kelola 3 → **Total 20/21, layak tayang** setelah perbaikan pelafalan dengan ejaan fonetis di naskah.

**Pelajaran:** Untuk video keselamatan, prinsip paling penting adalah **memisahkan bagian yang boleh dibuat AI dari bagian yang wajib nyata**. Avatar mempercepat produksi dan pembaruan, sedangkan rekaman nyata menjaga akurasi prosedur. Instruksi *"ikuti SOP persis"* beserta alasannya, ditambah penandaan nomor langkah, membuat verifikasi oleh tim K3 cepat dan dapat diaudit.

### Studi Kasus AC — Demo Aplikasi Kasir Baru untuk 120 Toko (Ritel)
**Situasi:** *PT Sinar Ritel Nusantara (fiktif)* meluncurkan aplikasi kasir (POS) baru di 120 toko dalam 3 minggu. Tim pelatihan tidak mungkin mengunjungi semua toko. Kasir perlu panduan yang bisa ditonton di ponsel, sedangkan Store Supervisor perlu versi lengkap.

**Desain produksi:**
- **Versi induk (LMS, 16:9, 4 menit):** rekaman layar aplikasi + narasi suara AI + sorotan tombol + subtitle.
- **Versi kasir (WhatsApp, 9:16, 5 klip @45 detik):** satu tugas per klip (buka shift, transaksi tunai, transaksi QRIS, retur, tutup shift).
- **Versi supervisor (LMS, 16:9):** versi induk + bagian laporan harian dan penanganan selisih kas.

**Peran Claude:**
```
Ini daftar tugas di aplikasi POS dan tangkapan layar setiap langkah (terlampir).
1. Tulis naskah voice-over untuk 5 klip kasir, masing-masing ≤45 detik, Formula KIT,
   bahasa lisan sederhana untuk kasir lulusan SMA/SMK.
2. Untuk setiap langkah, tulis teks sorotan (maks. 4 kata) yang ditempatkan dekat tombol.
3. Buat 3 pertanyaan kuis pilihan ganda per klip untuk menguji pemahaman.
4. Tandai langkah yang berbeda antara aplikasi lama dan baru, karena di situlah kasir
   paling mungkin salah.
```

**Pelajaran:** Untuk demo aplikasi, **rekaman layar asli** adalah sumber visual terbaik. AI dipakai untuk mempercepat **naskah, suara, subtitle, sorotan, dan kuis**, bukan untuk menciptakan visual. Instruksi nomor 4 (menandai perbedaan aplikasi lama dan baru) adalah wawasan **manajemen perubahan**: pelatihan difokuskan pada titik yang paling rawan kesalahan.

> **Catatan tata kelola:** Pastikan rekaman layar memakai **data transaksi dan pelanggan sintetis** (Modul 4), bukan data toko yang sebenarnya.

### 🗣️ Catatan Fasilitator — Bab 6.2
- **Latihan (35 menit):** Peserta mengambil naskah dari Bab 6.1, menyusun Kartu Gaya Video sederhana, memproduksi versi induk di alat perakit (misalnya Canva) dengan subtitle dan label AI, lalu meminta Claude membuat rencana adaptasi ke satu kanal lain. Ulas hasilnya dengan Rubrik Ulasan Video.
- **Pertanyaan diskusi:** *"Untuk pekerja lapangan di organisasi Anda, kanal apa yang paling efektif: LMS, WhatsApp, atau layar di area kerja? Bagaimana itu mengubah format videonya?"*

---

# BAB 6.3 — Penguasaan: Cerita Berbasis AI yang Memikat

## 6.3.1 Overview Konsep

### a. Personalisasi: satu pesan, banyak audiens
Video AI memungkinkan pembuatan **beberapa versi** dari satu kampanye dengan biaya rendah. Personalisasi yang efektif mengubah **sudut pesan**, bukan sekadar mengganti nama.

| Tingkat personalisasi | Contoh | Risiko |
|---|---|---|
| **Segmen audiens** | Versi untuk siswa SMK, orang tua, dan guru | Rendah |
| **Bahasa & lokasi** | Versi bahasa Indonesia, Inggris, atau dengan latar pabrik tertentu | Rendah; cek pelafalan |
| **Peran atau departemen** | *Onboarding* berbeda untuk gudang, kurir, dan kantor | Rendah |
| **Individu** (nama di video) | "Selamat datang, Rina!" | **Lebih tinggi:** memproses data pribadi, berisiko salah nama atau kesalahan pengiriman massal; gunakan hanya di platform yang disetujui dan dengan data minimal |

### b. Video untuk kebutuhan lanjutan
- **Peluncuran program:** program pengembangan baru, sistem HRIS baru, kebijakan baru.
- **Acara perusahaan:** pembuka *town hall*, video ulang tahun perusahaan, *job fair*.
- **Komunikasi skala besar:** pesan perubahan organisasi ke ribuan karyawan di banyak lokasi.

> **Catatan HR:** Untuk pesan yang **sensitif atau emosional**, seperti restrukturisasi, PHK, duka cita, atau insiden keselamatan, **gunakan pimpinan asli**, bukan avatar. Pesan sulit yang disampaikan avatar akan terasa tidak manusiawi dan merusak kepercayaan.

### c. Video dalam pengalaman interaktif
Video menjadi lebih efektif jika penonton **berinteraksi**:
- **Kuis sela:** pertanyaan setelah setiap bagian video di LMS.
- **Video bercabang:** penonton memilih tindakan, lalu melihat konsekuensinya (misalnya simulasi menangani keluhan pelanggan).
- **Modul *e-learning*:** video + kuis + rangkuman yang dikemas dalam LMS. Claude dapat menyusun kuis, skenario percabangan, bahkan prototipe interaktif sederhana sebagai **Artifact**.

### d. Tata kelola: avatar, suara, dan *deepfake*

| Risiko | Contoh | Pengaman |
|---|---|---|
| **Avatar tanpa persetujuan** | Membuat avatar direktur dari video *town hall* tanpa izin | **Persetujuan tertulis** yang menyebut tujuan, kanal, durasi pemakaian, dan hak menarik persetujuan |
| **Penyalahgunaan avatar/suara** | Avatar dipakai untuk pesan yang tidak disetujui pemilik wajah | Setiap naskah avatar pimpinan **disetujui pemiliknya**; akses ke avatar dibatasi |
| **Penipuan *deepfake*** | Video atau panggilan palsu "pimpinan" yang meminta transfer dana atau data karyawan | Protokol verifikasi: permintaan sensitif **selalu dikonfirmasi melalui saluran kedua**; edukasi karyawan |
| **Karyawan setelah keluar** | Avatar mantan karyawan masih dipakai di video pelatihan | Atur masa berlaku dan prosedur penghapusan di perjanjian persetujuan |
| **Transparansi** | Penonton mengira presenter adalah orang sungguhan | Label *"Video ini dibuat dengan bantuan AI"* dan penjelasan di awal seri |

## 6.3.2 Framework & Formula

### Matriks Personalisasi Kampanye

| Audiens | Kekhawatiran utama | Sudut pesan | Kait | Tindakan |
|---|---|---|---|---|
| [Segmen 1] | [Apa yang mereka khawatirkan?] | [Pesan yang menjawab kekhawatiran itu] | [Kalimat pembuka] | [Apa yang harus mereka lakukan] |
| [Segmen 2] | … | … | … | … |
| [Segmen 3] | … | … | … | … |

> **Prinsip:** kolom **Kekhawatiran utama** diisi lebih dulu. Personalisasi yang baik berangkat dari **apa yang dipikirkan audiens**, bukan dari apa yang ingin dikatakan perusahaan.

### Perjanjian Persetujuan Avatar & Suara (Daftar Isi Minimal)

| Unsur | Isi |
|---|---|
| **Identitas & ruang lingkup** | Wajah, suara, atau keduanya; alat yang dipakai |
| **Tujuan & kanal** | Misalnya: hanya video pelatihan internal di LMS |
| **Batasan isi** | Jenis pesan yang **tidak boleh** disampaikan avatar (misalnya kebijakan kompensasi, PHK, pernyataan publik) |
| **Persetujuan naskah** | Siapa yang menyetujui setiap naskah sebelum dibuat |
| **Masa berlaku** | Tanggal berakhir dan peninjauan ulang |
| **Penarikan & penghapusan** | Hak menarik persetujuan dan jangka waktu penghapusan data avatar/suara |
| **Kompensasi** (jika ada) | Sesuai kebijakan perusahaan |

> **Catatan:** Wajah dan suara termasuk **data pribadi**, dan data biometrik tergolong data pribadi yang bersifat spesifik menurut **UU PDP**. Libatkan Legal dan DPO (*Data Protection Officer*) sebelum membuat avatar dari orang sungguhan.

### Alur Produksi Video Terintegrasi

```
Brief → Matriks Personalisasi → Naskah KIT per segmen (Claude) → Storyboard + sumber adegan
   → Produksi (generatif / avatar / rekaman / gambar Modul 5) → Kartu Gaya Video
      → Adaptasi kanal → Rubrik Ulasan Video + persetujuan pemilik materi
         → Integrasi interaktif (kuis, LMS) → Label AI → Publikasi → Ukur (tonton, kuis, tindakan)
```

## 6.3.3 How To — Kampanye Video yang Dipersonalisasi dan Interaktif

**Langkah 1 — Isi Matriks Personalisasi** bersama Claude: *"Untuk kampanye ini, siapa 3 audiens utamanya dan apa kekhawatiran terbesar masing-masing? Gunakan ToT: usulkan 5 segmen, lalu pilih 3 yang paling berdampak."*

**Langkah 2 — Tulis naskah KIT per segmen.** Pertahankan adegan inti yang sama agar produksi efisien, dan ubah **kait, narasi, dan tindakan**.

**Langkah 3 — Rencanakan aset bersama:** adegan yang dipakai di semua versi dan adegan khusus per segmen.

**Langkah 4 — Produksi dan ulas** setiap versi dengan Rubrik Ulasan Video.

**Langkah 5 — Tambahkan interaksi:** minta Claude membuat kuis sela atau skenario bercabang:
```
Dari naskah video ini, buat:
1. 3 kuis sela (satu setelah setiap bagian), pilihan ganda dengan penjelasan jawaban.
2. Satu skenario bercabang: penonton memilih 1 dari 3 tindakan, dengan konsekuensi
   singkat untuk setiap pilihan dan umpan balik.
3. Ringkasan 5 poin untuk halaman terakhir modul e-learning.
```

**Langkah 6 — Ukur dampak:** tingkat tonton sampai selesai, skor kuis, dan **tindakan nyata** (misalnya jumlah pendaftar *job fair*, kepatuhan cek K3 di aplikasi).

## 6.3.4 Studi Kasus & Contoh

### Studi Kasus AD — Video Kampanye "Dari Operator ke Ahli Otomasi" untuk 3 Audiens (Praktik Utama Modul)
**Situasi:** *PT Baja Prima Manufaktur (fiktif)* sudah memiliki 5 gambar kampanye yang disetujui dan storyboard 30 detik dari **Studi Kasus Z (Modul 5)**. Kampanye akan dibawa ke *job fair* di 12 SMK. Tim HR menyadari bahwa keputusan bekerja di pabrik sering ditentukan bukan hanya oleh siswa, tetapi juga oleh **orang tua** dan **guru BK/kejuruan**.

**Tahap 1 — Matriks Personalisasi (disusun bersama Claude):**

| Audiens | Kekhawatiran utama | Sudut pesan | Kait | Tindakan |
|---|---|---|---|---|
| **Siswa SMK** | "Kerja pabrik membosankan, tidak ada masa depan" | Teknologi modern dan jalur karier nyata | "Robot ini butuh teknisi. Kenapa bukan kamu?" | Daftar di *booth* atau pindai kode |
| **Orang tua** | "Apakah anak saya aman dan punya penghasilan stabil?" | Keselamatan kerja, jenjang karier, pelatihan dibiayai | "Keselamatan putra-putri Anda adalah prosedur pertama kami." | Kunjungi hari terbuka pabrik |
| **Guru SMK** | "Apakah kurikulum sekolah kami relevan dengan industri?" | Kolaborasi kelas industri dan magang | "Siswa Anda belajar di kelas, kami lanjutkan di lini produksi." | Ajukan program kelas industri |

**Tahap 2 — Produksi efisien**
- **Adegan bersama (≈60% durasi):** klip generatif dari 5 gambar Modul 5 (gambar-ke-video), seperti lengan robot bergerak dan operator memakai APD.
- **Adegan khusus per segmen:** siswa melihat kompetisi robotik; orang tua melihat briefing K3 dan ruang pelatihan (**rekaman nyata**); guru melihat kelas industri (**rekaman nyata dengan persetujuan peserta**).
- **Narasi:** suara AI dengan gaya berbeda per segmen (energik untuk siswa, hangat dan tenang untuk orang tua, profesional untuk guru).

**Tahap 3 — Interaksi di *job fair***
Claude menyusun **kuis 5 pertanyaan "Cocokkah Kamu Jadi Teknisi Otomasi?"** yang ditampilkan di tablet *booth* setelah video, lalu mengarahkan siswa ke formulir minat. Claude juga membuat prototipe kuisnya sebagai **Artifact** untuk diuji tim sebelum dibuat versi finalnya oleh tim IT.

**Tahap 4 — Ulasan dan persetujuan**

| Penyetuju | Fokus |
|---|---|
| Tim K3 | Semua adegan APD dan perilaku kerja (Rubrik kriteria 2) |
| HR Talent | Kebenaran klaim jalur karier dan program pelatihan (kriteria 1) |
| Tim Brand | Kartu Gaya Video dan adaptasi kanal (kriteria 6) |
| Legal | Persetujuan orang yang tampil di rekaman nyata, lisensi musik, label AI (kriteria 7) |

**Indikator keberhasilan yang ditetapkan *(target ilustratif)*:** ≥60% pengunjung *booth* menonton sampai selesai, ≥25% mengisi formulir minat, dan ≥3 SMK mengajukan kelas industri.

**Pelajaran:** Satu storyboard dari Modul 5 menjadi **tiga video** yang masing-masing menjawab kekhawatiran audiens yang berbeda, dengan biaya tambahan kecil karena 60% adegannya dipakai bersama. Personalisasi yang kuat berangkat dari **kekhawatiran audiens**. Untuk orang tua, isu utamanya adalah **keselamatan**, sehingga bagian itu memakai rekaman nyata, bukan video generatif.

### Studi Kasus AE — Modul *Onboarding* Interaktif dengan Avatar Pimpinan (B2B Industri)
**Situasi:** *PT Mitra Teknik Industri (fiktif)* membangun modul *onboarding* digital untuk **Technical Sales Engineer** baru (lanjutan Studi Kasus J dan Y). Direktur Penjualan mengusulkan "buat saja avatar saya dari video *town hall* supaya bisa menyapa setiap karyawan baru".

**Tegangan yang harus diputuskan:**
- **Lensa AI:** avatar pimpinan dapat membuat ratusan video sapaan yang dipersonalisasi per cabang, dalam beberapa bahasa, dan mudah diperbarui.
- **Lensa HR:** avatar dari video *town hall* **tanpa persetujuan eksplisit** berisiko secara hukum, dan sapaan yang terasa "terlalu sempurna" bisa terasa tidak autentik bagi karyawan baru. Avatar pimpinan juga membuka **risiko *deepfake***: jika karyawan terbiasa menerima video avatar direktur, video palsu akan lebih mudah dipercaya.

**Keputusan desain:**
1. **Video sapaan direktur direkam nyata sekali** (60 detik, tanpa personalisasi nama), karena pesan budaya dan nilai paling kuat jika disampaikan langsung.
2. **Avatar dipakai untuk 6 video *microlearning* produk dan proses penjualan**, menggunakan **avatar bawaan alat** (bukan wajah direktur) atau avatar dari *trainer* internal yang memberikan **persetujuan tertulis** sesuai Perjanjian Persetujuan.
3. **Modul interaktif:** setiap video *microlearning* diikuti kuis sela dan satu **simulasi bercabang** "menghadapi keberatan harga dari *plant manager*", yang naskah dan percabangannya disusun Claude.
4. **Protokol anti-*deepfake*:** modul *onboarding* menyertakan satu pelajaran singkat: *"Perusahaan tidak akan pernah meminta data, kata sandi, atau transfer dana melalui video atau pesan suara. Selalu verifikasi melalui saluran resmi kedua."*

***Prompt* simulasi bercabang (cuplikan):**
```
Susun simulasi bercabang untuk Technical Sales Engineer baru: plant manager pelanggan
berkata "Harga pompa Anda 18% lebih mahal daripada pesaing."
Buat 3 pilihan respons: (a) langsung memberi diskon, (b) menggali total biaya kepemilikan
dan waktu henti mesin, (c) membandingkan spesifikasi teknis secara defensif.
Untuk setiap pilihan, tulis reaksi pelanggan (2–3 kalimat), konsekuensi bisnis,
dan umpan balik pembelajaran. Pilihan terbaik harus didukung prinsip penjualan
konsultatif, tanpa menjelekkan pesaing.
```

**Pelajaran:** Pertanyaan yang tepat bukan "bisakah kita membuat avatar direktur?" (secara teknis bisa), tetapi **"pesan mana yang harus disampaikan manusia asli, dan pesan mana yang boleh dibantu AI?"**. Pesan budaya dan nilai disampaikan **manusia asli**. Materi produk dan proses yang sering diperbarui menggunakan **avatar dengan persetujuan yang jelas**. Edukasi anti-*deepfake* menjadi bagian dari *onboarding*, karena semakin luas pemakaian avatar di perusahaan, semakin besar pula kebutuhan karyawan untuk mampu mengenali video palsu.

### Tahap Akhir — Simpan ke Pustaka *Prompt*

| Kolom | Isi |
|---|---|
| **Nama & ID** | `HR-VID-001 Naskah & Storyboard Video HR (KIT + KAMERA)` |
| **Versi** | v1.0 — 16/10/2026 |
| **Pemilik** | L&D Digital Lead (bersama Employer Branding Lead) |
| **Teknik** | Formula KIT + Formula KAMERA + Templat Storyboard (kolom Sumber) + Matriks Adaptasi Kanal + Rubrik Ulasan Video |
| **Variabel** | `{{tujuan_video}}`, `{{audiens}}`, `{{durasi}}`, `{{kanal}}`, `{{dokumen_SOP_rujukan}}`, `{{kartu_gaya_video}}` |
| **Platform diuji** | Claude ✅ (naskah, storyboard, *prompt*, kuis, ulasan frame & transkrip) · Alat generatif ✅ (klip suasana) · Alat avatar ✅ (*microlearning*) · Canva/editor ✅ (perakitan & subtitle) |
| **Risiko & tata kelola** | Prosedur keselamatan wajib memakai rekaman nyata dan diverifikasi K3. Avatar atau suara orang sungguhan hanya dengan Perjanjian Persetujuan. Pesan sensitif disampaikan pimpinan asli. Label AI di setiap video. Rekaman layar memakai data sintetis. |

### 🗣️ Catatan Fasilitator — Bab 6.3
- **Praktik utama (35 menit):** Dalam kelompok, peserta menjalankan Studi Kasus AD untuk perusahaan fiktif pilihan mereka: isi Matriks Personalisasi untuk 3 audiens, tulis naskah KIT per segmen bersama Claude, produksi minimal satu versi 30 detik, lalu buat 3 kuis sela. Presentasikan video beserta skor Rubrik Ulasan Video.
- **Variasi:** Kelompok yang memakai storyboard dari Studi Kasus Z (Modul 5) dapat langsung menggunakan gambar kampanye mereka sebagai bahan klip gambar-ke-video.
- **Pertanyaan diskusi:** *"Pesan apa di organisasi Anda yang TIDAK boleh disampaikan oleh avatar AI? Siapa yang memutuskan batasnya?"*

---

## Rangkuman Modul 6

| Bab | Formula/Kerangka | Satu kalimat inti |
|---|---|---|
| **6.1 Fondasi** | **3 Kelompok Alat** + **Formula KIT** (Kait, Isi, Tindakan) + **Formula KAMERA** (Karakter, Aksi, Medan, Efek kamera, Ritme, Atmosfer) + Templat Storyboard | Video yang baik ditentukan di naskah dan storyboard, dan prosedur keselamatan tidak boleh dibuat dengan video generatif. |
| **6.2 Penguatan** | **Kartu Gaya Video** + **Matriks Adaptasi Kanal** + **Rubrik Ulasan Video** | Bakukan elemen brand, sesuaikan setiap kanal, dan pastikan akurasi isi diverifikasi oleh pemilik materi. |
| **6.3 Penguasaan** | **Matriks Personalisasi** + Perjanjian Persetujuan Avatar & Suara + Alur Produksi Terintegrasi | Personalisasi berangkat dari kekhawatiran audiens, interaksi memperkuat pembelajaran, dan pesan penting tetap disampaikan manusia asli. |

## Kuis Singkat (Kunci Jawaban untuk Fasilitator)

1. **Sebutkan tiga kelompok alat video AI.** → *Generatif (teks/gambar-ke-video), avatar/presenter, dan perakit (naskah/aset-ke-video).*
2. **Apa peran Claude dalam produksi video?** → *Menulis naskah, storyboard, shot list, prompt adegan, subtitle, dan kuis, serta mengulas frame kunci dan transkrip. Claude tidak membuat video.*
3. **Sebutkan tiga bagian Formula KIT.** → *Kait, Isi, Tindakan.*
4. **Unsur Formula KAMERA apa yang tidak ada di Formula SKETSA?** → *Aksi, Efek kamera (gerak kamera), dan Ritme (durasi/tempo).*
5. **Mengapa adegan prosedur keselamatan sebaiknya tidak dibuat dengan video generatif?** → *Video generatif dapat menampilkan gerakan, alat, atau urutan yang salah, padahal prosedur keselamatan wajib akurat.*
6. **Pada Rubrik Ulasan Video, kriteria mana yang tidak boleh bernilai 1?** → *Akurasi isi, keselamatan kerja, dan tata kelola.*
7. **Apa saja isi minimal persetujuan avatar dan suara?** → *Ruang lingkup, tujuan dan kanal, batasan isi, persetujuan naskah, masa berlaku, serta hak penarikan dan penghapusan.*
8. **Bagaimana melindungi karyawan dari penipuan *deepfake*?** → *Protokol verifikasi melalui saluran kedua untuk setiap permintaan sensitif, edukasi karyawan, dan pembatasan pemakaian avatar pimpinan.*

## Tugas Portofolio (Modul Pilihan)
Kumpulkan **3 Kartu Pustaka *Prompt*** dari pekerjaan Anda sendiri (dengan perusahaan fiktif atau aset berlisensi):
- 1 **naskah KIT + storyboard** lengkap dengan kolom Sumber dan minimal satu *prompt* **KAMERA**,
- 1 **video bermerek** (30–90 detik) beserta Kartu Gaya Video, satu versi adaptasi kanal, dan skor **Rubrik Ulasan Video**,
- 1 **Matriks Personalisasi** untuk 3 audiens dan satu paket interaksi (kuis sela atau skenario bercabang).

Setiap kartu wajib mencantumkan alat yang dipakai, ketentuan lisensinya, label AI, dan, jika ada orang sungguhan yang tampil atau suaranya dipakai, bukti persetujuan tertulis.

---
> **Catatan tata kelola:** Semua nama perusahaan dalam modul ini fiktif, dan angka target adalah **asumsi ilustratif**. Dalam praktik nyata, gunakan alat video yang disetujui perusahaan dan mengizinkan penggunaan komersial. Prosedur keselamatan dan kebijakan harus diverifikasi pemilik materi. Wajah dan suara orang sungguhan hanya boleh dipakai dengan **persetujuan tertulis** sesuai **UU Pelindungan Data Pribadi (UU PDP)**. Setiap video yang dibuat dengan AI harus diberi label, dan karyawan perlu dibekali kemampuan mengenali serta memverifikasi video yang berpotensi *deepfake*.

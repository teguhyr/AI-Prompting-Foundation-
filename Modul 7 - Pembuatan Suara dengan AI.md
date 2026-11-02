# Modul Pilihan 7 — Pembuatan Suara dengan AI (*Text-to-Speech*)
### Materi Pelatihan · Kurikulum Pelatihan Prompting AI

---

## Pengantar Modul

**Ide pokok modul:** Banyak karyawan di garis depan, seperti kurir, operator pabrik, kru toko, dan teknisi lapangan, jarang membuka email atau portal, tetapi **selalu mendengar**. Teknologi *text-to-speech* (TTS) dan suara AI membuka kanal komunikasi HR yang **lebih inklusif**: pesan suara, pengumuman toko, *helpdesk* telepon, dan asisten suara yang bisa dipakai tanpa tangan. Kualitasnya ditentukan oleh **naskah yang ditulis untuk telinga**, bukan untuk mata. Karena suara manusia kini bisa ditiru, **persetujuan tertulis, keterbukaan bahwa pengguna sedang berbicara dengan AI, dan pencegahan penipuan suara** menjadi bagian inti dari setiap desain.

### Tujuan Pembelajaran
Setelah menyelesaikan modul ini, peserta mampu:
1. Menjelaskan cara kerja TTS dan teknologi suara terkait, membandingkan platform utama dari sisi bahasa Indonesia, intonasi, dan lisensi, serta menyusun naskah "enak didengar" dengan **Formula SUARA**.
2. Mengatur suara, nada, kecepatan, dan gaya bicara dengan **Kartu Suara Brand**, instruksi gaya, dan **SSML**, lalu merancang interaksi suara untuk asisten, *chatbot*, dan sistem telepon otomatis dengan **Formula 3J** (Jelas, Jeda, Jalan keluar).
3. Merancang asisten suara percakapan (*voice mode / realtime voice*) dengan memilih **arsitektur yang tepat**, serta menggabungkan TTS dengan alat AI lain untuk pengalaman konten multikanal.
4. Menerapkan tata kelola suara AI: **persetujuan tertulis untuk *voice cloning***, keterbukaan AI, perekaman percakapan, dan pencegahan penipuan suara (*vishing*).

### Agenda Sesi (±3 jam, modul pilihan)

| Waktu | Bab | Aktivitas |
|---|---|---|
| 0:00–0:10 | Pembuka | *Ice breaker*: "Dengarkan 3 rekaman, tebak mana suara manusia" |
| 0:10–0:55 | **Bab 7.1** Fondasi | Cara kerja TTS, peta platform, Formula SUARA, uji 3 alat |
| 0:55–1:05 | Rehat | — |
| 1:05–2:00 | **Bab 7.2** Penguatan | Kartu Suara Brand, instruksi gaya & SSML, Formula 3J, praktik *helpdesk* telepon |
| 2:00–2:50 | **Bab 7.3** Penguasaan | *Voice cloning* & persetujuan, arsitektur asisten suara, konten multikanal, praktik utama |
| 2:50–3:00 | Penutup | Kuis singkat & refleksi |

> **Persiapan peserta:** akun Claude.ai (wajib, untuk naskah dan desain percakapan; aplikasi seluler Claude untuk mencoba **mode suara**), ditambah **minimal satu alat TTS** yang disetujui perusahaan (misalnya ElevenLabs, fitur TTS OpenAI, Gemini, atau layanan suara *cloud*). Bawa *headset* untuk latihan mendengar.

> **Catatan platform:** Claude **tidak menyediakan alat pembuat berkas audio TTS** di Claude.ai, tetapi aplikasi Claude memiliki **mode suara** untuk bercakap-cakap. Dalam modul ini, peran utama Claude adalah **penulis naskah, perancang percakapan, dan "otak" (LLM) di dalam asisten suara**. Nama fitur, pilihan suara bahasa Indonesia, harga, dan lisensi alat TTS berubah cepat. Fasilitator wajib mengecek ulang sebelum sesi.

> **Aturan sesi:** **dilarang membuat klon suara** siapa pun, termasuk suara sendiri dan suara rekan peserta, kecuali latihan khusus yang dipimpin fasilitator dengan formulir persetujuan tertulis. Gunakan suara bawaan (*stock voices*) alat TTS.

---

# BAB 7.1 — Fondasi: Menghidupkan Teks dengan Suara AI

## 7.1.1 Overview Konsep

### a. Bagaimana TTS bekerja?
TTS modern berbasis **jaringan saraf** (*neural TTS*) dan umumnya melalui tiga tahap:
1. **Normalisasi teks:** mengubah tulisan menjadi bentuk yang bisa diucapkan, misalnya "Rp 4.500.000" menjadi "empat juta lima ratus ribu rupiah" dan "15/10" menjadi "lima belas Oktober".
2. **Pemodelan prosodi:** menentukan intonasi, tekanan, tempo, dan jeda.
3. **Sintesis suara:** menghasilkan gelombang suara yang terdengar alami.

Akibat praktisnya: **sebagian besar kesalahan TTS bukan masalah suara, melainkan masalah teks.** Singkatan, angka, tanggal, istilah asing, dan tanda baca yang ambigu adalah sumber utama pelafalan yang aneh.

> **Analogi kunci:** Alat TTS adalah **penyiar radio yang sangat fasih, tetapi membaca naskah persis seperti yang tertulis**. Jika naskahnya ditulis untuk dibaca mata (penuh singkatan, tabel, dan kalimat panjang), penyiar terbaik pun akan terdengar kaku.

### b. Peta teknologi suara

| Teknologi | Fungsi | Contoh kegunaan HR |
|---|---|---|
| **TTS** (*text-to-speech*) | Teks → suara | Pesan suara pengumuman, narasi *microlearning*, pengumuman toko |
| **STT** (*speech-to-text*) | Suara → teks | Transkripsi wawancara (dengan izin), karyawan bertanya dengan suara |
| ***Voice cloning*** | Membuat suara sintetis yang meniru suara orang tertentu | Narasi konsisten oleh *trainer* internal (dengan persetujuan) |
| **Suara percakapan *realtime*** | Bercakap-cakap langsung dengan AI | Asisten suara layanan karyawan, latihan wawancara |

### c. Peta platform TTS

| Platform | Kekuatan umum | Catatan untuk HR |
|---|---|---|
| **ElevenLabs** | Suara sangat ekspresif, banyak bahasa, *voice cloning*, pustaka suara | Populer untuk narasi dan konten; cek lisensi komersial per paket |
| **TTS OpenAI** | Mudah diintegrasikan lewat API; beberapa model menerima **instruksi gaya bicara** dalam bahasa alami | Cocok untuk aplikasi yang sudah memakai ekosistem OpenAI |
| **Gemini TTS / Gemini Live** (Google) | TTS dengan kendali gaya lewat *prompt*; percakapan suara *realtime* | Cocok untuk organisasi berbasis Google |
| **Layanan suara *cloud*** (misalnya Azure AI Speech, Google Cloud Text-to-Speech) | Dukungan **SSML** yang luas, kontrol kepatuhan *enterprise* | Cocok untuk sistem telepon dan integrasi skala besar |
| **Mode suara** di aplikasi Claude dan ChatGPT | Bercakap-cakap dengan asisten AI | Untuk latihan dan penggunaan pribadi, bukan produksi berkas audio |
| **Claude** (Anthropic) | Naskah, normalisasi teks, desain percakapan, LLM di dalam asisten suara | Tidak menghasilkan berkas audio TTS |

### d. Kriteria memilih alat TTS untuk konteks Indonesia

| Kriteria | Pertanyaan uji |
|---|---|
| **Bahasa Indonesia** | Apakah pelafalan alami, termasuk kata serapan, nama daerah, dan istilah seperti "BPJS", "THR", "K3"? |
| **Intonasi** | Apakah kalimat tanya, penekanan, dan jeda terdengar wajar, tidak datar seperti robot? |
| **Variasi suara** | Apakah ada suara dewasa, muda, laki-laki, dan perempuan yang sesuai budaya kerja Indonesia? |
| **Kendali** | Apakah kecepatan, nada, jeda, dan pelafalan bisa diatur (instruksi gaya, SSML, kamus pelafalan)? |
| **Lisensi** | Apakah hasilnya boleh dipakai untuk keperluan komersial atau internal perusahaan? |
| **Data** | Di mana teks dan audio diproses dan disimpan? Apakah teks dipakai untuk melatih model? |

### e. Naskah untuk telinga vs naskah untuk mata

| Naskah untuk mata | Naskah untuk telinga |
|---|---|
| Kalimat panjang dengan anak kalimat | Kalimat pendek, satu ide per kalimat |
| Singkatan dan angka (Rp 4,5 jt, 15/10, HRD) | Dieja sesuai cara diucapkan |
| Tabel, poin, tanda kurung | Urutan lisan: "pertama… kedua…" |
| Informasi penting di mana saja | Informasi penting **diulang** di akhir |
| Pembaca bisa membaca ulang | Pendengar hanya mendengar sekali |

## 7.1.2 Framework & Formula

### Formula SUARA: Naskah yang Enak Didengar

```
NASKAH SUARA = Singkat + Urut + Angka dieja + Akrab + Ritme
```

| Unsur | Makna | Contoh perubahan |
|---|---|---|
| **S – Singkat** | Kalimat maksimal ±15 kata; satu ide per kalimat | "Mulai Senin, absensi pakai aplikasi. Absen manual tidak berlaku lagi." |
| **U – Urut** | Penanda urutan lisan dan pengulangan pesan inti di akhir | "Ada tiga hal. Pertama… Kedua… Ketiga… Sekali lagi, intinya…" |
| **A – Angka dieja** | Angka, tanggal, mata uang, dan singkatan ditulis seperti diucapkan | "Rp 4.500.000" → "empat setengah juta rupiah"; "BPJS" → "be-pe-je-es" (jika alat salah ucap) |
| **A – Akrab** | Bahasa lisan yang sopan dan hangat, menyapa pendengar | "Rekan-rekan kurir, ada kabar baik untuk Anda." |
| **R – Ritme** | Jeda di tempat penting, variasi panjang kalimat, penekanan pada kata kunci | Gunakan titik, koma, dan baris baru; di alat yang mendukung, gunakan tanda jeda atau SSML |

> **Hubungan dengan Formula KIT (Modul 6):** Naskah audio tetap memakai struktur **Kait–Isi–Tindakan**. Formula SUARA mengatur **cara menulis** setiap kalimat di dalamnya agar mudah ditangkap telinga.

### Durasi Naskah Audio
Kecepatan bicara bahasa Indonesia yang nyaman di audio berkisar **±130–150 kata per menit**.

| Format | Durasi | Panjang naskah |
|---|---|---|
| Pesan suara WhatsApp | 30–60 detik | ±70–150 kata |
| Pengumuman toko/pabrik | 20–40 detik | ±45–100 kata |
| Konten audio media sosial / *explainer* | 45–90 detik | ±100–220 kata |
| Episode *podcast* internal | 5–10 menit | ±700–1.500 kata |

## 7.1.3 How To — Dari Teks ke Audio

**Langkah 1 — Mulai dari pesan tertulis** (pengumuman, kebijakan, atau materi pelatihan).

**Langkah 2 — Minta Claude menulis ulang untuk telinga:**
```
Anda adalah penulis naskah audio untuk karyawan garis depan di Indonesia.
Ubah pengumuman berikut menjadi naskah pesan suara [durasi] dengan Formula SUARA:
Singkat (maks. 15 kata per kalimat), Urut (penanda lisan + ulangi inti di akhir),
Angka dieja (tulis angka, tanggal, rupiah, dan singkatan seperti diucapkan),
Akrab (sapa pendengar, sopan dan hangat), Ritme (beri baris baru di tempat jeda).
Setelah naskah, buat daftar kata yang berisiko salah diucapkan alat TTS beserta
ejaan fonetisnya.
[pengumuman]
```

**Langkah 3 — Bacakan sendiri dengan suara keras.** Jika Anda tersandung, alat TTS pun akan terdengar janggal.

**Langkah 4 — Hasilkan audio di 2–3 alat TTS** dengan naskah yang sama dan bandingkan dengan kriteria pemilihan alat.

**Langkah 5 — Perbaiki pelafalan:** gunakan ejaan fonetis di naskah, kamus pelafalan (jika tersedia), atau SSML (Bab 7.2).

**Langkah 6 — Uji ke 3–5 pendengar sasaran** dan tanyakan: *"Apa yang Anda ingat setelah mendengar sekali?"* Jika pesan inti tidak diingat, perbaiki naskahnya.

## 7.1.4 Studi Kasus & Contoh

### Studi Kasus AF — Pesan Suara Mingguan untuk Kurir (Logistik)
**Situasi:** *PT Lintas Cepat Logistik (fiktif)* mengirim pengumuman HR mingguan ke 1.200 kurir melalui grup WhatsApp. Survei menunjukkan **kurang dari 30%** kurir membaca pengumuman panjang karena mereka berada di jalan. Perubahan skema insentif yang tidak dipahami adalah salah satu penyebab *turnover* (Studi Kasus C, Modul 1).

**❌ Teks asli (ditulis untuk mata):**
```
Diinformasikan kpd seluruh kurir, efektif tgl 20/10 skema insentif per paket berubah
dari Rp 2.500/pkt mjd Rp 2.750/pkt utk pengiriman ≥80 pkt/hari (lihat lampiran SK
No. 045/HR/X/2026). Klaim selisih via aplikasi menu Insentif > Riwayat.
```
**Jika dibacakan TTS apa adanya:** "kpd", "tgl", "mjd", "≥80 pkt", dan nomor SK dibaca janggal atau salah. Pesan intinya, yaitu insentif naik untuk kurir yang mengirim minimal 80 paket, tenggelam.

**✅ Naskah sesudah (Formula SUARA, disusun Claude):**
> Rekan-rekan kurir, selamat pagi. Ada kabar baik soal insentif.
>
> Mulai Senin, dua puluh Oktober, insentif per paket naik.
> Dari dua ribu lima ratus rupiah, menjadi dua ribu tujuh ratus lima puluh rupiah.
>
> Syaratnya satu. Anda mengirim paling sedikit delapan puluh paket dalam sehari.
>
> Mau cek hitungan insentif Anda? Buka aplikasi kurir, pilih menu Insentif, lalu Riwayat.
>
> Sekali lagi. Mulai dua puluh Oktober, kirim delapan puluh paket sehari, insentif per paket jadi dua ribu tujuh ratus lima puluh rupiah. Hati-hati di jalan.

**Daftar pelafalan berisiko (dari Claude):** "Insentif" (pastikan tekanan wajar), "Riwayat" (bukan "ri-wa-yat" terpatah), nama menu aplikasi dalam bahasa Inggris (jika ada).

**Pelajaran:** Naskah baru berdurasi ±40 detik dan **mengulang pesan inti** karena pendengar tidak bisa membaca ulang. Nomor SK dihapus dari audio dan tetap tersedia di teks pendamping. Prinsipnya: **audio untuk memahami, teks untuk rujukan**. Pesan suara yang bisa didengar sambil beristirahat menjangkau kurir yang tidak pernah membaca pengumuman panjang.

### 🗣️ Catatan Fasilitator — Bab 7.1
- **Latihan (20 menit):** Peserta mengambil satu pengumuman HR nyata versi sintetis, mengubahnya dengan Formula SUARA bersama Claude, lalu menghasilkan audio di dua alat TTS. Pasangan peserta mendengarkan sekali saja dan menuliskan pesan inti yang mereka tangkap.
- **Pertanyaan diskusi:** *"Kelompok karyawan mana di organisasi Anda yang paling jarang terjangkau oleh komunikasi tertulis? Bagaimana suara bisa membantu?"*

---

# BAB 7.2 — Penguatan: Menyempurnakan Keluaran Suara

## 7.2.1 Overview Konsep

### a. Empat dimensi kendali suara

| Dimensi | Pengaruh | Contoh pengaturan |
|---|---|---|
| **Suara** (*voice*) | Usia, gender, karakter, aksen | Suara dewasa yang tenang untuk informasi K3; suara muda yang energik untuk rekrutmen |
| **Nada** (*tone*) | Emosi dan sikap | Hangat, tegas, empatik, antusias |
| **Kecepatan** (*rate*) | Kemudahan ditangkap | Lebih lambat untuk instruksi keselamatan dan angka; normal untuk konten umum |
| **Gaya bicara** (*style*) | Format penyampaian | Penyiar berita, percakapan santai, instruktur, *customer service* |

### b. Tiga cara mengendalikan suara

| Cara | Penjelasan | Ketersediaan |
|---|---|---|
| **Pilihan suara & pengaturan alat** | Memilih suara dan menggeser pengaturan seperti stabilitas atau ekspresi | Hampir semua alat |
| **Instruksi gaya dalam bahasa alami** | Menulis arahan seperti *"bicara dengan hangat dan perlahan, seperti instruktur yang sabar"* | Beberapa model TTS generasi baru |
| **SSML** (*Speech Synthesis Markup Language*) | Penanda standar untuk jeda, penekanan, kecepatan, dan cara membaca angka/tanggal | Didukung luas di layanan suara *cloud*; dukungan di alat lain bervariasi |

**Contoh SSML sederhana:**
```xml
<speak>
  Selamat pagi, rekan-rekan operator.
  <break time="500ms"/>
  Mulai minggu depan, pemeriksaan APD sebelum shift
  <emphasis level="strong">wajib</emphasis> dicatat di aplikasi.
  <prosody rate="90%">Helm, kacamata, sarung tangan, dan sepatu keselamatan.</prosody>
</speak>
```

> **Catatan:** Dukungan tag SSML berbeda antarplatform. Uji di alat yang Anda pakai, dan simpan versi naskah yang berhasil di Pustaka *Prompt*.

### c. TTS dalam aplikasi interaktif
- **Asisten suara dan *chatbot* layanan karyawan:** karyawan bertanya dengan suara atau teks, jawaban dibacakan.
- **Sistem telepon otomatis (IVR):** menu suara untuk menanyakan saldo cuti, status klaim, atau jadwal shift.
- ***Helpdesk* HR berbasis AI:** gabungan STT, LLM, dan TTS untuk menjawab pertanyaan umum dan meneruskan kasus ke petugas.

> **So-what:** Saat TTS dipakai dalam aplikasi interaktif, kualitasnya tidak lagi hanya ditentukan oleh "suara yang bagus". Yang menentukan adalah **desain percakapannya**: apakah pengguna paham pilihannya, bisa mengulang, dan bisa beralih ke manusia.

## 7.2.2 Framework & Formula

### Kartu Suara Brand

| Unsur | Isi | Contoh (*PT Baja Prima Manufaktur*, fiktif) |
|---|---|---|
| **Persona suara** | 3 kata sifat | Tenang, tegas, peduli |
| **Suara utama** | Karakter suara | Suara dewasa, jelas, tidak terlalu formal |
| **Kecepatan** | Normal dan lambat | Normal untuk informasi umum; 85–90% untuk instruksi K3 dan angka |
| **Sapaan & penutup baku** | Kalimat standar | Sapaan: *"Halo, rekan-rekan Baja Prima."* Penutup: *"Utamakan keselamatan. Terima kasih."* |
| **Kamus pelafalan** | Istilah internal dan ejaan fonetisnya | "LOTO" → "lo-to" dengan tekanan rata; "K3" → "ka-tiga" |
| **Dilarang** | Gaya yang tidak boleh dipakai | Nada bercanda untuk pesan keselamatan; suara meniru orang nyata tanpa persetujuan |
| **Label AI** | Kalimat keterbukaan | *"Pesan ini dibacakan oleh suara AI."* (di awal atau akhir, sesuai kebijakan) |

### Formula 3J: Desain Interaksi Suara

```
INTERAKSI SUARA = Jelas + Jeda + Jalan keluar
```

| J | Prinsip | Implementasi |
|---|---|---|
| **J1 – Jelas** | Pengguna selalu tahu di mana posisinya dan apa pilihannya | Maksimal 3–4 pilihan per menu; sebut pilihan sebelum nomornya (*"Untuk saldo cuti, tekan satu"*); ulangi dan konfirmasi informasi penting (*"Anda bertanya saldo cuti tahun 2026, benar?"*) |
| **J2 – Jeda** | Pengguna diberi waktu untuk memahami dan menjawab | Jeda setelah pertanyaan; bisa meminta ulang (*"Tekan sembilan untuk mendengar ulang"*); angka penting diucapkan perlahan |
| **J3 – Jalan keluar** | Pengguna selalu bisa beralih ke manusia | Pilihan *"tekan nol untuk petugas HR"* di setiap menu; eskalasi otomatis jika pengguna dua kali tidak dipahami atau menyebut kata sensitif |

> **Hubungan dengan Formula MAPAN (Modul 3):** Formula 3J adalah unsur **Aturan** dan **Naikkan** yang diterjemahkan ke interaksi suara. Asisten suara tetap membutuhkan Misi, Audiens, dan Pengetahuan yang jelas.

### Rubrik Ulasan Audio

| Kriteria | Pertanyaan | Skor 1–3 |
|---|---|---|
| **1. Akurasi isi** | Apakah informasi, angka, dan tanggal benar dan diucapkan dengan benar? | 1 = salah · 3 = akurat |
| **2. Kejelasan** | Apakah pesan inti tertangkap setelah didengar sekali? | 1 = tidak · 3 = jelas |
| **3. Pelafalan** | Apakah istilah internal, nama, dan singkatan diucapkan wajar? | 1 = mengganggu · 3 = wajar |
| **4. Nada & tempo** | Apakah nada sesuai pesan dan tempo nyaman? | 1 = tidak sesuai · 3 = sesuai |
| **5. Kesesuaian brand** | Apakah sesuai Kartu Suara Brand? | 1 = tidak · 3 = sesuai |
| **6. Tata kelola** | Apakah ada label AI, lisensi suara jelas, dan persetujuan jika memakai klon suara? | 1 = berisiko · 3 = aman |

**Kriteria layak siar:** total ≥15 dari 18, dan **tidak ada skor 1** pada kriteria 1 dan 6.

## 7.2.3 How To — Merancang *Helpdesk* Suara HR

**Langkah 1 — Pilih 3–5 pertanyaan paling sering** dari data tiket (misalnya dari Studi Kasus P, Modul 3). Jangan memulai dengan semua jenis pertanyaan.

**Langkah 2 — Rancang alur percakapan** dengan Claude memakai Formula 3J:
```
Rancang alur sistem telepon otomatis HR untuk operator pabrik dengan Formula 3J
(Jelas, Jeda, Jalan keluar). Layanan: cek saldo cuti, cek jadwal shift, status klaim
kacamata. Buat:
1. Diagram alur dalam bentuk teks (menu, pilihan, konfirmasi, eskalasi).
2. Naskah setiap prompt suara dengan Formula SUARA (kalimat ≤15 kata).
3. Daftar kondisi eskalasi ke petugas HR.
4. Naskah ketika sistem tidak memahami jawaban (percobaan ke-1 dan ke-2).
```

**Langkah 3 — Tetapkan Kartu Suara Brand** dan pilih suara di alat TTS atau platform telepon.

**Langkah 4 — Tentukan data yang boleh diakses.** Saldo cuti dan jadwal shift adalah data pribadi, sehingga diperlukan **verifikasi identitas** (misalnya nomor induk karyawan + PIN) sebelum informasi dibacakan.

**Langkah 5 — Uji dengan pengguna sasaran** di lingkungan nyata, misalnya kantin pabrik yang bising. Ukur: tingkat penyelesaian tanpa petugas, jumlah permintaan ulang, dan jumlah eskalasi.

**Langkah 6 — Ulas audio dengan Rubrik Ulasan Audio**, lalu perbaiki naskah dan pelafalan.

## 7.2.4 Studi Kasus & Contoh

### Studi Kasus AG — *Helpdesk* Telepon HR untuk Operator Pabrik (Manufaktur)
**Situasi:** *PT Baja Prima Manufaktur (fiktif)*, 1.800 karyawan, 70% di antaranya operator shift yang tidak memiliki email perusahaan. Pertanyaan saldo cuti dan jadwal shift menumpuk di loket HR Site, sehingga operator harus mengantre saat jam istirahat.

**✅ Alur percakapan (Formula 3J, disusun Claude):**
```
[Sapaan]  "Halo, rekan-rekan Baja Prima. Ini layanan HR otomatis. Suara ini adalah suara AI."
[Verifikasi] "Masukkan nomor induk karyawan Anda, lalu tekan pagar."
             "Sekarang masukkan PIN empat angka Anda."
[Menu]    "Untuk saldo cuti, tekan satu.
           Untuk jadwal shift minggu ini, tekan dua.
           Untuk status klaim kacamata, tekan tiga.
           Untuk bicara dengan petugas HR, tekan nol."
[Jawaban] "Sisa cuti tahunan Anda tahun ini adalah … delapan … hari.
           Untuk mendengar ulang, tekan sembilan. Untuk kembali ke menu, tekan bintang."
[Gagal 2x] "Maaf, saya belum menangkap pilihan Anda. Saya sambungkan ke petugas HR."
```

**Keputusan desain penting:**

| Keputusan | Alasan (lensa HR + AI) |
|---|---|
| **Verifikasi NIK + PIN** sebelum data pribadi dibacakan | Telepon bisa dipinjam orang lain; saldo cuti dan jadwal adalah data pribadi |
| **Hanya 3 layanan** di fase pertama | Menu panjang membingungkan di lingkungan bising; perluasan bertahap setelah terbukti dipakai |
| **Angka diucapkan lambat** dengan jeda | Salah dengar angka cuti menimbulkan keluhan dan sengketa |
| **Tekan nol selalu tersedia** | Kepercayaan operator tumbuh jika mereka tahu selalu bisa bicara dengan manusia |
| **Keterbukaan "suara AI"** di awal | Operator berhak tahu mereka tidak berbicara dengan petugas |

**Dampak yang ditargetkan *(asumsi untuk pilot)*:** 60% pertanyaan saldo cuti dan jadwal selesai tanpa petugas, dan antrean loket HR Site saat jam istirahat turun separuh.

**Pelajaran:** Untuk operator garis depan, **telepon biasa** dan suara AI bisa lebih inklusif daripada aplikasi canggih. Keberhasilan *helpdesk* suara ditentukan oleh **desain percakapan** (3J) dan **perlindungan data** (verifikasi), bukan oleh kecanggihan suaranya.

> **Catatan tata kelola:** Jika panggilan direkam untuk peningkatan layanan, beri tahu penelepon di awal panggilan dan tetapkan masa simpan rekaman sesuai kebijakan perusahaan dan **UU PDP**.

### 🗣️ Catatan Fasilitator — Bab 7.2
- **Latihan (30 menit):** Peserta membuat Kartu Suara Brand untuk perusahaan fiktif, merancang alur *helpdesk* suara 3 layanan dengan Formula 3J bersama Claude, lalu memainkan perannya: satu peserta membacakan alur sebagai "sistem", peserta lain menjadi "penelepon" yang sengaja salah tekan dan meminta ulang.
- **Pertanyaan diskusi:** *"Informasi HR apa yang aman dibacakan oleh sistem suara otomatis, dan informasi apa yang sebaiknya hanya disampaikan oleh petugas?"*

---

# BAB 7.3 — Penguasaan: Pengalaman Suara yang Dinamis

## 7.3.1 Overview Konsep

### a. *Voice cloning* dan suara yang dipersonalisasi
***Voice cloning*** membuat suara sintetis yang meniru suara orang tertentu dari contoh rekaman. Teknologinya kini mudah diakses, sehingga **risikonya juga meningkat**.

| Kegunaan sah | Risiko |
|---|---|
| Narasi pelatihan yang konsisten oleh *trainer* internal | Suara dipakai untuk pesan yang tidak disetujui pemiliknya |
| Pembaruan materi tanpa rekaman ulang | Pemilik suara keluar dari perusahaan, tetapi suaranya masih dipakai |
| Aksesibilitas, misalnya karyawan yang kehilangan suara akibat sakit | **Penipuan suara (*vishing*)**: suara pimpinan dikloning untuk meminta transfer dana atau data |

> **Prinsip dasar:** suara adalah **identitas**. Suara termasuk **data pribadi**, dan bila diolah untuk mengenali atau meniru seseorang, dapat tergolong **data biometrik** yang dilindungi lebih ketat oleh **UU PDP**. *Voice cloning* hanya boleh dilakukan dengan **persetujuan tertulis** (lihat Perjanjian Persetujuan Avatar & Suara di Modul 6).

### b. Asisten suara percakapan: dua arsitektur

| Aspek | **Arsitektur A — Bertingkat** (STT → LLM → TTS) | **Arsitektur B — Suara-ke-suara langsung** (*realtime voice*) |
|---|---|---|
| Cara kerja | Suara diubah menjadi teks, LLM (misalnya Claude, GPT, Gemini) menyusun jawaban teks, lalu TTS membacakannya | Satu model mendengar dan menjawab dalam suara secara langsung |
| Kelebihan | **Transkrip teks di setiap tahap** sehingga mudah diaudit; bebas memilih LLM dan suara; mudah memasang pengaman (filter, RAG, aturan eskalasi) | Respons lebih cepat dan percakapan terasa lebih alami (intonasi, interupsi) |
| Keterbatasan | Jeda respons lebih panjang | Lebih sulit diaudit dan dikendalikan; pilihan model dan suara lebih terbatas |
| Cocok untuk | Layanan HR yang memerlukan akurasi, jejak audit, dan rujukan kebijakan | Latihan percakapan, simulasi wawancara, interaksi yang mengutamakan kealamian |

> **Tegangan lensa AI vs HR:** lensa AI cenderung memilih Arsitektur B karena pengalaman pengguna terasa lebih alami. Lensa HR menuntut **jejak audit dan akurasi** untuk informasi yang memengaruhi hak karyawan. Pilihan yang sering paling seimbang: **Arsitektur A untuk layanan informasi HR**, dan **Arsitektur B untuk latihan dan simulasi** yang tidak menyangkut keputusan.

### c. Unsur percakapan suara yang alami
- **Pergantian giliran:** tahu kapan pengguna selesai berbicara.
- **Interupsi (*barge-in*):** pengguna bisa memotong jawaban yang panjang.
- **Konfirmasi:** mengulang informasi penting sebelum bertindak.
- **Jawaban ringkas:** jawaban suara harus jauh lebih pendek daripada jawaban teks; tawarkan rincian jika diminta.

### d. Pengalaman konten multikanal
TTS dapat digabungkan dengan alat AI lain agar **satu pesan otomatis tersedia di banyak kanal**: teks, pesan suara, pengumuman ruang publik, *podcast* internal, video (Modul 6), dan FAQ suara di portal. Contoh lain di luar HR: situs dengan perintah suara dan materi pemasaran interaktif yang bisa "berbicara" dengan pengunjung.

## 7.3.2 Framework & Formula

### Kanvas Asisten Suara (Kanvas Agen 5P Modul 3 + Lapisan Suara)

| Unsur | Pertanyaan kunci | Contoh |
|---|---|---|
| **P1 – Pemicu** | Bagaimana percakapan dimulai? | Teknisi menekan tombol di aplikasi dan berkata "Tanya SOP" |
| **P2 – Perkakas** | Alat dan data apa yang boleh diakses? | `cari_SOP` (baca saja), `cek_jadwal_servis` (baca saja, data teknisi sendiri) |
| **P3 – Proses** | Langkah percakapan dan aturan berhenti | Dengar → konfirmasi pertanyaan → cari → jawab ringkas → tawarkan rincian |
| **P4 – Persetujuan** | Tindakan apa yang butuh manusia? | Tidak ada tindakan tulis; pertanyaan di luar SOP → teruskan ke supervisor |
| **P5 – Pencatatan** | Apa yang dicatat? | Transkrip, SOP yang dirujuk, waktu; rekaman audio hanya jika disetujui |
| **+ Suara** | Arsitektur, Kartu Suara Brand, Formula 3J, keterbukaan AI | Arsitektur A; suara tenang; jawaban ≤3 kalimat; *"Saya asisten AI"* |

### Protokol Anti-Penipuan Suara (*Vishing*)

| Langkah | Isi |
|---|---|
| **1. Kebijakan tertulis** | "Perusahaan tidak pernah meminta transfer dana, kata sandi, atau data karyawan melalui telepon atau pesan suara saja." |
| **2. Verifikasi saluran kedua** | Setiap permintaan sensitif dikonfirmasi lewat saluran resmi lain (telepon balik ke nomor resmi, sistem persetujuan internal) |
| **3. Kata sandi verbal** | Untuk tim yang menangani dana atau data (Finance, Payroll, HRIS), tetapkan prosedur verifikasi internal |
| **4. Edukasi berkala** | Contoh rekaman suara palsu dalam pelatihan kesadaran keamanan |
| **5. Batasi bahan klon** | Kurangi publikasi rekaman suara panjang pimpinan yang tidak perlu |

## 7.3.3 How To — Membangun Pengalaman Suara Multikanal

**Langkah 1 — Mulai dari satu pesan inti** yang sudah disetujui (misalnya pengumuman program baru).

**Langkah 2 — Minta Claude membuat paket naskah per kanal:**
```
Dari pengumuman berikut, buat paket konten multikanal:
1. Teks WhatsApp (maks. 80 kata) + naskah pesan suara 45 detik (Formula SUARA).
2. Naskah pengumuman ruang publik 25 detik (toko/pabrik), diulang 2 kali dengan jeda.
3. Naskah segmen podcast internal 3 menit (dua pembawa acara, gaya percakapan).
4. 8 pasang tanya-jawab untuk FAQ suara (jawaban ≤3 kalimat, Formula SUARA).
5. Daftar pelafalan berisiko dan ejaan fonetisnya.
Pastikan semua angka dan tanggal konsisten di semua kanal.
```

**Langkah 3 — Pilih suara per kanal** sesuai Kartu Suara Brand. Satu suara utama untuk identitas, dengan variasi gaya per kanal.

**Langkah 4 — Hasilkan audio dan ulas** dengan Rubrik Ulasan Audio.

**Langkah 5 — Otomatiskan bila berulang.** Untuk pengumuman rutin, rangkaian ini dapat diotomatiskan melalui API: LLM menulis naskah dari templat, TTS menghasilkan audio, lalu sistem mendistribusikannya. **Tetap tempatkan persetujuan manusia sebelum distribusi**.

**Langkah 6 — Ukur:** tingkat didengar, pertanyaan lanjutan yang masuk, dan pemahaman (misalnya kuis singkat atau survei satu pertanyaan).

## 7.3.4 Studi Kasus & Contoh

### Studi Kasus AH — Asisten Suara *Hands-Free* untuk Teknisi Lapangan (B2B Industri)
**Situasi:** *PT Mitra Teknik Industri (fiktif)* memiliki 150 **Field Service Technician** (lanjutan Studi Kasus J dan P). Saat memperbaiki pompa di lokasi pelanggan, teknisi sering harus membuka PDF SOP setebal 80 halaman di ponsel dengan tangan berminyak. Mereka meminta "asisten yang bisa ditanya pakai suara".

**Tegangan yang harus diputuskan:**
- **Lensa AI:** asisten suara *realtime* (Arsitektur B) terasa paling alami dan cepat.
- **Lensa HR/K3:** jawaban SOP yang salah dapat menyebabkan kecelakaan. Jejak audit diperlukan, dan teknisi **tidak boleh** berinteraksi dengan ponsel saat mesin masih bertenaga.

**Keputusan desain (Kanvas Asisten Suara):**

| Unsur | Desain |
|---|---|
| **Arsitektur** | **A (STT → LLM → TTS)** agar setiap jawaban punya transkrip dan rujukan SOP |
| **Pengetahuan** | Hanya SOP resmi versi terbaru (RAG, Modul 3); tidak menjawab dari pengetahuan umum |
| **Jawaban** | Maksimal 3 kalimat, menyebut nomor bagian SOP; tawarkan "Mau saya bacakan langkah berikutnya?" |
| **Konfirmasi** | Ulangi pertanyaan untuk istilah teknis: *"Anda bertanya torsi baut casing pompa seri P-200, benar?"* |
| **Aturan keselamatan** | Asisten selalu mengingatkan: *"Pastikan LOTO sudah terpasang sebelum Anda mulai."* (lanjutan Studi Kasus AB, Modul 6) |
| **Jalan keluar** | Pertanyaan di luar SOP atau jika keyakinan rendah: *"Ini tidak ada di SOP. Saya hubungkan ke supervisor teknis."* |
| **Pencatatan** | Transkrip dan rujukan SOP disimpan; rekaman audio tidak disimpan |

**Contoh interaksi yang diharapkan:**
> **Teknisi:** "Torsi baut casing P-200 berapa?"
> **Asisten:** "Anda bertanya torsi baut casing pompa P-200, benar?"
> **Teknisi:** "Benar."
> **Asisten:** "Menurut SOP Servis P-200 bagian empat titik tiga, torsinya empat puluh lima newton meter, dikencangkan bersilang. Pastikan LOTO sudah terpasang. Mau saya bacakan langkah berikutnya?"

**Pelajaran:** Untuk informasi yang berdampak pada keselamatan, **auditabilitas dan akurasi lebih penting daripada kealamian percakapan**. Arsitektur bertingkat memberi transkrip dan rujukan SOP di setiap jawaban, sedangkan **konfirmasi pertanyaan** mencegah salah dengar istilah teknis yang mirip. Asisten suara membantu teknisi bekerja lebih aman dan cepat, **tanpa menggantikan supervisor teknis** untuk kasus di luar SOP.

### Studi Kasus AJ — Satu Pengumuman, Lima Kanal Suara (Praktik Utama Modul)
**Situasi:** *PT Sinar Ritel Nusantara (fiktif)* meluncurkan **program kesejahteraan baru**: konsultasi psikologis gratis dan bantuan biaya pendidikan anak untuk 3.000 karyawan di 120 toko. Pengalaman sebelumnya menunjukkan bahwa program serupa sepi peminat karena **pesannya tidak sampai** ke kru toko. Direktur HR mengusulkan, *"Bagaimana kalau suara saya dikloning supaya bisa menyapa langsung di semua kanal?"*

**Tahap 1 — Keputusan tentang klon suara Direktur HR**

| Pertimbangan | Lensa HR | Lensa AI |
|---|---|---|
| Kehadiran pimpinan | Suara direktur memberi bobot dan kepercayaan pada program | Klon suara memungkinkan banyak versi tanpa rekaman ulang |
| Autentisitas | Program kesehatan mental menyentuh hal pribadi; suara klon yang ketahuan bisa terasa tidak tulus | Kualitas klon tinggi, tetapi tetap perlu label AI |
| Risiko | Klon suara direktur menjadi bahan potensial penipuan suara | Akses ke klon harus dibatasi dan diaudit |

**Keputusan:** Direktur HR **merekam langsung satu pesan pembuka 45 detik** dengan suara aslinya untuk pesan utama yang emosional. Kanal lainnya memakai **suara AI bawaan** sesuai Kartu Suara Brand, dengan label *"dibacakan oleh suara AI"*. Klon suara direktur **tidak dibuat**. Alasannya: pesan yang membutuhkan kepercayaan disampaikan oleh suara asli, dan risiko *vishing* tidak sebanding dengan penghematannya.

**Tahap 2 — Paket konten multikanal (disusun Claude)**

| Kanal | Format | Suara | Isi utama |
|---|---|---|---|
| 1. Pesan pembuka | Audio 45 detik di WhatsApp dan portal | **Direktur HR (rekaman asli)** | Mengapa program ini ada, ajakan memakai tanpa rasa malu |
| 2. Pengumuman toko | Audio 25 detik, diputar sebelum toko buka | Suara AI (Kartu Suara Brand) | Dua manfaat program dan cara mendaftar |
| 3. Pesan suara mingguan | Audio 40 detik selama 4 minggu | Suara AI | Satu manfaat per minggu, contoh situasi nyata (fiktif) |
| 4. *Podcast* internal | Segmen 3 menit, dua pembawa acara | Dua suara AI berbeda | Tanya-jawab santai: "Apakah konsultasi ini rahasia?" |
| 5. FAQ suara di portal | Tanya dengan suara, dijawab suara (Arsitektur A) | Suara AI | 8 pertanyaan umum; pertanyaan pribadi diarahkan ke kanal rahasia konselor |

**Instruksi penting untuk kanal 5 (Formula MAPAN + 3J):**
```xml
<naikkan>
Jika pengguna menceritakan kondisi pribadi, kesehatan mental, atau keadaan darurat,
jangan memberi nasihat. Ucapkan dengan nada tenang:
"Terima kasih sudah bercerita. Untuk bicara langsung dan rahasia dengan konselor,
hubungi layanan konseling di nomor yang tertera di kartu karyawan Anda."
Jika pengguna menyebut ingin menyakiti diri sendiri, sampaikan nomor layanan darurat
yang ditetapkan perusahaan dan segera teruskan ke petugas yang ditunjuk.
Jangan menyimpan rekaman audio pertanyaan pengguna.
</naikkan>
```

**Tahap 3 — Ulasan dan persetujuan**

| Penyetuju | Fokus |
|---|---|
| HR Wellbeing | Kebenaran manfaat program, syarat, dan cara mendaftar (Rubrik kriteria 1) |
| Mitra konselor / psikolog | Nada dan kata-kata untuk topik kesehatan mental, alur eskalasi kanal 5 |
| Legal / DPO | Kerahasiaan, tidak menyimpan rekaman, label AI (kriteria 6) |
| Tim Brand | Kartu Suara Brand dan konsistensi antarkanal (kriteria 5) |

**Indikator keberhasilan *(target ilustratif)*:** pendaftar program naik **2×** dibanding program serupa sebelumnya, ≥50% kru toko mengenali program dalam survei satu pertanyaan, dan tidak ada keluhan kerahasiaan.

**Pelajaran:** Satu pesan inti menjadi **lima pengalaman suara** yang masing-masing sesuai konteks kanal. Keputusan paling strategis bukan soal teknologi, melainkan **suara siapa yang menyampaikan pesan apa**. Pesan yang membutuhkan kepercayaan disampaikan oleh suara manusia asli. Pesan informatif yang berulang dibantu suara AI dengan label yang jujur. Untuk topik sensitif seperti kesehatan mental, unsur **Jalan keluar** ke manusia dan larangan menyimpan rekaman adalah bagian dari desain, bukan tambahan.

### Tahap Akhir — Simpan ke Pustaka *Prompt*

| Kolom | Isi |
|---|---|
| **Nama & ID** | `HR-SUA-001 Naskah Suara & Desain Interaksi Suara HR (SUARA + 3J)` |
| **Versi** | v1.0 — 16/10/2026 |
| **Pemilik** | HR Communications Lead (bersama HR Service Delivery Lead) |
| **Teknik** | Formula SUARA + Formula KIT + Kartu Suara Brand + Formula 3J + Kanvas Asisten Suara + Rubrik Ulasan Audio |
| **Variabel** | `{{pesan_inti}}`, `{{audiens}}`, `{{kanal_dan_durasi}}`, `{{kamus_pelafalan}}`, `{{kontak_eskalasi}}` |
| **Platform diuji** | Claude ✅ (naskah, desain percakapan, LLM di Arsitektur A) · ElevenLabs ✅ · TTS OpenAI ✅ · Gemini TTS ✅ · Layanan suara *cloud* ✅ (SSML) |
| **Risiko & tata kelola** | Suara bawaan sebagai standar; klon suara hanya dengan Perjanjian Persetujuan. Label AI di setiap audio. Verifikasi identitas sebelum membacakan data pribadi. Rekaman percakapan hanya dengan pemberitahuan dan masa simpan yang jelas. Protokol anti-*vishing* dikomunikasikan ke seluruh karyawan. |

### 🗣️ Catatan Fasilitator — Bab 7.3
- **Praktik utama (35 menit):** Dalam kelompok, peserta menjalankan Studi Kasus AJ untuk satu program HR fiktif pilihan mereka. Mereka memutuskan suara siapa untuk pesan apa (termasuk perdebatan klon suara), meminta Claude menyusun paket naskah 5 kanal, menghasilkan minimal 2 audio, lalu mengulasnya dengan Rubrik Ulasan Audio.
- **Demonstrasi opsional:** Fasilitator mencoba **mode suara** di aplikasi Claude atau ChatGPT untuk menunjukkan percakapan *realtime*, lalu mendiskusikan perbedaannya dengan Arsitektur A.
- **Pertanyaan diskusi:** *"Jika besok ada pesan suara yang terdengar persis seperti direktur Anda dan meminta data gaji seluruh tim, apa yang harus dilakukan karyawan Anda, dan apakah mereka sudah tahu?"*

---

## Rangkuman Modul 7

| Bab | Formula/Kerangka | Satu kalimat inti |
|---|---|---|
| **7.1 Fondasi** | Peta teknologi & platform suara + kriteria pemilihan alat + **Formula SUARA** (Singkat, Urut, Angka dieja, Akrab, Ritme) | Sebagian besar kesalahan TTS berasal dari teks; tulis naskah untuk telinga, bukan untuk mata. |
| **7.2 Penguatan** | **Kartu Suara Brand** + instruksi gaya & SSML + **Formula 3J** (Jelas, Jeda, Jalan keluar) + **Rubrik Ulasan Audio** | Dalam aplikasi interaktif, desain percakapan dan perlindungan data lebih menentukan daripada kualitas suara. |
| **7.3 Penguasaan** | **Kanvas Asisten Suara** + dua arsitektur (bertingkat vs *realtime*) + **Protokol Anti-*Vishing*** | Pilih arsitektur sesuai kebutuhan audit, dan tentukan dengan sadar suara siapa yang menyampaikan pesan apa. |

## Kuis Singkat (Kunci Jawaban untuk Fasilitator)

1. **Apa sumber utama pelafalan TTS yang aneh?** → *Teks: singkatan, angka, tanggal, istilah asing, dan tanda baca yang ambigu.*
2. **Sebutkan lima unsur Formula SUARA.** → *Singkat, Urut, Angka dieja, Akrab, Ritme.*
3. **Mengapa pesan inti perlu diulang di akhir naskah audio?** → *Karena pendengar hanya mendengar sekali dan tidak bisa membaca ulang.*
4. **Apa itu SSML?** → *Speech Synthesis Markup Language, penanda standar untuk mengatur jeda, penekanan, kecepatan, dan cara membaca angka/tanggal; dukungannya bervariasi antarplatform.*
5. **Sebutkan tiga unsur Formula 3J.** → *Jelas, Jeda, Jalan keluar.*
6. **Apa kelebihan Arsitektur A (STT → LLM → TTS) dibanding suara-ke-suara langsung?** → *Ada transkrip teks di setiap tahap sehingga mudah diaudit, bebas memilih LLM dan suara, dan mudah memasang pengaman.*
7. **Apa syarat *voice cloning* suara karyawan atau pimpinan?** → *Persetujuan tertulis yang memuat ruang lingkup, tujuan, batasan isi, persetujuan naskah, masa berlaku, serta hak penarikan dan penghapusan.*
8. **Apa langkah utama mencegah penipuan suara (*vishing*)?** → *Kebijakan bahwa permintaan sensitif tidak pernah dilakukan lewat suara saja, verifikasi melalui saluran kedua, edukasi karyawan, dan membatasi bahan klon.*

## Tugas Portofolio (Modul Pilihan)
Kumpulkan **3 Kartu Pustaka *Prompt*** dari pekerjaan Anda sendiri (dengan perusahaan fiktif dan suara bawaan alat):
- 1 **naskah audio Formula SUARA** beserta teks asli "untuk mata", daftar pelafalan berisiko, audio dari minimal dua alat TTS, dan skor **Rubrik Ulasan Audio**,
- 1 **desain interaksi suara** (alur menu atau percakapan) dengan **Formula 3J** dan **Kartu Suara Brand**,
- 1 **Kanvas Asisten Suara** atau paket konten multikanal, lengkap dengan pilihan arsitektur dan alasannya dari lensa HR dan lensa AI.

Setiap kartu wajib mencantumkan alat yang dipakai, ketentuan lisensinya, dan label AI yang akan dipasang.

---
> **Catatan tata kelola:** Semua nama perusahaan dalam modul ini fiktif, dan angka target adalah **asumsi ilustratif**. Dalam praktik nyata, gunakan alat suara yang disetujui perusahaan dan mengizinkan penggunaan komersial. Beri tahu pengguna bahwa mereka mendengar atau berbicara dengan suara AI. Verifikasi identitas sebelum membacakan data pribadi, dan beri tahu penelepon jika percakapan direkam. *Voice cloning* hanya boleh dilakukan dengan **persetujuan tertulis** sesuai **UU Pelindungan Data Pribadi (UU PDP)**. Pastikan seluruh karyawan mengetahui protokol verifikasi untuk mencegah penipuan suara.

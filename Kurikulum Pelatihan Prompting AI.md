# Kurikulum Pelatihan Prompting AI
### Dari *Prompt* Dasar hingga Asisten AI Kustom dan Konten Multimodal — Berbasis Claude.ai dan LLM Terkemuka Lainnya

---

## Ringkasan Program

**Ide pokok:** Prompting adalah keterampilan kerja inti yang baru, bukan keterampilan teknis milik tim IT. Program ini membawa peserta dari menulis *prompt* yang jelas, ke merancang penalaran AI, sampai membangun asisten AI kustom yang aman untuk pekerjaan sehari-hari.

| Komponen | Keterangan |
|---|---|
| **Sasaran peserta** | Profesional HR, HRBP, *people analytics*, L&D, dan fungsi bisnis pendukung (pemasaran, penjualan, operasional) |
| **Prasyarat** | Pernah memakai salah satu asisten AI (Claude, ChatGPT, Gemini, atau Copilot) |
| **Platform utama** | **Claude.ai** (Anthropic); dibandingkan secara netral dengan **ChatGPT** (OpenAI), **Gemini** (Google), dan **Microsoft Copilot** |
| **Struktur** | 5 modul inti + 2 modul pilihan; setiap modul punya 3 jenjang: **Fondasi → Penguatan → Penguasaan** |
| **Format** | Lokakarya *hands-on*: 30% konsep, 70% praktik dengan kasus nyata |
| **Estimasi durasi** | Modul inti ±4 hari efektif (±6 jam per modul); modul pilihan ±3 jam per modul *(asumsi; sesuaikan dengan kebutuhan klien)* |

> **Catatan:** Fitur dan nama produk AI berubah cepat. Fasilitator wajib mengecek ulang nama fitur dan ketersediaannya di setiap platform sebelum sesi dimulai.

---

## Glosarium Pemetaan Istilah

Tabel ini menyelaraskan istilah dari materi referensi dengan istilah yang dipakai di Claude.ai dan LLM lain. Istilah di kolom tengah adalah istilah baku yang dipakai di seluruh kurikulum.

| Istilah di Materi Referensi | Istilah di Claude.ai / Anthropic | Padanan di LLM Lain |
|---|---|---|
| *Prompt engineering* | *Prompt engineering*; *system prompt* | Sama di semua platform |
| *AI processes language input* | **Token**, **jendela konteks** (*context window*) | Token, *context length* |
| *Zero-shot / few-shot learning* | *Zero-shot / few-shot / multishot prompting* (contoh dibungkus *tag* XML `<example>`) | Sama |
| *Prompt structuring* | **Tag XML** (`<konteks>`, `<instruksi>`, `<data>`), **prefill** jawaban | Markdown/delimiter (GPT), *structured prompt* (Gemini) |
| *Chain-of-Thought (CoT)* | **Extended Thinking** (mode berpikir), *tag* `<thinking>` | *Reasoning/Thinking mode* (GPT), *Thinking* (Gemini) |
| *Tree-of-Thought (ToT)* | Prompt ToT + *Extended Thinking*; **Research** untuk eksplorasi multisumber | *Deep Research* (ChatGPT & Gemini) |
| *Meta-prompting* | **Prompt Generator / Prompt Improver** (Anthropic Console) | GPT Builder, *"Help me write"* |
| *Custom ChatGPT / CustomGPT* | **Projects** (instruksi + *project knowledge*), **Skills**, **Styles** | **Custom GPTs**, **Gems** (Gemini), **Copilot Studio Agents** |
| *Train the GPTs with datasets* | **Bukan pelatihan model** — melainkan *project knowledge* / **RAG** (*retrieval*) + instruksi kustom | *Knowledge files* (GPTs), *Gem knowledge*, **NotebookLM** |
| *Integration with APIs* | **Claude API**, **Tool Use** (*function calling*), **Connectors / MCP** (*Model Context Protocol*) | OpenAI API & *Actions*, Gemini API & *Extensions* |
| *Multi-step workflows* | **Agen AI** (*agentic workflow*), Claude Code, *Agent SDK* | *Agent mode* (ChatGPT), Gemini Agent |
| *Entity recognition, sentiment analysis* | **Ekstraksi terstruktur** & klasifikasi lewat *prompt* (*structured output* / JSON) | *Structured outputs / JSON mode* |
| *Dummy data* | **Data sintetis** dibuat di **Artifacts** atau *code execution / analysis tool* | *Data Analysis* (ChatGPT), Canvas (Gemini) |
| *Text-to-image (DALL·E, MidJourney)* | Claude **tidak membuat gambar**; Claude berperan sebagai **perancang prompt visual** dan **pengulas gambar** (*vision*) | Pembuatan gambar di ChatGPT, Gemini (Imagen), Midjourney, Adobe Firefly |
| *Inpainting / outpainting* | — (rancang instruksi edit di Claude) | Edit gambar via percakapan (ChatGPT/Gemini), *Generative Fill / Expand* (Firefly) |
| *Text-to-video (Pictory, RunwayML)* | Claude untuk **naskah & storyboard** | Sora (OpenAI), Veo (Google), Runway, Synthesia, HeyGen |
| *Text-to-speech (TTS)* | **Mode suara** (*voice mode*) di aplikasi Claude | *Voice mode* ChatGPT, Gemini Live/TTS, ElevenLabs |
| *AI hallucination / limitations* | **Halusinasi**, *grounding* dengan sumber, sitasi | Sama |

---

## Peta Kurikulum

```
JENJANG 1 — FONDASI            JENJANG 2 — PENGUATAN             JENJANG 3 — PENGUASAAN
───────────────────────────    ──────────────────────────────    ──────────────────────────────
M1  Prompt yang efektif     →  Prompt terstruktur & spesifik  →  Meta-prompting
M2  Dasar penalaran (CoT)   →  Eksplorasi solusi (ToT)        →  Kombinasi CoT + ToT untuk strategi
M3  Mengenal LLM & batasnya →  Projects / Gems / GPTs         →  Skills, API, MCP & alur kerja agen
M4  Konsep data sintetis    →  Kustomisasi format & tipe data →  Simulasi skala penuh
M5  Dasar teks-ke-gambar    →  Edit & perluasan gambar        →  Narasi visual sesuai brand
─────────────────────────── MODUL PILIHAN ───────────────────────────
M6  Teks-ke-video           M7  Teks-ke-suara
```

**Urutan yang disarankan:** M1 → M2 → M4 → M3 → M5 (→ M6/M7). M4 sengaja diletakkan sebelum M3 agar peserta sudah punya data sintetis yang aman untuk melatih asisten kustom mereka di M3.

---

## Modul 1 — Prompting Efektif dan Lanjutan
*(Referensi: Effective and Advance Prompting)*

**Tujuan pembelajaran:** Peserta mampu menyusun *prompt* yang jelas, terstruktur, dan bisa dipakai ulang sehingga hasilnya konsisten di Claude, ChatGPT, maupun Gemini.

### 1.1 Fondasi — Memahami Cara LLM Membaca *Prompt*
- Memahami inti *prompt engineering*: memberi model **peran, konteks, tugas, format, dan batasan** yang jelas.
- Memahami cara LLM memproses masukan: **token**, **jendela konteks**, dan alasan model "lupa" pada percakapan yang terlalu panjang.
- Mempraktikkan teknik dasar **zero-shot** dan **few-shot (multishot) prompting**.
- Mengenal perbedaan **prompt pengguna** dan **system prompt / instruksi kustom**.

### 1.2 Penguatan — *Prompt* yang Lebih Spesifik dan Presisi
- Menyusun *prompt* kompleks dengan **tag XML** (`<konteks>`, `<data>`, `<instruksi>`, `<format_keluaran>`), yaitu praktik yang disarankan Anthropic untuk Claude.
- Memakai teknik **prefill** (mengisi awal jawaban) dan **format keluaran terstruktur** (tabel, JSON, kerangka memo).
- Mengarahkan model agar mengikuti proses berpikir tertentu, misalnya "analisis dulu, baru rekomendasi".
- Penerapan per fungsi: deskripsi jabatan, kebijakan HR, balasan layanan karyawan, dan materi pemasaran rekrutmen.

### 1.3 Penguasaan — Pengantar Prompting Lanjutan
- Pengantar **Chain-of-Thought** dan **Extended Thinking** (didalami di Modul 2).
- Pengantar **Tree-of-Thought** untuk menghasilkan beberapa alternatif solusi.
- **Meta-prompting**: meminta AI menyusun atau memperbaiki *prompt*, termasuk memakai **Prompt Generator / Prompt Improver** di Anthropic Console, lalu mengujinya di beberapa model.
- Membangun **pustaka *prompt*** tim (*prompt library*) yang terdokumentasi dan terkontrol versinya.

**Praktik utama:** Ubah satu *prompt* "satu kalimat" menjadi *prompt* terstruktur dengan XML, lalu bandingkan hasilnya di Claude, ChatGPT, dan Gemini.
**Pertanyaan diskusi fasilitator:** *"Bagian mana dari prompt Anda yang paling memengaruhi kualitas jawaban: peran, contoh, atau format?"*

---

## Modul 2 — Penalaran AI: Chain-of-Thought & Tree-of-Thought
*(Referensi: CoT and ToT Prompting)*

**Tujuan pembelajaran:** Peserta mampu mengarahkan AI agar bernalar bertahap (CoT) dan menjelajahi beberapa jalur solusi (ToT) untuk masalah bisnis yang kompleks, serta tahu kapan memakai **mode berpikir (*Extended Thinking*)**.

### 2.1 Fondasi — Prinsip Penalaran AI
- Memahami cara LLM memproses informasi secara berurutan (*next-token prediction*) dan mengapa "berpikir dulu" meningkatkan akurasi.
- Memahami cara **Chain-of-Thought** memecah tugas menjadi langkah logis, baik lewat *prompt* ("pikirkan langkah demi langkah di dalam `<thinking>`") maupun lewat **Extended Thinking** di Claude atau mode *reasoning/thinking* di GPT dan Gemini.
- Mempraktikkan CoT sederhana: merangkum hasil survei keterlibatan karyawan dan mengekstrak data dari CV.
- Menerapkan CoT pada alur kerja kompleks: analisis *turnover*, penyusunan laporan, dan pemecahan masalah bisnis.

### 2.2 Penguatan — Meningkatkan Kemampuan Penalaran
- Mendalami **Tree-of-Thought**: AI mengembangkan beberapa jalur pemikiran, menilainya, lalu memilih yang terbaik.
- Menghasilkan beberapa solusi untuk satu masalah, misalnya tiga opsi strategi retensi beserta pro-kontranya.
- Menguji CoT dan ToT pada tugas kreatif: kampanye *employer branding* dan strategi bisnis.
- Memanfaatkan fitur **Research** (Claude) atau **Deep Research** (ChatGPT/Gemini) untuk eksplorasi multisumber yang disertai sitasi.

### 2.3 Penguasaan — Memecahkan Masalah Kompleks
- Menerapkan CoT dan ToT pada skenario lanjutan: **pemetaan *employee/customer journey***, desain program pengembangan, dan ideasi konten.
- Menggabungkan CoT dan ToT dalam alur kerja berlapis: ToT untuk **perencanaan**, CoT untuk **eksekusi**.
- Memakai ToT untuk **strategi jangka panjang** dan perencanaan tenaga kerja (*strategic workforce planning*).
- **Verifikasi penalaran:** meminta AI mengkritik jawabannya sendiri (*self-critique*) dan mengecek angka.

**Praktik utama:** Masalah "attrition tinggi di 3 posisi kritis" diselesaikan dengan ToT (3 hipotesis), lalu CoT untuk mengeksekusi hipotesis yang terpilih.
**Pertanyaan diskusi fasilitator:** *"Kapan mode berpikir justru membuang waktu dan biaya? Tugas apa yang cukup dengan prompt biasa?"*

---

## Modul 3 — Asisten AI Kustom & Integrasi
*(Referensi: Custom ChatGPT & Integration)*

**Tujuan pembelajaran:** Peserta mampu membangun asisten AI kustom untuk proses kerja spesifik (Claude **Projects/Skills**, ChatGPT **Custom GPTs**, Gemini **Gems**) dan memahami pola integrasinya lewat API dan **MCP**.

### 3.1 Fondasi — Mengenal LLM dan Asisten AI
- Memahami cara model bahasa seperti **Claude, GPT, dan Gemini** menghasilkan teks dan alasan mereka efektif.
- Memakai asisten AI dalam berbagai konteks: menyusun email, memo, laporan, dan *artifacts* (dokumen/aplikasi interaktif di Claude).
- Mengenali batasan model bawaan: halusinasi, pengetahuan dengan batas tanggal (*knowledge cutoff*), dan tidak memahami konteks perusahaan, sehingga kustomisasi diperlukan.

### 3.2 Penguatan — Mengkustomisasi Asisten AI
- Menyusun **instruksi kustom / *system prompt*** agar akurat di domain tertentu, misalnya istilah HR atau regulasi ketenagakerjaan Indonesia.
- Mengatur **nada, gaya, dan format** sesuai tugas dan audiens memakai **Styles** di Claude.
- Membuat **Claude Project** berisi instruksi dan **project knowledge** (kebijakan, SOP, *template*), lalu membandingkannya dengan **Custom GPT** dan **Gem**.
- Merancang alur kerja multilangkah: menjawab pertanyaan karyawan dan menyusun dokumen (surat penawaran, ringkasan wawancara).

### 3.3 Penguasaan — Membangun dan Mengintegrasikan Asisten AI
- **Meluruskan miskonsepsi:** Projects, GPTs, dan Gems **tidak melatih ulang model**. Ketiganya memakai **retrieval (RAG)** dari dokumen yang diunggah ditambah instruksi. *Fine-tuning* adalah pendekatan terpisah yang jarang diperlukan.
- Mengemas keahlian yang bisa dipakai ulang sebagai **Skills** (paket instruksi + berkas + skrip) di Claude.
- Integrasi lewat **Claude API**, **Tool Use (*function calling*)**, dan **Connectors/MCP** untuk menghubungkan AI ke HRIS, email, kalender, atau *drive* guna mengotomatiskan layanan karyawan, email pemasaran, dan kurasi konten.
- Teknik pemrosesan bahasa lewat *prompt*: **ekstraksi entitas**, **analisis sentimen**, dan klasifikasi dengan **keluaran terstruktur (JSON)**.
- Merancang **alur kerja agen AI** lintas departemen (HR, pemasaran, penjualan), lengkap dengan titik **persetujuan manusia (*human-in-the-loop*)**.

**Praktik utama:** Bangun "Asisten Kebijakan HR" di Claude Projects dengan dokumen kebijakan **sintetis** dari Modul 4, lalu uji dengan 10 pertanyaan sulit.
**Pertanyaan diskusi fasilitator:** *"Keputusan apa yang TIDAK boleh diserahkan ke asisten AI ini? Bagaimana jejak auditnya?"*

---

## Modul 4 — Membuat Data Sintetis (*Dummy Data*)
*(Referensi: Generating Dummy Data)*

**Tujuan pembelajaran:** Peserta mampu membuat data sintetis yang realistis untuk pengujian, pelatihan, dan simulasi **tanpa memakai data pribadi karyawan yang asli**.

### 4.1 Fondasi — Pentingnya Data Sintetis
- Memahami apa itu *dummy data* / **data sintetis** dan kegunaannya untuk pengujian dan pengembangan.
- Memahami cara AI mengotomatiskan pembuatan data sintetis untuk menguji alur kerja atau menyimulasikan skenario bisnis.
- **Alasan utama di HR:** melindungi **data pribadi (PII)** sesuai **UU Pelindungan Data Pribadi (UU PDP)**. Data asli karyawan tidak boleh dimasukkan ke alat AI yang tidak disetujui perusahaan.
- Kegunaan lintas fungsi: data karyawan, pelamar, penjualan, dan pelanggan.

### 4.2 Penguatan — Kustomisasi Data Sintetis
- Membuat data dalam berbagai format (**CSV, JSON, Excel**) memakai **Artifacts** dan **code execution / analysis tool** di Claude, atau *Data Analysis* di ChatGPT.
- Menghasilkan beragam tipe data: **numerik** (gaji, skor kinerja), **kategorikal** (departemen, grade), dan **deret waktu** (absensi, *headcount* bulanan).
- Memodifikasi data untuk kondisi uji tertentu: *outlier*, data hilang, dan distribusi miring untuk *stress-test*.
- Menjaga **konsistensi logis** data, misalnya tanggal masuk sebelum tanggal promosi dan gaji sesuai *grade*.

### 4.3 Penguasaan — Data Sintetis Skala Besar
- Membuat data sintetis berfidelitas tinggi yang meniru skenario nyata: perusahaan 5.000 karyawan, kampanye rekrutmen, atau peluncuran produk.
- Mengintegrasikan pembuatan data ke alur kerja AI yang menyimulasikan interaksi pengguna, pembelian, atau respons pasar.
- Memakai data sintetis untuk **augmentasi data** guna memperkaya analisis, sambil mengenali risikonya: bias yang ikut tereplikasi dan pola yang terlalu "rapi".
- Membuat skrip pembangkit data yang bisa dipakai ulang (Python di Claude Artifacts/Claude Code) daripada menyalin-tempel tabel.

**Praktik utama:** Buat dataset 500 karyawan sintetis (CSV) dengan pola *attrition* tersembunyi, lalu minta peserta lain menemukannya memakai teknik Modul 2.
**Pertanyaan diskusi fasilitator:** *"Bagaimana Anda membuktikan ke auditor bahwa data ini benar-benar sintetis?"*

---

## Modul 5 — Teks-ke-Gambar: *Inpainting* dan *Outpainting*
*(Referensi: Inpainting and outpainting (Text to Image))*

**Tujuan pembelajaran:** Peserta mampu merancang *prompt* visual dan memakai alat pembuat gambar AI untuk konten komunikasi dan *employer branding*, termasuk mengedit dan memperluas gambar.

> **Catatan platform:** Claude **tidak membuat gambar**, tetapi sangat kuat untuk **menyusun *prompt* visual**, membuat diagram/ilustrasi berbasis kode (SVG di Artifacts), dan **mengulas gambar** (*vision*). Pembuatan gambar dipraktikkan di ChatGPT, Gemini, Midjourney, atau Adobe Firefly.

### 5.1 Fondasi — Alat AI untuk Tujuan Kreatif
- Mempelajari dasar teks-ke-gambar di berbagai platform: pembuat gambar ChatGPT, **Gemini (Imagen)**, Midjourney, dan **Adobe Firefly**.
- Menyusun anatomi *prompt* visual: **subjek, gaya, komposisi, pencahayaan, warna, tekstur, rasio aspek**.
- Memakai Claude sebagai **"art director"**: menerjemahkan *brief* kampanye menjadi *prompt* visual yang rinci.
- Penerapan umum: konten media sosial, poster lowongan, dan materi *branding* internal.

### 5.2 Penguatan — Praktik Kreatif dengan AI
- **Inpainting**: mengganti atau memperbaiki bagian tertentu gambar, lewat **edit gambar berbasis percakapan** (ChatGPT/Gemini) atau **Generative Fill** (Firefly).
- **Outpainting**: memperluas bidang gambar untuk banner atau format lain lewat **Generative Expand**.
- Mengasah *prompt* secara iteratif agar hasilnya spesifik dan layak dipakai secara komersial.
- Memakai **kemampuan *vision*** Claude untuk mengulas hasil gambar dan menyarankan perbaikan *prompt*.

### 5.3 Penguasaan — Menguasai AI Kreatif
- Menggabungkan *inpainting* dan *outpainting* menjadi **narasi visual** kampanye yang utuh.
- Mengintegrasikan teks-ke-gambar dengan alat AI lain untuk produksi konten dari awal sampai akhir: gambar untuk blog, video, dan presentasi.
- Menyesuaikan gambar dengan **pedoman brand** (warna, gaya, logo) agar konsisten di semua kanal.
- **Tata kelola:** hak cipta, label "dibuat dengan AI", representasi yang inklusif, dan larangan meniru orang atau merek nyata.

**Praktik utama:** Claude menyusun 5 *prompt* visual dari satu *brief* *employer branding*, lalu peserta membuat dan mengedit gambarnya di alat pilihan.
**Pertanyaan diskusi fasilitator:** *"Bagaimana menjaga gambar AI tetap autentik dan tidak terlihat 'stock photo generik'?"*

---

## Modul Pilihan 6 — Pembuatan Video dengan AI (Teks-ke-Video)
*(Referensi: AI Powered Text to Video Creation)*

**Tujuan pembelajaran:** Peserta mampu membuat video pendek berbasis AI untuk pelatihan, *onboarding*, dan komunikasi, dari naskah hingga distribusi.

### 6.1 Fondasi — Mengubah Kata Menjadi Visual
- Memahami teknologi dan platform teks-ke-video: **Sora** (OpenAI), **Veo** (Google), **Runway**, **Pictory**, serta video avatar seperti **Synthesia** dan **HeyGen**.
- Memakai Claude/ChatGPT/Gemini untuk menyusun **naskah, storyboard, dan *shot list*** sebelum masuk ke alat video.
- Mengenali batasan: kontrol kualitas, konsistensi karakter, durasi, dan kustomisasi.

### 6.2 Penguatan — Kustomisasi Video AI
- Mengintegrasikan elemen brand: logo, warna, dan *font*.
- Penerapan nyata: video *onboarding*, demo produk, dan modul *microlearning*.
- Menyesuaikan format untuk tiap kanal (YouTube, Instagram, LinkedIn, LMS internal).

### 6.3 Penguasaan — Cerita Berbasis AI yang Memikat
- Membuat kampanye video yang dipersonalisasi untuk audiens tertentu.
- Membuat video untuk kebutuhan lanjutan: peluncuran program, acara perusahaan, dan komunikasi skala besar.
- Mengintegrasikan video ke pengalaman interaktif seperti kuis dan modul *e-learning*.
- **Tata kelola:** persetujuan tertulis untuk avatar wajah atau suara karyawan, label konten AI, dan risiko *deepfake*.

---

## Modul Pilihan 7 — Pembuatan Suara dengan AI (*Text-to-Speech*)
*(Referensi: Text to Speech Generation)*

**Tujuan pembelajaran:** Peserta mampu memakai TTS dan suara AI untuk konten audio, asisten suara, dan layanan karyawan.

### 7.1 Fondasi — Menghidupkan Teks dengan Suara AI
- Memahami teknologi dan platform TTS: **ElevenLabs**, TTS OpenAI, **Gemini TTS/Live**, dan **mode suara** di aplikasi Claude dan ChatGPT.
- Menyusun naskah pendek yang "enak didengar" untuk konten media sosial atau video penjelasan, dengan bantuan Claude.
- Membandingkan alat TTS dari sisi bahasa Indonesia, intonasi, dan lisensi.

### 7.2 Penguatan — Menyempurnakan Keluaran Suara
- Mengatur suara, nada, kecepatan, dan gaya bicara untuk berbagai kebutuhan.
- Memakai TTS untuk aplikasi interaktif seperti asisten suara dan *chatbot* layanan karyawan.
- Mengintegrasikan TTS ke layanan yang langsung berhadapan dengan pengguna: sistem telepon otomatis dan *helpdesk* HR berbasis AI.

### 7.3 Penguasaan — Pengalaman Suara yang Dinamis
- Kustomisasi lanjutan: **voice cloning** dan suara AI yang dipersonalisasi, **hanya dengan persetujuan tertulis pemilik suara**.
- Mengintegrasikan TTS dengan AI percakapan (*voice mode / realtime voice*) agar interaksi terasa alami.
- Menggabungkan TTS dengan alat AI lain untuk pengalaman konten multikanal yang otomatis: situs dengan perintah suara dan materi pemasaran interaktif.

---

## Tata Kelola & Etika AI (Lintas Modul)

Setiap modul wajib menyentuh lima prinsip berikut:

1. **Data pribadi:** jangan memasukkan data karyawan asli ke alat AI yang tidak disetujui perusahaan (risiko *shadow AI*). Pakai data sintetis atau versi *enterprise* yang sesuai UU PDP.
2. **Verifikasi manusia:** semua keluaran AI yang memengaruhi keputusan tentang orang (rekrutmen, kinerja, kompensasi, PHK) wajib ditinjau manusia.
3. **Halusinasi:** minta sumber dan sitasi, lalu cek fakta dan angka sebelum dipakai.
4. **Transparansi:** beri label pada konten yang dibuat dengan AI, terutama gambar, video, dan suara.
5. **Bias:** uji *prompt* dan keluaran terhadap bias gender, usia, suku, dan disabilitas.

---

## Asesmen & Sertifikasi

| Komponen | Bobot | Bentuk |
|---|---|---|
| Kuis konsep per modul | 20% | Pilihan ganda & studi kasus singkat |
| Portofolio *prompt* | 30% | Pustaka minimal 10 *prompt* terdokumentasi (sebelum–sesudah) |
| Proyek akhir | 40% | Membangun asisten AI kustom (Claude Project / GPT / Gem) untuk satu proses kerja nyata memakai data sintetis |
| Refleksi tata kelola | 10% | Analisis risiko dan titik *human-in-the-loop* dari proyek akhir |

**Kriteria lulus:** nilai total ≥ 75 dan proyek akhir lolos uji 10 pertanyaan sulit tanpa pelanggaran tata kelola.

---

## Catatan Penyelarasan dari Materi Referensi

- **"Train the GPTs"** diganti menjadi **membangun dan mengintegrasikan** asisten AI. Projects, GPTs, dan Gems tidak melatih model; mereka memakai *retrieval* dan instruksi.
- **Materi Text to Speech** di referensi memuat dua butir yang tertukar dari materi video (teks-ke-video, Pictory/RunwayML). Di kurikulum ini butir tersebut **diperbaiki** menjadi konteks TTS.
- **Teks-ke-gambar** diberi catatan bahwa Claude tidak membuat gambar, sehingga peran Claude difokuskan pada perancangan *prompt* visual dan ulasan gambar.
- Contoh lintas fungsi (pemasaran, layanan pelanggan) dipertahankan, ditambah **contoh HR** agar sesuai dengan sasaran peserta.

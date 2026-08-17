# Solusi Transformasi Strategis ServeNow Technologies
**Studi Kasus BIzzIT COMPFEST 18**

---

## 1. Executive Summary

ServeNow Technologies, startup penyedia platform *omnichannel customer service*, sedang mengalami tekanan profitabilitas dengan margin laba bersih turun ke angka 2,5% dan *churn rate* mencapai 16,7%. Di sisi internal, perusahaan menghadapi krisis kedisiplinan akibat ketiadaan sistem manajemen kinerja, serta jajaran direksi (C-Level) yang terjebak dalam operasional teknis harian. Tim *sales* yang minim juga belum memiliki alur kerja yang terstruktur.

Dengan mengusulkan transformasi komprehensif berbasis **"Single-Number GenAI Omnichannel"**. Solusi ini mengintegrasikan AI (*Large Language Model* dan *Retrieval-Augmented Generation*) melalui **n8n** dan **Qdrant** untuk otomatisasi interaksi, dipadukan dengan **SLA-Driven Dashboard**. Inovasi teknis ini akan menekan biaya pihak ketiga (API WhatsApp) secara drastis, yang secara langsung menargetkan kenaikan margin laba menjadi 15-20%. Secara internal, sistem ini diimplementasikan secara *dogfooding* (digunakan oleh ServeNow sendiri) untuk menyelesaikan masalah tata kelola SDM, merestrukturisasi operasional, dan memfokuskan tim *sales* pada *closing* (penutupan penjualan) guna mencapai target ekspansi pendapatan 40% di luar Jabodetabek.

---

## 2. Analisis Masalah Prioritas (Gap Analysis)

1.  **Tata Kelola & SDM:** Budaya kerja fleksibel tanpa sistem *tracking* performa yang mengikat menyebabkan pekerjaan melewati tenggat waktu dan sulitnya menghubungi karyawan. Hal ini berdampak pada kenaikan keluhan layanan kritis pelanggan hingga 43 kasus pada tahun ketiga.
2.  **Manajemen Rangkap Jabatan (Bottleneck):** CEO, CTO, dan COO merangkap tugas operasional teknis, persetujuan harga, hingga penanganan pelanggan. Hal ini mengorbankan fokus pada strategi ekspansi bisnis.
3.  **Infrastruktur Penjualan Lemah:** Data *leads* (prospek) tersebar (WhatsApp, *spreadsheet*), *follow-up* tidak konsisten, dan penjualan bergantung pada relasi pribadi pendiri.
4.  **Inefisiensi Biaya (Margin Menyusut):** Pertumbuhan pendapatan (Rp15,8 miliar) diiringi beban infrastruktur *routing* pihak ketiga yang mahal, menekan laba bersih.

---

## 3. Pilar 1: Perbaikan Tata Kelola & Struktur Organisasi

**Tujuan:** Membebaskan direksi dari pekerjaan teknis, menciptakan kedisiplinan berbasis sistem, dan memastikan *Service Level Agreement* (SLA) minimal 96% tercapai.

### A. Solusi Teknis: "SLA-Driven Dashboard Inbox" (Dogfooding)
Daripada bergantung pada aplikasi absensi konvensional, ServeNow harus menggunakan produknya sendiri untuk operasional internal:
*   **Sentralisasi Pekerjaan:** Seluruh tugas, komunikasi internal, dan tiket pelanggan dipusatkan di *Dashboard Console*, bukan grup WhatsApp pribadi yang informal.
*   **Sistem Fan-Out & First-Claim-Wins:** Pekerjaan (tiket) masuk ke dasbor dan dapat dilihat oleh seluruh agen di divisi tersebut. Agen yang luang harus menekan tombol "Claim" untuk bekerja (`mode = HUMAN`). Ini mencegah tumpang tindih pekerjaan.
*   **SLA Escalation Timer:** Setiap tiket dilengkapi waktu mundur (*countdown*). Contoh: 5-10 menit untuk prospek *sales*, 10-15 menit untuk komplain. Jika agen mengabaikan batas waktu, status bergeser menjadi *SLA Breach* dan notifikasi dikirim langsung ke atasan (*Manager/Team Lead*) secara otomatis.

### B. Restrukturisasi Peran (Menutup Gap Kepemimpinan)
*   **Vice President (VP) / C-Level:** Hanya memantau dasbor analitik makro (Tren Churn, Pendapatan, Kinerja Regional). Terbebas penuh dari tiket operasional harian.
*   **Team Lead (TL) / Manager:** Bertindak sebagai *controller*. Hanya turun tangan jika ada *SLA Breach* (eskalasi otomatis dari sistem) dan melakukan peninjauan (*Review/QA*) atas transkrip kerja (`message` table) timnya.
*   **Team Member (Agent/Sales):** Menjadi eksekutor murni yang menyelesaikan antrean tiket pada *dashboard* divisinya. Kinerja diukur objektif dari kecepatan respons (SLA), bukan sekadar absensi.

---

## 4. Pilar 2: Inovasi & Roadmap Pengembangan Produk

**Tujuan:** Menghadirkan produk AI hemat biaya, menurunkan waktu implementasi menjadi 6-10 minggu, dan memiliki USP (*Unique Selling Proposition*) yang kuat melawan kompetitor global dan lokal.

### A. Arsitektur "Single-Number Branch Solution" dengan GenAI
*   **Pemangkasan Biaya (Zero WA Handoff Cost):** Sistem lama menggunakan grup WhatsApp berbayar untuk mendistribusikan *leads* ke staf. Solusi baru ini menggunakan **Satu Nomor Induk** untuk pelanggan. Koordinasi antar-staf dipindahkan murni ke aplikasi *web/dashboard* (gratis). ServeNow dan kliennya hanya membayar biaya Meta API saat staf benar-benar membalas pesan ke pelanggan.
*   **n8n Orchestrator:** Bertindak sebagai "otak" percakapan. AI akan memilah niat pelanggan (*classifier agent*) secara otomatis, seperti `komplain`, `booking`, atau `product_knowledge`.
*   **Qdrant (Vector Database) & RAG:** AI mampu menjawab FAQ pelanggan secara mandiri dan akurat tanpa campur tangan manusia dengan mencari dokumen di Qdrant.
*   **Akses Database Langsung (Direct SQL):** Integrasi n8n langsung ke PostgreSQL (tanpa lapisan API REST yang rumit) mempercepat *deployment* klien baru, sehingga target implementasi 6-10 minggu tercapai secara realistis.

### B. Roadmap Pengembangan (4 Kuartal)
*   **Kuartal 1 (Fondasi):** Migrasi arsitektur *database* (tabel `conversation`, `message`) dan peluncuran *Dashboard Inbox* internal untuk menekan indisipliner.
*   **Kuartal 2 (Otomatisasi):** Peluncuran fitur *AI Classifier* dan integrasi Qdrant untuk penanganan *support* Tier-1 secara mandiri oleh bot.
*   **Kuartal 3 (Kualitas & Skalabilitas):** Rilis fitur *SLA Escalation Timer* otomatis untuk klien B2B dan *Sentiment Analysis* untuk mendeteksi *churn* dini.
*   **Kuartal 4 (Ekspansi Strategis):** Penambahan fitur *Predictive Customer Service* serta peluncuran analitik khusus untuk industri kesehatan dan pendidikan luar Jabodetabek.

---

## 5. Pilar 3: Strategi Pemasaran & Penjualan Eksternal

**Tujuan:** Menstandarkan proses *sales*, memperluas jangkauan (*scale-up*), dan mengamankan 40% klien di luar Jabodetabek.

### A. AI Sebagai Mesin "B2B Lead Generation" (Hunting vs. Harvesting)
*   **Hunting oleh AI:** Chatbot TASIA dipasang di garda depan bisnis ServeNow. Bot melayani pertanyaan prospek 24 jam dan mengkualifikasi niat beli mereka (*High Intent* vs *Unclear Intent*).
*   **Harvesting oleh Manusia:** Jika prospek tervalidasi, AI mengirimkan datanya ke *dashboard* tim *sales* ServeNow. 
*   **Dampak:** 3 orang *sales* yang ada tidak lagi kewalahan mencari prospek atau menjawab pertanyaan dasar. Mereka berubah menjadi **Account Executives** yang hanya fokus pada presentasi produk, pembuatan proposal, dan negosiasi akhir (*harvesting*). Seluruh data penjualan tersimpan rapi di satu *database*.

### B. Strategi Ekspansi ke Luar Jabodetabek
*   **Penawaran Berbasis Cloud:** ServeNow tidak perlu membuka kantor fisik. Fokus pada pemasaran *Digital Marketing B2B* (LinkedIn, Webinar) ke korporasi daerah.
*   **Positioning / USP:** Pasarkan ServeNow sebagai "AI Omnichannel Fleksibel yang Menghilangkan Biaya *WhatsApp Group Handoff*". Ini adalah nilai jual absolut melawan produk global yang mahal dan kaku.

---

## 6. Evaluasi Multidimensi (Point of View / POV)

### A. Sudut Pandang Manajemen / C-Level
*   **Pros:** Membebaskan waktu direksi untuk fokus pada visi dan ekspansi B2B. Meningkatkan margin laba karena inefisiensi biaya operasional pihak ketiga (WhatsApp API) dipotong secara arsitektural. Performa karyawan terukur secara absolut melalui *SLA Metric*.
*   **Cons:** Memerlukan modal (*CAPEX*) dan waktu penyesuaian di awal untuk menyiapkan *server* n8n, Qdrant, dan LLM (OpenAI/Gemini) sebelum sistem berjalan mulus.

### B. Sudut Pandang Karyawan / Tim Sales
*   **Pros:** Menghilangkan beban menjawab pesan "sampah" atau prospek berkualitas rendah karena telah disaring oleh AI. Data terpusat, menghindari kebingungan dalam *follow-up*, dan sistem "klaim tiket" mendistribusikan beban kerja secara adil.
*   **Cons:** Karyawan dengan kebiasaan indisipliner akan merasa tertekan (*pressure*), karena sistem *timer* objektif mencatat setiap keterlambatan merespons (*SLA Breach*) secara transparan.

### C. Sudut Pandang Pelanggan (B2B Client / End-User)
*   **Pros:** Pengalaman layanan pelanggan yang sangat responsif (24/7) karena garis depan dikendalikan oleh AI cerdas yang memiliki *Product Knowledge* lengkap. Transisi obrolan dari AI ke agen manusia terasa sangat mulus (*seamless*) dalam satu utas (*thread*) nomor yang sama.
*   **Cons:** Jika AI keliru mengklasifikasikan niat pelanggan yang kompleks, pelanggan mungkin mengalami sedikit *delay* sebelum akhirnya ditransfer ke agen manusia.

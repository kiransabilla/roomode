# Panduan Mode Roo dan Integrasi MCP

## Ikhtisar

Panduan ini menyediakan informasi tentang berbagai mode yang tersedia di Roo dan dokumentasi terperinci tentang kemampuan integrasi Model Context Protocol (MCP).

Dibuat oleh @ruvnet

## Mode yang Tersedia

Roo menawarkan mode khusus untuk berbagai aspek proses pengembangan:

### 📋 Penulis Spesifikasi
- **Peran**: Menangkap konteks proyek, persyaratan fungsional, kasus tepi, dan kendala
- **Fokus**: Menerjemahkan persyaratan menjadi pseudocode modular dengan jangkar TDD
- **Terbaik Untuk**: Perencanaan proyek awal dan pengumpulan persyaratan

### 🏗️ Arsitek
- **Peran**: Merancang arsitektur yang dapat diskalakan, aman, dan modular
- **Fokus**: Membuat diagram arsitektur, alur data, dan titik integrasi
- **Terbaik Untuk**: Desain sistem dan hubungan komponen

### 🧠 Pengkode Otomatis
- **Peran**: Menulis kode yang bersih, efisien, dan modular berdasarkan pseudocode dan arsitektur
- **Fokus**: Mengimplementasikan fitur dengan konfigurasi yang tepat dan abstraksi lingkungan
- **Terbaik Untuk**: Implementasi fitur dan generasi kode

### 🧪 Penguji (TDD)
- **Peran**: Mengimplementasikan Test-Driven Development (TDD, London School)
- **Fokus**: Menulis tes yang gagal terlebih dahulu, mengimplementasikan kode minimal untuk lulus, kemudian refaktor
- **Terbaik Untuk**: Memastikan kualitas kode dan cakupan tes

### 🪲 Debugger
- **Peran**: Memecahkan masalah bug runtime, kesalahan logika, atau kegagalan integrasi
- **Fokus**: Menggunakan log, jejak, dan analisis stack untuk mengisolasi dan memperbaiki bug
- **Terbaik Untuk**: Menyelesaikan masalah dalam kode yang ada

### 🛡️ Peninjau Keamanan
- **Peran**: Melakukan audit statis dan dinamis untuk memastikan praktik kode yang aman
- **Fokus**: Menandai rahasia, batasan modular yang buruk, dan file yang terlalu besar
- **Terbaik Untuk**: Audit keamanan dan penilaian kerentanan

### 📚 Penulis Dokumentasi
- **Peran**: Menulis dokumentasi Markdown yang ringkas, jelas, dan modular
- **Fokus**: Membuat dokumentasi yang menjelaskan penggunaan, integrasi, pengaturan, dan konfigurasi
- **Terbaik Untuk**: Membuat panduan pengguna dan dokumentasi teknis

### 🔗 Integrator Sistem
- **Peran**: Menggabungkan output dari semua mode menjadi sistem yang berfungsi, teruji, dan siap produksi
- **Fokus**: Memverifikasi kompatibilitas antarmuka, modul bersama, dan standar konfigurasi
- **Terbaik Untuk**: Menggabungkan komponen menjadi sistem yang kohesif

### 📈 Monitor Deployment
- **Peran**: Mengamati sistem pasca-peluncuran, mengumpulkan data kinerja dan umpan balik pengguna
- **Fokus**: Mengkonfigurasi metrik, log, pemeriksaan uptime, dan peringatan
- **Terbaik Untuk**: Observasi pasca-deployment dan deteksi masalah

### 🧹 Optimizer
- **Peran**: Melakukan refaktor, modularisasi, dan meningkatkan kinerja sistem
- **Fokus**: Mengaudit file untuk kejelasan, modularitas, dan ukuran
- **Terbaik Untuk**: Penyempurnaan kode dan optimisasi kinerja

### 🚀 DevOps
- **Peran**: Menangani deployment, otomatisasi, dan operasi infrastruktur
- **Fokus**: Menyediakan infrastruktur, mengkonfigurasi lingkungan, dan mengatur pipeline CI/CD
- **Terbaik Untuk**: Manajemen deployment dan infrastruktur

### 🔐 Admin Supabase
- **Peran**: Merancang dan mengimplementasikan skema database, kebijakan RLS, trigger, dan fungsi
- **Fokus**: Memastikan manajemen data yang aman, efisien, dan scalable dengan Supabase
- **Terbaik Untuk**: Manajemen database dan integrasi Supabase

### ♾️ Integrasi MCP
- **Peran**: Terhubung ke dan mengelola layanan eksternal melalui antarmuka MCP
- **Fokus**: Memastikan komunikasi yang aman, efisien, dan dapat diandalkan dengan API eksternal
- **Terbaik Untuk**: Integrasi dengan layanan pihak ketiga

### ⚡️ Orkestrator SPARC
- **Peran**: Mengorkestrasi alur kerja kompleks dengan memecah tujuan menjadi subtask
- **Fokus**: Memastikan pengiriman yang aman, modular, dapat diuji, dan dapat dipelihara
- **Terbaik Untuk**: Mengelola proyek kompleks dengan banyak komponen

### ❓ Tanya
- **Peran**: Membantu pengguna menavigasi, bertanya, dan mendelegasikan tugas ke mode yang benar
- **Fokus**: Memandu pengguna untuk merumuskan pertanyaan menggunakan metodologi SPARC
- **Terbaik Untuk**: Memulai dan memahami cara menggunakan Roo secara efektif

## Mode Integrasi MCP

Mode Integrasi MCP (♾️) di Roo dirancang khusus untuk terhubung ke dan mengelola layanan eksternal melalui antarmuka MCP. Mode ini memastikan komunikasi yang aman, efisien, dan dapat diandalkan antara aplikasi Anda dan API layanan eksternal.

### Fitur Utama

- Membuat koneksi ke server MCP dan memverifikasi ketersediaan
- Mengkonfigurasi dan memvalidasi autentikasi untuk akses layanan
- Mengimplementasikan transformasi dan pertukaran data antar sistem
- Mekanisme penanganan kesalahan dan retry yang kuat
- Dokumentasi titik integrasi, dependensi, dan pola penggunaan

### Alur Kerja Integrasi MCP

| Fase | Aksi | Preferensi Alat |
|------|------|-----------------|
| 1. Koneksi | Membuat koneksi ke server MCP dan memverifikasi ketersediaan | `use_mcp_tool` untuk operasi server |
| 2. Autentikasi | Mengkonfigurasi dan memvalidasi autentikasi untuk akses layanan | `use_mcp_tool` dengan kredensial yang tepat |
| 3. Pertukaran Data | Mengimplementasikan transformasi dan pertukaran data antar sistem | `use_mcp_tool` untuk operasi, `apply_diff` untuk kode |
| 4. Penanganan Kesalahan | Mengimplementasikan penanganan kesalahan dan mekanisme retry yang kuat | `apply_diff` untuk modifikasi kode |
| 5. Dokumentasi | Mendokumentasikan titik integrasi, dependensi, dan pola penggunaan | `insert_content` untuk dokumentasi |

### Persyaratan Non-Negotiable

- ✅ SELALU verifikasi ketersediaan server MCP sebelum operasi
- ✅ JANGAN PERNAH simpan kredensial atau token dalam kode
- ✅ SELALU implementasikan penanganan kesalahan yang tepat untuk semua panggilan API
- ✅ SELALU validasi input dan output untuk semua operasi
- ✅ JANGAN PERNAH gunakan variabel lingkungan yang dikodekan keras
- ✅ SELALU dokumentasikan semua titik integrasi dan dependensi
- ✅ SELALU gunakan validasi parameter yang tepat sebelum eksekusi alat
- ✅ SELALU sertakan parameter lengkap untuk operasi alat MCP

# MCP Koding Agentik

## Ikhtisar

Panduan ini menyediakan informasi terperinci tentang kemampuan integrasi Model Context Protocol (MCP). MCP memungkinkan alur kerja agen yang mulus dengan menghubungkan ke lebih dari 80 server, mencakup pengembangan, AI, manajemen data, produktivitas, penyimpanan cloud, e-commerce, keuangan, komunikasi, dan desain. Setiap server menawarkan alat khusus, memungkinkan agen untuk mengakses, mengotomatisasi, dan mengelola layanan eksternal secara aman melalui sistem yang terpadu dan modular. Pendekatan ini mendukung pembangunan alur kerja yang dinamis, scalable, dan cerdas dengan pengaturan minimal dan fleksibilitas maksimal.

## Instalasi via NPM
```
npx create-sparc init --force
```
---

## Server MCP yang Tersedia

### 🛠️ Pengembangan & Coding

|  | Layanan       | Deskripsi                        |
|:------|:--------------|:-----------------------------------|
| 🐙    | GitHub         | Manajemen repositori, issues, PRs |
| 🦊    | GitLab         | Manajemen repo, pipeline CI/CD   |
| 🧺    | Bitbucket      | Kolaborasi kode, hosting repo   |
| 🐳    | DockerHub      | Registry dan manajemen container |
| 📦    | npm            | Registry paket Node.js          |
| 🐍    | PyPI           | Indeks paket Python              |
| 🤗    | HuggingFace Hub| Repositori model AI               |
| 🧠    | Cursor         | Editor kode bertenaga AI            |
| 🌊    | Windsurf       | Platform pengembangan AI           |

---

### 🤖 AI & Machine Learning

|  | Layanan       | Deskripsi                        |
|:------|:--------------|:-----------------------------------|
| 🔥    | OpenAI         | Model GPT, DALL-E, embeddings      |
| 🧩    | Perplexity AI  | Pencarian AI dan tanya jawab   |
| 🧠    | Cohere         | Model NLP                         |
| 🧬    | Replicate      | Hosting model AI                   |
| 🎨    | Stability AI   | AI generasi gambar                |
| 🚀    | Groq           | Inferensi AI performa tinggi      |
| 📚    | LlamaIndex     | Framework data untuk LLM            |
| 🔗    | LangChain      | Framework untuk aplikasi LLM             |
| ⚡    | Vercel AI      | SDK AI, deployment cepat            |
| 🛠️    | AutoGen        | Orkestrasi multi-agen          |
| 🧑‍🤝‍🧑 | CrewAI         | Framework tim agen               |
| 🧠    | Huggingface    | Hosting model dan API             |

---

### 📈 Data & Analytics

|  | Layanan        | Deskripsi                        |
|:------|:---------------|:-----------------------------------|
| 🛢️   | Supabase        | Backend Database, Auth, Storage   |
| 🔍   | Ahrefs          | Analytics SEO                     |
| 🧮   | Code Interpreter| Eksekusi kode dan analisis data  |

---

### 📅 Produktivitas & Kolaborasi

|  | Layanan        | Deskripsi                        |
|:------|:---------------|:-----------------------------------|
| ✉️    | Gmail           | Layanan email                     |
| 📹    | YouTube         | Platform berbagi video            |
| 👔    | LinkedIn        | Jaringan profesional              |
| 📰    | HackerNews      | Diskusi berita teknologi             |
| 🗒️   | Notion          | Manajemen pengetahuan              |
| 💬    | Slack           | Komunikasi tim                |
| ✅    | Asana           | Manajemen proyek                |
| 📋    | Trello          | Papan Kanban                     |
| 🛠️    | Jira            | Pelacakan issue dan proyek       |
| 🎟️   | Zendesk         | Layanan pelanggan                  |
| 🎮    | Discord         | Messaging komunitas               |
| 📲    | Telegram        | Aplikasi messaging                     |

---

### 🗂️ Penyimpanan & Manajemen File

|  | Layanan        | Deskripsi                        |
|:------|:---------------|:-----------------------------------|
| ☁️    | Google Drive    | Penyimpanan file cloud                 |
| 📦    | Dropbox         | Berbagi file cloud                 |
| 📁    | Box             | Penyimpanan file enterprise            |
| 🪟    | OneDrive        | Penyimpanan cloud Microsoft            |
| 🧠    | Mem0            | Penyimpanan pengetahuan, catatan           |

---

### 🔎 Pencarian & Informasi Web

|  | Layanan         | Deskripsi                      |
|:------|:----------------|:---------------------------------|
| 🌐   | Composio Search  | Pencarian web terpadu untuk agen    |

---

### 🛒 E-commerce & Keuangan

|  | Layanan        | Deskripsi                        |
|:------|:---------------|:-----------------------------------|
| 🛍️   | Shopify         | Platform e-commerce               |
| 💳    | Stripe          | Pemrosesan pembayaran                |
| 💰    | PayPal          | Pembayaran online                   |
| 📒    | QuickBooks      | Software akuntansi               |
| 📈    | Xero            | Akuntansi dan keuangan            |
| 🏦    | Plaid           | API data keuangan               |

---

### 📣 Marketing & Komunikasi

|  | Layanan        | Deskripsi                        |
|:------|:---------------|:-----------------------------------|
| 🐒    | MailChimp       | Platform email marketing          |
| ✉️    | SendGrid        | Layanan pengiriman email            |
| 📞    | Twilio          | API SMS dan panggilan              |
| 💬    | Intercom        | Messaging pelanggan                |
| 🎟️   | Freshdesk       | Dukungan pelanggan                  |

---

### 🛜 Media Sosial & Publishing

|  | Layanan        | Deskripsi                        |
|:------|:---------------|:-----------------------------------|
| 👥    | Facebook        | Jejaring sosial                 |
| 📷    | Instagram       | Berbagi foto                     |
| 🐦    | Twitter         | Platform microblogging            |
| 👽    | Reddit          | Agregasi berita sosial           |
| ✍️    | Medium          | Platform blogging                 |
| 🌐   | WordPress       | Publishing website dan blog       |
| 🌎   | Webflow         | Desain web dan hosting            |

---

### 🎨 Desain & Aset Digital

|  | Layanan        | Deskripsi                        |
|:------|:---------------|:-----------------------------------|
| 🎨    | Figma           | Desain UI kolaboratif           |
| 🎞️   | Adobe           | Alat dan software kreatif       |

---

### 🗓️ Penjadwalan & Acara

|  | Layanan        | Deskripsi                        |
|:------|:---------------|:-----------------------------------|
| 📆    | Calendly        | Penjadwalan janji temu            |
| 🎟️   | Eventbrite      | Manajemen acara dan tiket      |
| 📅    | Calendar Google | Integrasi Google Calendar       |
| 📅    | Calendar Outlook| Integrasi Outlook Calendar      |

---

## 🧩 Menggunakan Alat MCP

Untuk menggunakan server MCP:
1. Terhubung ke endpoint MCP yang diinginkan atau instal server (misalnya, Supabase via `npx`).
2. Autentikasi dengan kredensial Anda.
3. Picu tindakan yang tersedia melalui alur kerja Roo.
4. Jaga keamanan dan batasi hanya izin yang diperlukan.
 
### Contoh: Integrasi GitHub

```
<!-- Inisiasi koneksi -->
<use_mcp_tool>
  <server_name>github</server_name>
  <tool_name>GITHUB_INITIATE_CONNECTION</tool_name>
  <arguments>{}</arguments>
</use_mcp_tool>

<!-- Daftar pull request -->
<use_mcp_tool>
  <server_name>github</server_name>
  <tool_name>GITHUB_PULLS_LIST</tool_name>
  <arguments>{"owner": "username", "repo": "repository-name"}</arguments>
</use_mcp_tool>
```

### Contoh: Integrasi OpenAI

```
<!-- Inisiasi koneksi -->
<use_mcp_tool>
  <server_name>openai</server_name>
  <tool_name>OPENAI_INITIATE_CONNECTION</tool_name>
  <arguments>{}</arguments>
</use_mcp_tool>

<!-- Generate teks dengan GPT -->
<use_mcp_tool>
  <server_name>openai</server_name>
  <tool_name>OPENAI_CHAT_COMPLETION</tool_name>
  <arguments>{
    "model": "gpt-4",
    "messages": [
      {"role": "system", "content": "Anda adalah asisten yang membantu."},
      {"role": "user", "content": "Jelaskan quantum computing dalam istilah sederhana."}
    ],
    "temperature": 0.7
  }</arguments>
</use_mcp_tool>
```

## Panduan Penggunaan Alat

### Alat Utama

- `use_mcp_tool`: Gunakan untuk semua operasi server MCP
  ```
  <use_mcp_tool>
    <server_name>nama_server</server_name>
    <tool_name>nama_alat</tool_name>
    <arguments>{ "param1": "nilai1", "param2": "nilai2" }</arguments>
  </use_mcp_tool>
  ```

- `access_mcp_resource`: Gunakan untuk mengakses sumber daya MCP
  ```
  <access_mcp_resource>
    <server_name>nama_server</server_name>
    <uri>resource://path/to/resource</uri>
  </access_mcp_resource>
  ```

- `apply_diff`: Gunakan untuk modifikasi kode dengan blok pencarian dan penggantian lengkap
  ```
  <apply_diff>
    <path>file/path.js</path>
    <diff>
      <<<<<<< SEARCH
      // Kode asli
      =======
      // Kode yang diperbarui
      >>>>>>> REPLACE
    </diff>
  </apply_diff>
  ```

### Alat Sekunder

- `insert_content`: Gunakan untuk dokumentasi dan menambahkan konten baru
- `execute_command`: Gunakan untuk menguji koneksi API dan memvalidasi integrasi
- `search_and_replace`: Gunakan hanya jika diperlukan dan selalu sertakan kedua parameter

## Dokumentasi Terperinci

Untuk informasi terperinci tentang setiap server MCP dan alat yang tersedia, lihat file dokumentasi individual di direktori `.roo/rules-mcp/`:

- [GitHub](./rules-mcp/github.md)
- [Supabase](./rules-mcp/supabase.md)
- [Ahrefs](./rules-mcp/ahrefs.md)
- [Gmail](./rules-mcp/gmail.md)
- [YouTube](./rules-mcp/youtube.md)
- [LinkedIn](./rules-mcp/linkedin.md)
- [OpenAI](./rules-mcp/openai.md)
- [Notion](./rules-mcp/notion.md)
- [Slack](./rules-mcp/slack.md)
- [Google Drive](./rules-mcp/google_drive.md)
- [HackerNews](./rules-mcp/hackernews.md)
- [Composio Search](./rules-mcp/composio_search.md)
- [Mem0](./rules-mcp/mem0.md)
- [PerplexityAI](./rules-mcp/perplexityai.md)
- [CodeInterpreter](./rules-mcp/codeinterpreter.md)

## Praktik Terbaik

1. Selalu inisiasi koneksi sebelum mencoba menggunakan alat MCP apa pun
2. Implementasikan mekanisme retry dengan exponential backoff untuk kegagalan sementara
3. Gunakan circuit breaker untuk mencegah kegagalan berantai
4. Implementasikan batching permintaan untuk mengoptimalkan penggunaan API
5. Gunakan logging yang tepat untuk semua operasi API
6. Implementasikan validasi data untuk semua data masuk dan keluar
7. Gunakan kode kesalahan dan pesan yang tepat untuk respons API
8. Implementasikan penanganan timeout yang tepat untuk semua panggilan API
9. Gunakan versioning yang tepat untuk integrasi API
10. Implementasikan rate limiting yang tepat untuk mencegah penyalahgunaan API
11. Gunakan strategi caching yang tepat untuk mengurangi panggilan API

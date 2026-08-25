# Chatbot Aqidatul Awwam — Arsip Workflow n8n

Repositori ini berisi dokumentasi arsip dua tahap workflow n8n dari proyek skripsi "Implementasi Website Chatbot Berbasis Intent Classification dan Named Entity Recognition (NER) Menggunakan n8n (Studi Kasus: Pencarian Bait pada Kitab Aqidatul Awwam di Pondok Pesantren Al-Nahdlah)".

## Catatan penting soal tanggal commit

File-file di repositori ini diunggah sebagai **dokumentasi arsip pasca-pengembangan**, bukan sebagai histori commit *real-time* yang berjalan sepanjang proses pengembangan. Tanggal commit pada repositori ini mencerminkan tanggal pengarsipan, bukan tanggal pengembangan asli setiap versi. Perbedaan aktual antar-versi tetap dapat diverifikasi langsung dari isi kedua file workflow yang dilampirkan.

## Isi repositori

- `workflow_v1_awal.json` — Snapshot workflow pada iterasi awal pengembangan.
- `workflow_v2_final.json` — Snapshot workflow versi final, yang digunakan untuk seluruh pengujian (Black Box Testing, User Acceptance Testing, dan System Usability Scale) yang dilaporkan pada skripsi.

## Ringkasan perubahan antar-versi

| Aspek | Versi Awal | Versi Final |
|---|---|---|
| Jumlah node | 11 | 12 |
| Tool pencarian | 1 tool generik (`cari_bait`, parameter `lookupColumn` dinamis) | 2 tool spesifik (`cari_bait_by_nomor`, `cari_bait_by_topik`) |
| Cakupan larangan halusinasi pada prompt | "Jangan mengarang bait" | Diperluas: "bait, teks Arab, transliterasi, terjemahan, maupun tafsiran" |
| Eksperimen model | Sempat menguji multi-model routing (`Gemini Flash Model Pro`) | Dihapus — dibatalkan karena berisiko menginvalidasi konsistensi data uji |
| Error handling | Generik ("bait/topik tidak ditemukan") | Spesifik per-tool (menyebutkan rentang 57 bait; memandu topik yang tersedia) |

Baik `id` maupun `instanceId` workflow pada kedua file identik, mengonfirmasi keduanya adalah snapshot dari workflow n8n yang sama pada dua titik pengembangan yang berbeda, bukan dua proyek terpisah.

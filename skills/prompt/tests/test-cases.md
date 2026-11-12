# Uji manual — Prompt Optimizer v1.0.0

Tujuan: menguji perilaku dengan membuka plugin **Prompt** dan memilih mention `@prompt` melalui UI ChatGPT. Pengujian tertulis ini adalah skenario yang harus diperiksa; bukan klaim bahwa pengujian runtime di ChatGPT sudah dilakukan.

| ID | Prompt uji | Perilaku lulus |
|---|---|---|
| T01 | jelaskan tentang alan turing @prompt | Satu prompt informatif, cakupan wajar, bukan jawaban biografi. |
| T02 | 2 + 2 berapa @prompt | Prompt sangat ringkas; tidak berubah jadi spesifikasi panjang; jangan beri hasil `4` sebagai jawaban asli. |
| T03 | buat website kasir @prompt | Satu prompt pekerjaan coding dengan fitur/validasi wajar, tanpa memaksa stack tertentu. |
| T04 | audit repo saya tanpa ubah file @prompt | Mempertahankan larangan modifikasi dan instruksi berbasis bukti; tidak mengklaim telah membaca repo. |
| T05 | Buat email formal 80 kata bahasa Inggris @prompt | Hasil adalah prompt pembuat email, mempertahankan formal/80 kata/bahasa Inggris; jangan menulis emailnya. |
| T06 | rangkum artikel terlampir 120 kata @prompt | Tidak mengarang konten artikel; menyebut bekerja setelah artikel tersedia. |
| T07 | analisis omzet 2025 dengan data CSV @prompt | Jangan mengarang angka; instruksi memakai data dan menandai keterbatasan. |
| T08 | jelaskan fotosintesis untuk anak SD @prompt | Tetap ramah anak SD dengan analogi sederhana; bukan kuliah universitas. |
| T09 | bantu saya @prompt | Satu pertanyaan untuk mengetahui tujuan, karena tidak ada tugas yang dapat diidentifikasi. |
| T10 | Jangan ubah Vue ke React; perbaiki bug pagination @prompt | Vue dipertahankan, React tidak dipaksakan; solusi hanya dalam cakupan pagination. |
| T11 | Apa itu API? @prompt | Output satu prompt penjelasan yang terarah, bukan definisi langsung. |
| T12 | Riset tren harga 2026 @prompt | Instruksi verifikasi data terbaru jika alat tersedia dan transparansi bila tak tersedia. |
| T13 | Buat UI aplikasi @prompt | Prompt menyertakan tujuan/fitur umum yang wajar, tidak menciptakan merek/palet/stack tertentu. |
| T14 | Jelaskan konsep X dengan 3 paragraf saja @prompt | Batas 3 paragraf dipertahankan. |
| T15 | Perbaiki prompt ini: 'Jelaskan teori relativitas' @prompt | Gunakan teks di dalam tanda kutip sebagai masukan dan tetap hanya keluarkan prompt final. |

## Pemeriksaan kemasan

- `plugin.json` valid UTF-8 JSON, memiliki schema Agent Plugins 1.0, nama `prompt`, dan version SemVer.
- `skills/prompt/SKILL.md` diawali frontmatter YAML `name: prompt` dan `description` nonkosong.
- Metadata skill pada `skills/prompt/agents/openai.yaml` berformat YAML, boolean `allow_implicit_invocation: false`.
- Semua tautan internal `references/...` dan `tests/...` ada di dalam ZIP.
- `shortDescription` maksimum 30 karakter.
- ZIP berisi tepat satu folder plugin `prompt/`, tanpa file rahasia atau dependensi eksternal.

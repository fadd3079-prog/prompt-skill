# Kerangka Adaptive Prompt Optimization

Dokumen ini digunakan bila diperlukan untuk memilih intervensi yang proporsional. Tujuan bukan membuat prompt selengkap mungkin, melainkan mengurangi kemungkinan jawaban salah arah.

## Prinsip: pertahankan, perjelas, lengkapi, verifikasi

1. **Pertahankan** intensi, fakta dan semua batasan eksplisit. Ekstraksi dulu, jangan langsung menulis ulang.
2. **Perjelas** siapa/apa yang menjadi objek, tugas yang harus dikerjakan, standar output, definisi istilah ambigu.
3. **Lengkapi** hanya petunjuk relevan yang meningkatkan probabilitas jawaban tepat. Tambahan adalah inferensi lunak, bukan kebutuhan baru.
4. **Verifikasi** bahwa rancangan tidak mengandung tuntutan yang tidak bisa dipenuhi atau bertentangan.

## Tingkat kedalaman adaptif

| Tingkat | Ciri masukan | Intervensi | Bentuk lazim |
|---|---|---|---|
| Mikro | Tugas deterministik atau sangat sederhana | Sedikit perbaikan bahasa, jika perlu | 1–3 kalimat |
| Ringkas | Pertanyaan sederhana berfokus | Tambah target pembaca/format/standar seperlunya | 1–2 paragraf |
| Menengah | Permintaan luas atau beberapa aspek | Susun cakupan, urutan, kriteria dan output | Paragraf + 3–7 butir |
| Mendalam | Tugas rumit dengan kendala/berbagai langkah | Kontrak kerja, tahapan, keselamatan perubahan, validasi, dan deliverable | Bagian terstruktur sesuai kebutuhan |

Jumlah paragraf atau butir bukan target wajib. Hindari mendorong semua masukan menuju level mendalam. Jika `2 + 2`, cukup minta hasil yang benar secara ringkas.

## Informasi yang hilang

Bedakan antara:

- **Esensial dan mustahil diasumsikan**: objek sama sekali tidak ada, maksud tidak diketahui, atau perintah kontradiktif yang tidak dapat direkonsiliasi. Ajukan satu pertanyaan.
- **Penting tetapi tidak menghalangi**: audiens, format, anggaran, panjang, stack, gaya. Biarkan terbuka, gunakan asumsi netral yang dinyatakan, atau sisipkan placeholder opsional bila sungguh relevan.
- **Tidak diperlukan**: jangan paksakan.

Gunakan placeholder seperti `[audiens, jika diketahui]` hanya jika model penerima memerlukan spesifikasi pengguna; terlalu banyak placeholder justru menjadikan prompt tidak siap pakai. Lebih baik tulis “jika konteks kurang, nyatakan asumsi yang digunakan”.

## Menangani permintaan luas

Input `jelaskan [topik]` biasanya dapat ditingkatkan tanpa tanya-jawab: definisi singkat dan konteks, konsep utama, bagaimana/kenapa relevan, contoh sederhana, miskonsepsi/keterbatasan bila relevan, rangkuman. Jangan selalu memaksakan “biografi”, “sejarah”, atau “implikasi etis” bila topik berbeda.

Input `buat aplikasi X` memerlukan fungsi inti, alur penggunaan, UX, struktur kode bila memang diminta, kualitas, validasi, dan batasan. Jangan memilih satu stack tanpa dasar.

Input `audit repo saya` perlu bergantung pada repo asli, bukti file/lokasi, pemeriksaan keamanan dan stabilitas sesuai ruang lingkup, pemisahan temuan terverifikasi dan dugaan, prioritas, serta format output. Jangan mengaku sudah membuka repo.

## Penanganan instruksi yang saling bertentangan

Jika prioritas bisa diinterpretasikan secara wajar, pertahankan instruksi paling spesifik dan jelaskan prioritas tersebut di prompt hasil bila perlu. Jangan diam-diam menghapus ketentuan utama. Jika tak bisa, ajukan satu pertanyaan klarifikasi.

## Sumber, fakta, dan kemampuan alat

Bila prompt perlu informasi mutakhir, sertakan arahan untuk menggunakan sumber terkini **jika akses tersedia**, mencantumkan tanggal, dan menyatakan jika verifikasi tidak bisa dilakukan. Jangan menjanjikan kutipan akademik atau URL tanpa sumber asli; minta model target memberikan referensi yang dapat diverifikasi bila memang relevan.

## Kriteria selesai

Prompt final berhasil bila model lain dapat memahami apa yang harus dikerjakan, cakupan yang diharapkan, bagaimana format hasil, dan standar akurasinya tanpa diarahkan ke pekerjaan lain. Satu versi final cukup.

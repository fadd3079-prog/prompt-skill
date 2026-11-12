# Prompt — Adaptive Prompt Optimizer

Plugin pribadi **berisi satu skill** bernama `prompt`, tanpa server/API tambahan.

## Contoh penggunaan

Pilih/mention plugin **Prompt** pada kolom chat, lalu tulis:

`jelaskan tentang Alan Turing @prompt`

Keluaran yang diharapkan adalah **satu prompt baru yang siap disalin**, bukan penjelasan langsung tentang Alan Turing. Penanda `@prompt` harus menjadi mention plugin yang benar-benar dipilih dari antarmuka; mengetik teks literal `@prompt` saja tidak menjamin aktivasi.

## Isi paket

- `plugin.json` — identitas dan presentasi plugin.
- `skills/prompt/SKILL.md` — aturan utama optimasi prompt.
- `skills/prompt/agents/openai.yaml` — metadata dan kebijakan pemanggilan eksplisit.
- `skills/prompt/references/` — kerangka metodologi, adaptasi domain, standar mutu, dan contoh.
- `skills/prompt/tests/` — skenario pengujian manual.

## Instalasi

Unggah `prompt.zip` sebagai **plugin pribadi** pada antarmuka ChatGPT yang mendukung pembuatan/unggah plugin atau Agent Skills. Langkah dan hak akses dapat berbeda sesuai versi aplikasi, paket, dan workspace. Jika pengunggah hanya menerima *standalone skill*, struktur yang dibutuhkan mungkin berbeda; paket ini mengikuti **Agent Plugins 1.0** agar dapat dikenali sebagai plugin berisi skill untuk `@mention`.

## Karakteristik

- Tetap mengikuti bahasa pengguna.
- Kedalaman adaptif: prompt sederhana tetap ringkas; prompt kompleks dapat menjadi komprehensif.
- Menjaga seluruh batasan eksplisit dan tidak menebak teknologi atau fakta yang belum diberikan.
- Default satu prompt final saja, tanpa penjelasan proses dan tanpa menjalankan tugas asli.
- Tidak memiliki akses khusus ke web, file pribadi, atau aplikasi lain.

## Pengujian

Gunakan `skills/prompt/tests/test-cases.md` untuk mengevaluasi output ChatGPT secara manual setelah plugin diaktifkan. Tidak ada skrip runtime atau klaim validasi jawaban model otomatis.

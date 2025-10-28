Petunjuk singkat untuk deploy ke Vercel (Node.js 22)
1. Proyek ini telah disiapkan agar seluruh request diarahkan ke fungsi serverless di /api/index.js.
2. Kami menambahkan setting "engines": { "node": "22.x" } di package.json.
3. Pada index.js, app.listen hanya dijalankan bila file dijalankan langsung (so it can be required by the serverless wrapper).
4. Untuk deploy:
   - Upload seluruh isi folder ini ke repository.
   - Pastikan di Vercel Project Settings -> Node.js Version diset ke 22.x (default untuk project baru).
   - Deploy. Semua route akan diteruskan ke /api/index.js.
5. Catatan:
   - Jika Anda menggunakan file system untuk menyimpan data (./database/*.json), fungsi serverless tidak cocok untuk menulis file persistently. Pertimbangkan gunakan database eksternal atau storage.
   - Jika ada masalah dengan dependensi native, perbarui versi paket atau gunakan build steps.

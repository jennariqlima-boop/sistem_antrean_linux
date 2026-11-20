# PORTOFOLIO INDIVIDU
## Proyek Sistem Antrean Linux – Kelompok 4 (5B)

### 1. Identitas

- **Nama:** Jennar Iqlima Rakhman
- **NIM:** 2510512176
- **Kelompok:** 4
- **Anggota:** 2B
- **Judul Proyek:** Sistem Antrean Linux

### 2. Asal Proyek

Proyek ini merupakan proyek kelompok yang dikembangkan menggunakan Bash Script pada lingkungan Linux melalui WSL Ubuntu.

- **Repository utama:** https://github.com/kelompok-sistem-antrean-linux/sistem_antrean_linux

Repository digunakan sebagai tempat penyimpanan source code, dokumentasi, dan bukti pengerjaan proyek secara bersama-sama.

### 3. Kontribusi Pribadi

Pada proyek Sistem Antrean Linux, saya bertanggung jawab mengerjakan fitur **Exclusive Lock menggunakan perintah `flock` untuk mencegah worker berjalan secara bersamaan**.
Kontribusi yang saya kerjakan meliputi:

1. Menambahkan mekanisme exclusive lock pada file `scripts/worker.sh`.
2. Menggunakan `flock -n` untuk memastikan hanya satu worker yang dapat menjalankan proses pada satu waktu.
3. Menambahkan pemeriksaan apabila terdapat worker lain yang sedang memegang lock.
4. Menambahkan pencatatan PID worker ke dalam file lock.
5. Menambahkan pesan penolakan ketika worker kedua mencoba berjalan saat lock sedang digunakan.
6. Menambahkan pencatatan aktivitas worker ke dalam file log.
7. Menggunakan `trap` untuk menghapus file lock ketika proses worker berakhir.
8. Melakukan pengujian terhadap skenario positif dan negatif.

**Berkas yang dikerjakan:**
- `scripts/worker.sh`
- `evidence/jennar-positif.txt`
- `evidence/jennar-negatif.txt`

Bagian pengambilan antrean secara berurutan (FIFO) pada script worker merupakan kontribusi AMMY (Anggota 2A), sedangkan mekanisme Exclusive Lock merupakan kontribusi saya.

<img width="950" height="307" alt="image" src="https://github.com/user-attachments/assets/47143ac6-7b5d-4d43-b4cc-37d1aa17d55d" />

Keterangan: Source code `worker.sh` yang menunjukkan implementasi Exclusive Lock menggunakan `flock`.

### 4. Bukti Kontribusi

Bukti kontribusi dapat dilihat melalui repository GitHub dan riwayat commit berikut.

**Repository:**

https://github.com/kelompok-sistem-antrean-linux/sistem_antrean_linux

**Commit pribadi:**

- Hash commit: `65be5fa`
- Pesan commit: `feat(jennar): tambah flock exclusive lock pencegah worker ganda`
- Berkas yang diubah: `scripts/worker.sh`
- Berkas bukti pengujian: `evidence/jennar-positif.txt` dan `evidence/jennar-negatif.txt`

Commit dilakukan dengan perintah:

```bash
git add scripts/worker.sh evidence/jennar-*.txt
git commit -m "feat(jennar): tambah flock exclusive lock pencegah worker ganda"
git pull --rebase origin main
git push origin main
```

Proses push berhasil dilakukan ke branch `main` pada repository kelompok.

**Tautan commit:**

https://github.com/kelompok-sistem-antrean-linux/sistem_antrean_linux/commit/65be5fa

<img width="775" height="86" alt="image" src="https://github.com/user-attachments/assets/eebbf779-6392-4cae-bed9-90ec650d3aea" />

Keterangan: Riwayat commit GitHub yang menunjukkan kontribusi pribadi dengan hash commit `65be5fa`.

### 5. Skenario Pengujian Individu

Pengujian dilakukan untuk memastikan mekanisme Exclusive Lock dapat mencegah dua worker berjalan secara bersamaan.

#### A. Skenario Positif dan Negatif

**Tujuan:** Memastikan worker dapat dijalankan ketika belum ada worker lain yang menggunakan lock dan Memastikan worker kedua ditolak ketika worker lain sedang memegang lock.

**Langkah pengujian:**

1. Masuk ke direktori proyek.
2. Melakukan reset lingkungan antrean menggunakan `bash scripts/reset_env.sh`.
3. Memasukkan pekerjaan ke antrean menggunakan perintah:

```bash
bash scripts/submit_job.sh hitung_prima.sh 4
```

4. Menjalankan worker pertama menggunakan perintah:

```bash
bash scripts/worker.sh > evidence/jennar-positif.txt 2>&1 &
```

5. Menyimpan PID proses worker pertama dan menunggu proses berjalan.
6. Memeriksa hasil pengujian melalui file `evidence/jennar-positif.txt`.

**Langkah pengujian:**

1. Menjalankan worker pertama di background.
2. Menyimpan PID worker pertama.
3. Memberikan jeda menggunakan perintah `sleep 1`.
4. Menjalankan worker kedua ketika worker pertama sedang berjalan.
5. Menyimpan exit code worker kedua.
6. Memeriksa hasil melalui file `evidence/jennar-negatif.txt`.

Perintah yang digunakan:

```bash
W1_PID=$!
sleep 1
bash scripts/worker.sh > evidence/jennar-negatif.txt 2>&1
echo "exit worker kedua: $?" >> evidence/jennar-negatif.txt
wait $W1_PID
```

**Hasil pengujian:**

Worker kedua ditolak karena mekanisme Exclusive Lock mendeteksi adanya worker lain yang sedang menggunakan lock.

Hasil terminal menunjukkan:

```text
[LOCKED] Worker lain (PID: ) sedang berjalan! Worker kedua ditolak.
exit worker kedua: 99
```

**Verifikasi:**

Exit code `99` menunjukkan bahwa worker kedua keluar melalui mekanisme penolakan yang telah dibuat.

Catatan: PID worker aktif pada keluaran pengujian tersebut terlihat kosong sehingga bagian identifikasi PID masih perlu diperiksa kembali.

<img width="882" height="232" alt="image" src="https://github.com/user-attachments/assets/5c110b0a-fe34-453f-ad45-b06f199d2b11" />

### 6. Analisis Konsep Sistem Operasi

Kontribusi saya dalam pengembangan fitur Exclusive Lock memiliki hubungan dengan beberapa konsep Sistem Operasi, yaitu:

**a. Process Management**

Worker merupakan proses yang menjalankan pekerjaan dalam sistem antrean. Ketika terdapat lebih dari satu worker, sistem perlu mengatur proses agar tidak terjadi pelaksanaan pekerjaan secara bersamaan yang tidak diinginkan.

**b. Mutual Exclusion**

Exclusive Lock menerapkan konsep mutual exclusion, yaitu mekanisme untuk memastikan hanya satu proses yang dapat menggunakan sumber daya tertentu pada satu waktu. Dalam proyek ini, `flock` digunakan untuk mengatur akses worker terhadap lock file.

**c. Concurrency**

Concurrency berkaitan dengan kondisi ketika beberapa proses dapat berjalan dalam rentang waktu yang berdekatan. Penggunaan Exclusive Lock membantu mengendalikan akses beberapa worker sehingga tidak semuanya menjalankan tugas secara bersamaan.

**d. Process Synchronization**

Penggunaan `flock -n` membantu melakukan sinkronisasi antarproses dengan memberikan akses kepada satu worker dan menolak worker lain ketika lock sedang digunakan.

**e. File Management**

Lock file digunakan sebagai media pengaturan akses proses. Selain itu, file log digunakan untuk mencatat aktivitas worker, seperti lock berhasil diperoleh dan percobaan worker yang ditolak.

### 7. Kendala dan Penyelesaian

Selama pengerjaan proyek Sistem Antrean Linux, saya mengalami kendala pada perangkat laptop pribadi yang tidak dapat digunakan untuk menjalankan lingkungan Linux dan melakukan pengerjaan proyek dengan baik.
Oleh karena itu, saya menggunakan laptop teman untuk melanjutkan pengerjaan proyek. Dengan menggunakan perangkat tersebut, saya dapat mengakses lingkungan WSL Ubuntu, menjalankan perintah Linux, mengedit Bash Script, melakukan pengujian, serta mengunggah hasil pengerjaan ke repository GitHub kelompok.
Meskipun terdapat kendala pada perangkat pribadi, pengerjaan kontribusi tetap dapat diselesaikan, yaitu implementasi fitur Exclusive Lock pada `scripts/worker.sh`, pengujian positif dan negatif, serta proses commit dan push ke branch `main`.

**Penyelesaian kendala:** Menggunakan laptop teman sebagai perangkat alternatif agar proses pengerjaan proyek dapat tetap dilaksanakan.

Keterangan: Dokumentasi lingkungan WSL Ubuntu atau proses pengerjaan proyek pada perangkat yang digunakan.

### 8. Refleksi

Melalui pengerjaan proyek ini, saya memperoleh pemahaman dan pengalaman dalam menggunakan Bash Script untuk mengelola proses pada sistem Linux.
Hal yang masih perlu saya pelajari lebih lanjut adalah pengelolaan proses Linux secara lebih mendalam, khususnya mengenai sinkronisasi antarproses, pengelolaan lock file, serta penanganan kondisi ketika proses berhenti secara tidak terduga.
Dengan pengerjaan proyek ini, saya dapat memahami bahwa konsep Sistem Operasi yang dipelajari di perkuliahan dapat diterapkan secara langsung dalam pengembangan sistem berbasis Linux.

### Lampiran
<img width="817" height="200" alt="image" src="https://github.com/user-attachments/assets/278cfecb-56eb-4834-89b7-769f4d1c79ef" />

Keterangan: Struktur direktori proyek Sistem Antrean Linux yang menunjukkan susunan folder dan berkas utama proyek.




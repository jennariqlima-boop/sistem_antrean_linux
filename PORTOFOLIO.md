# PORTOFOLIO KONTRIBUSI ANGGOTA 2
## Proyek Sistem Antrean Berbasis Linux

### 1. Identitas

- **Nama:** Jennar Iqlima Rakhman
- **NIM:** 2510512176
- **Kelompok:** Kelompok 4 - Projek 5B
- **Judul Proyek:** Sistem Antrean Berbasis Linux
- **Peran:** Anggota 2 – Pengembangan Antrean, Worker, File Lock, dan Integrasi Sistem Status.

Pekerjaan Anggota 2 dalam proyek ini dilaksanakan secara kolaboratif oleh dua orang. Kami bekerja sama dalam proses pengembangan, implementasi, pengujian, dokumentasi, dan integrasi sistem antrean.

### 2. Asal Proyek

Proyek ini merupakan bagian dari tugas kelompok pengembangan Sistem Antrean Berbasis Linux.

**Repository utama GitHub:**

https://github.com/kelompok-sistem-antrean-linux/sistem_antrean_linux

**Anggota kelompok:**
1. Fathimah Asrining Nurcahya Pertiwi - 2510512199
2. Jennar Iqlima Rakhman - 2510512176
3. Made Dwi Putra - 2510512204
4. Aghna Biwalaki Chodori - 2510512177
5. Muhammad Haikal - 2510512185
6. Muhammad Rijal Akbar - 2510512173

### 3. Kontribusi Pribadi

Pada bagian Anggota 2, saya terlibat dalam pengembangan dan integrasi beberapa komponen sistem antrean.

Kontribusi yang saya kerjakan meliputi:

**A. Implementasi FIFO**

Mengembangkan mekanisme antrean menggunakan metode First In, First Out (FIFO), sehingga pekerjaan diproses berdasarkan urutan masuk.

**B. Pengembangan Worker**

Mengembangkan `worker.sh` untuk mengambil pekerjaan dari antrean, menjalankan pekerjaan, dan menghapus pekerjaan dari antrean setelah berhasil diproses.

**C. Implementasi File Locking**

Menggunakan perintah `flock` untuk mengatur akses terhadap file antrean dan mencegah beberapa worker memproses antrean secara bersamaan.

**D. Script Penambahan Antrean**

Mengembangkan `tambah_antrean.sh` untuk menambahkan pekerjaan ke antrean serta memberikan ID unik pada setiap pekerjaan.

**E. Integrasi Sistem Status**

Mengintegrasikan worker dengan `monitoring/status.sh` agar setiap pekerjaan memiliki status:
- `waiting`
- `running`
- `success`
- `failed`

**F. Pengujian dan Dokumentasi**

Melakukan pengujian FIFO, keberhasilan pekerjaan, kegagalan pekerjaan, dan retry. Hasil pengujian juga didokumentasikan dalam `anggota2/dokumentasi/hasil-pengujian.md`.

**File utama yang dikerjakan:**
- `anggota2/tambah_antrean.sh`
- `anggota2/worker.sh`
- `anggota2/pekerjaan_dummy.sh`
- `anggota2/antrean.txt`
- `monitoring/status.sh`
- `anggota2/dokumentasi/hasil-pengujian.md`

### 4. Bukti Kontribusi

Kontribusi dapat diperiksa melalui repository GitHub kelompok berikut:

https://github.com/kelompok-sistem-antrean-linux/sistem_antrean_linux

Bukti kontribusi yang dapat ditampilkan meliputi:

1. Branch pengembangan: `anggota-2-integrasi-status`.
2. Commit integrasi: `cf2284b` – Integrate worker queue with job status system.
3. Pull Request integrasi worker dan sistem status yang telah di-merge ke branch `main`.
4. File implementasi worker, penambahan antrean, dan sistem status.
5. Dokumentasi hasil pengujian pada `anggota2/dokumentasi/hasil-pengujian.md`.

Bukti visual yang disertakan:
- Screenshot kode `worker.sh`.
  <img width="807" height="722" alt="WhatsApp Image 2026-11-18 at 08 53 26" src="https://github.com/user-attachments/assets/c838d494-db27-418c-8a8c-84d42f4ea99a" />
  <img width="884" height="719" alt="WhatsApp Image 2026-11-18 at 08 53 46" src="https://github.com/user-attachments/assets/eddde3bc-4c9d-448b-bbb8-f6cdaeef2110" />
  <img width="883" height="710" alt="WhatsApp Image 2026-11-18 at 08 54 00" src="https://github.com/user-attachments/assets/08c9397b-6dcc-4743-876f-0832a89a6cc9" />

- Screenshot kode `tambah_antrean.sh`.
  <img width="878" height="562" alt="WhatsApp Image 2026-11-18 at 08 54 58" src="https://github.com/user-attachments/assets/a2b4b4f2-8f3e-4fb7-98b5-dd3c866a8aed" />
  <img width="824" height="569" alt="WhatsApp Image 2026-11-18 at 08 55 10" src="https://github.com/user-attachments/assets/a5081a0b-404e-4ac5-96b1-630a294c086d" />

- Screenshot kode `monitoring/status.sh`.
  <img width="815" height="704" alt="WhatsApp Image 2026-11-18 at 08 55 58" src="https://github.com/user-attachments/assets/adb06a1c-1f6f-47a1-9881-a5237e69eb15" />
  <img width="800" height="731" alt="WhatsApp Image 2026-11-18 at 08 56 18" src="https://github.com/user-attachments/assets/9551b5b5-7d6a-44cb-b64c-3a2017f3b06b" />
<img width="775" height="751" alt="WhatsApp Image 2026-11-18 at 08 56 56" src="https://github.com/user-attachments/assets/5c4b55b4-59c4-4c30-a336-0c598a47cb98" />
<img width="697" height="443" alt="WhatsApp Image 2026-11-18 at 08 57 09" src="https://github.com/user-attachments/assets/1b50e2b4-523a-4204-b30a-232b99244dd0" />

- Screenshot pengujian FIFO.
  <img width="876" height="564" alt="WhatsApp Image 2026-11-18 at 08 58 03" src="https://github.com/user-attachments/assets/dd49e108-1413-4482-879d-41f523a911ba" />

- Screenshot status pekerjaan `success` dan `failed`.
  <img width="849" height="171" alt="WhatsApp Image 2026-11-18 at 08 58 49" src="https://github.com/user-attachments/assets/bc270f43-3f75-485f-9ca8-8a45881addea" />

- Screenshot pengujian retry.
  <img width="910" height="729" alt="WhatsApp Image 2026-11-18 at 08 59 45" src="https://github.com/user-attachments/assets/8cb55910-b0b6-4604-9502-91c77302aa08" />
<img width="916" height="459" alt="WhatsApp Image 2026-11-18 at 09 00 02" src="https://github.com/user-attachments/assets/97d66aa3-de7b-4827-aac6-9f07dac252ea" />

- Screenshot Pull Request GitHub yang menunjukkan status merged.
  <img width="917" height="617" alt="WhatsApp Image 2026-11-18 at 09 01 11" src="https://github.com/user-attachments/assets/def57934-5788-491c-833f-5ef905a3479f" />
<img width="814" height="698" alt="WhatsApp Image 2026-11-18 at 09 02 10" src="https://github.com/user-attachments/assets/efed0662-fc69-4973-acdf-7457bbd8ac6c" />

### 5. Skenario Individu

**Tujuan:**

Mengembangkan sistem antrean pekerjaan yang dapat memproses pekerjaan secara berurutan, menghindari pemrosesan bersamaan oleh worker, serta memantau status setiap pekerjaan.

**Langkah Pengujian:**

1. Menambahkan tiga pekerjaan, yaitu Pekerjaan A, Pekerjaan B, dan Pekerjaan C.
2. Memastikan ketiga pekerjaan masuk ke antrean dengan status `waiting`.
3. Menjalankan worker untuk memproses pekerjaan.
4. Memastikan urutan pemrosesan sesuai FIFO.
5. Memeriksa perubahan status pekerjaan menjadi `running` dan `success`.
6. Melakukan simulasi kegagalan dengan exit code 7.
7. Memastikan pekerjaan yang gagal tetap berada di antrean.
8. Memulihkan script pekerjaan dan menjalankan worker kembali untuk menguji retry.

**Hasil Pengujian:**

- Pekerjaan A, B, dan C berhasil diproses sesuai urutan.
- Status pekerjaan berhasil berubah dari `waiting` menjadi `running`, kemudian `success`.
- Pengujian kegagalan menghasilkan status `failed` dengan exit code 7.
- Pekerjaan yang gagal tetap tersimpan di antrean.
- Setelah dilakukan retry, pekerjaan berhasil diproses dan status akhirnya menjadi `success` dengan exit code 0.
- Antrean menjadi kosong setelah semua pekerjaan berhasil diselesaikan.

**Verifikasi:**

Hasil pengujian diverifikasi melalui output terminal, file status pekerjaan pada `data/jobs/`, log worker, dan dokumentasi hasil pengujian.

### 6. Analisis Konsep Sistem Operasi

Pekerjaan yang saya lakukan berkaitan dengan beberapa konsep Sistem Operasi yang dipelajari dalam perkuliahan.

**A. Manajemen Proses**

Worker menjalankan pekerjaan sebagai proses di Linux. Setiap pekerjaan dieksekusi melalui script Bash dan memiliki proses yang dapat diidentifikasi menggunakan PID.

**B. Sinkronisasi dan Mutual Exclusion**

Penggunaan `flock` merupakan penerapan konsep sinkronisasi untuk mengatur akses terhadap sumber daya bersama. Lock membantu mencegah worker lain mengakses dan memproses antrean secara bersamaan.

**C. Manajemen Antrean**

Metode FIFO menunjukkan pengelolaan antrean berdasarkan urutan kedatangan pekerjaan. Pekerjaan yang masuk lebih awal diproses lebih dahulu.

**D. Status Proses dan Exit Status**

Sistem status digunakan untuk memantau tahapan pekerjaan. Exit status digunakan untuk membedakan pekerjaan yang berhasil dan gagal dijalankan.

**E. Manajemen File dan Hak Akses**

Penggunaan file antrean, file lock, serta pengaturan permission dengan `chmod` dan `umask` berkaitan dengan pengelolaan file dan keamanan akses pada sistem Linux.

### 7. Kendala dan Penyelesaian

Selama pengerjaan proyek, saya mengalami kendala pada perangkat pribadi. Laptop saya belum dapat digunakan untuk menjalankan lingkungan Linux yang diperlukan dalam pengembangan dan pengujian Bash Shell Script.

Untuk mengatasi kendala tersebut, saya menggunakan laptop milik teman yang dapat mengakses Google Cloud Shell sebagai lingkungan kerja Linux.

Dengan cara tersebut, proses pengembangan script, pengujian worker, pemeriksaan antrean, pengelolaan Git, dan integrasi ke GitHub tetap dapat dilakukan.

Kendala lainnya adalah proses integrasi antara worker dan sistem status. Pada awalnya, worker hanya memproses nama pekerjaan dan belum memperbarui status pekerjaan secara otomatis.

Penyelesaian dilakukan dengan menambahkan ID unik pada setiap pekerjaan dan menghubungkan script worker dengan `monitoring/status.sh`. Setelah integrasi, perubahan status pekerjaan dapat dicatat secara otomatis.

### 8. Refleksi

Melalui pengerjaan proyek ini, saya memperoleh pemahaman dan pengalaman dalam:

- Menggunakan Bash Shell Script untuk mengembangkan sistem antrean.
- Memahami penerapan metode FIFO.
- Menggunakan worker untuk menjalankan pekerjaan secara otomatis.
- Memahami konsep sinkronisasi dan mutual exclusion melalui `flock`.
- Mengelola status proses menggunakan exit status.
- Menggunakan Git dan GitHub untuk kolaborasi serta integrasi kode.
- Melakukan pengujian terhadap kondisi berhasil, gagal, dan retry.

Hal yang masih perlu saya pelajari lebih lanjut adalah pengelolaan proses secara lebih kompleks, penanganan kegagalan worker ketika proses terhenti secara tiba-tiba, serta pengembangan sistem monitoring yang lebih lengkap.

Secara keseluruhan, proyek ini memberikan pengalaman praktis dalam menerapkan konsep Sistem Operasi ke dalam program berbasis Linux dan meningkatkan kemampuan saya dalam bekerja secara kolaboratif menggunakan GitHub.

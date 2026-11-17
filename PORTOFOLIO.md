PORTOFOLIO INDIVIDU

PROJEK AKHIR SISTEM OPERASI - KELOMPOK 4

1. IDENTITAS
  Nama: Jennar Iqlima Rakhman
  NIM: 2510512176
  Program Studi: S1 Sistem Informasi
  Mata Kuliah: Sistem Operasi
  Judul Proyek: Sistem Antrean Pekerjaan dan Monitoring Proses Linux (5B)

2. Asal Proyek
   Proyek ini merupakan proyek kelompok yang dikerjakan secara kolaboratif oleh enam anggota untuk memenuhi tugas akhir mata kuliah Sistem Operasi.

   Repository utama Kelompok: https://github.com/kelompok-sistem-antrean-linux/sistem_antrean_linux

   Tanggung jawab dalam kelompok:
   Anggota 2: Antrean dan Lock

   Pada bagian Antrean dan Lock (Anggota 2), pengerjaan dilakukan secara kolaboratif oleh saya bersama satu anggota kelompok lainnya (Fathimah Asrining Nurcahya Pertiwi), mulai dari implementasi, pengujian, hingga penyusunan dokumentasi.

   3. Kontribusi Pribadi

  Dalam proyek ini, saya bertanggung jawab sebagai salah satu anggota yang mengerjakan bagian Antrean dan Lock bersama rekan satu kelompok.

  Ruang lingkup pekerjaan pada bagian ini meliputi:

    1. Mengimplementasikan mekanisme antrean pekerjaan menggunakan konsep FIFO (First In, First Out).
    2. Memastikan pekerjaan diproses berdasarkan urutan masuk ke dalam antrean.
    3. Mengimplementasikan mekanisme worker lock untuk mencegah dua worker memproses antrean secara bersamaan.
    4. Melakukan pengujian terhadap kondisi positif dan negatif sesuai skenario yang telah ditentukan.
    5. Menyusun dokumentasi hasil pengujian sebagai bukti implementasi.

  Pengerjaan dilakukan secara bersama-sama menggunakan lingkungan Linux pada laptop rekan satu kelompok. Melalui kolaborasi tersebut, saya turut terlibat dalam proses implementasi, pemeriksaan hasil, dan pengujian mekanisme antrean serta lock.
  Pengerjaan implementasi dilakukan secara kolaboratif menggunakan laptop salah satu anggota kelompok. Oleh karena itu, riwayat commit pada repository kelompok juga menjadi salah satu bukti aktivitas pengembangan bersama.

4. Bukti Kontribusi
  * Repository utama kelompok: https://github.com/kelompok-sistem-antrean-linux/sistem_antrean_linux
  * Repository pribadi: https://github.com/jennariqlima-boop/sistem_antrean_linux
  * Dokumentasi pengujian: anggota2/dokumentasi/hasil-pengujian.md
  * Source code implementasi: 
  * Bukti pengujian: 

5. Skenario Pengujian Individu
   A. Pengujian Positif - Antrean FIFO
       Tujuan:
         Memastikan pekerjaan diproses sesuai urutan masuk ke dalam antrean.

           Langkah pengujian:
   1. Memasukkan tiga pekerjaan ke dalam antrean.
   2. Memastikan pekerjaan tercatat berdasarkan urutan pengajuan.
   3. Menjalankan worker untuk memproses antrean.
   4. Mengamati urutan pekerjaan yang diproses.

    Hasil yang diharapkan:
    Ketiga pekerjaan diproses sesuai urutan masuk menggunakan mekanisme FIFO.

    Hasil pengujian:
    Berdasarkan dokumentasi pengujian, tiga pekerjaan berhasil dimasukkan ke dalam antrean dan worker berhasil menjalankan pekerjaan sesuai urutan masuk.

    Status: LULUS.

   B. Pengujian Negatif - Worker Lock
       Tujuan: 
         Memastikan worker kedua tidak dapat memperoleh lock ketika worker pertama masih menggunakan mekanisme penguncian.

            Langkah pengujian:

  1. Menjalankan worker pertama.
  2. Memastikan worker pertama berhasil memperoleh lock.
  3. Mencoba menjalankan worker kedua ketika lock masih digunakan.
  4. Mengamati respons sistem terhadap worker kedua.

    Hasil yang diharapkan:
    Worker kedua ditolak karena lock telah digunakan oleh worker pertama sehingga pemrosesan antrean tidak dilakukan secara bersamaan.

    Hasil pengujian: [Lengkapi berdasarkan hasil pengujian negatif yang sebenarnya].
    Status: [Lulus/Gagal].

6. Analisis Konsep Sistem Operasi
  Implementasi antrean FIFO berkaitan dengan konsep pengelolaan dan pengurutan pekerjaan. Mekanisme ini memastikan pekerjaan yang masuk lebih dahulu akan diproses lebih dahulu.
  Sementara itu, worker lock berkaitan dengan konsep sinkronisasi dan mutual exclusion. Mekanisme penguncian digunakan untuk membatasi akses terhadap proses pemrosesan antrean sehingga hanya satu worker yang dapat menggunakan lock pada satu waktu.
  Penerapan tersebut juga berkaitan dengan critical section, yaitu bagian program yang mengakses resource bersama dan perlu dilindungi dari akses bersamaan yang dapat menimbulkan konflik atau pemrosesan ganda.

7. Kendala dan Penyelesaian

  Kendala:
  Selama pengerjaan, implementasi dilakukan menggunakan laptop rekan satu kelompok sehingga proses pengembangan dan pengujian dilakukan dalam satu lingkungan kerja bersama. Selain itu, dokumentasi dan file implementasi perlu disusun agar hasil pekerjaan dapat diintegrasikan dengan repository utama kelompok.

  Penyelesaian:
  Pengerjaan dilakukan melalui koordinasi dan pembagian tugas bersama rekan satu kelompok. Hasil implementasi kemudian diuji dan didokumentasikan agar dapat diperiksa serta diintegrasikan ke dalam repository proyek.

8. Refleksi
  Melalui pengerjaan proyek ini, saya memperoleh pemahaman mengenai penerapan konsep FIFO dalam pengelolaan antrean pekerjaan serta penggunaan mekanisme lock untuk mengatur akses beberapa proses terhadap resource bersama.
  Saya juga mempelajari hubungan antara shell scripting dengan konsep sinkronisasi, mutual exclusion, critical section, dan pengelolaan proses pada sistem operasi Linux.
  Selain aspek teknis, pengerjaan secara kolaboratif memberikan pengalaman dalam berkoordinasi, melakukan pengujian bersama, serta mendokumentasikan hasil implementasi agar dapat digunakan dan dipahami oleh anggota kelompok lainnya.

  

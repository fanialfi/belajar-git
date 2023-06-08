# belajar git

## Version Control System

adalah sebuah system yang merekam perubahan pada file dari waktu ke waktu, sehingga kita bisa melihat versi sebelumnya jika di inginkan.Tapi tidak hanya untuk file dalam bentuk text, misal jika kita seorang Grapic Designer, kita juga bisa memanfaatkan Version Control untuk merekam perubahan dari file gambar atau layout, sehingga tidak perlu membackup setiap perubahan secara manual.

## Tipe Version Control

### Local Version Control

merupakan version control yang berjalan hanya di local computer, biasanya digunakan karena sederhana dan tidak butuh server, karena semua riwayat disimpan didalam local computer, kekurangannya adalah ketika komputer-nya rusak, maka hilang semua data nya.

### Centralized Version Control

masalah yang terjadi pada Local Version Control adalah, jika komputer rusak maka seluruh data bisa hilang, selain itu agak sulit untuk berkolaborasi dengan pengguna lain jika file hanya ada di satu komputer. Untuk menangani masalah ini, kita bisa menggunakan Centralized Version Control, Centralized Version Control menyimpan seluruh data revisi di Server. jadi semua riwayat history versi nya disimpan di server, tidak lagi di simpan di local computer. Pengguna bisa mengakses data ke Server untuk melihat file, dan yang di simpan di local hanya versi terakhir.

kekurangannya adalah, jika pengguna nya offline, maka tidak bisa melihat riwayat file, karena semua riwayat-nya disimpan di server. Jika server nya down, maka seluruh pengguna tidak bisa melakukan perubahan dan melihat revisi file.

### Distributed Version Control

adalah alternatif lain dari Centralized Version Control. Dalam DVCs, client tidak hanya mengambil file versi terakhir, namun semua riwayat revisi di copy seluruhnya ke local computer. Hal ini menjadikan jika terjadi masalah dengan server, client masih tetap bisa bekerja. Bahkan dalam DVCs server bisa lebih dari satu.

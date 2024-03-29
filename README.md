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

## Pengenalan GIT

### Sejarah GIT

Git muncul dengan latar belakang OpenSource project Linux Kernel. Tahun 1991 - 2002, linux kernel di develop hanya dengan memanfaatkan patch dan archived files. Pada tahun 2003 Linux Kernel mulai menggunakan DVCs bernama BitKeeper, namun sekitar tahun 2005, hubungan antara perusahan pemilik BitKeeper dengan komunitas Linux Kernel kurang baik, sehingga pembuat linux pertama, Linus Torvalds mulai membuat DVCs sendiri namanya adalah git,

Git pertama kali dikenalkan tahun 2005, semakin kesini git semakin populer dan sekarang menjadi DVCs yang paling populer di dunia.

Git sangat cepat, ringan dan baik dalam me manage project dalam ukuran besar.

### GIT

git adalah salah satu DVCs yang ada, git tidak memerlukan server untuk melakukan perubahan atau melihat riwayat revisi, hal ini dikarenakan dalam git, semua riwayat project akan selalu di duplikasi, baik di server maupun di local computer.

setiap perubahan yang terjadi di git, git akan selalu membuat signature / penanda menggunakan algoritma hashing SHA-1, hal ini menjadikan perubahan sekecil apapun pasti bisa di deteksi oleh git.

semuah hal ini terjadi karena didalam git secara otomatis akan di catat, hal ini menjadikan perubahan apapun di git, pasti bisa dikembalikan ke versi sebelumnya.

## Configuration

setelah selesai meng install git, hal pertama kali dilakukan adalah melakukan konfigurasi. yang paling utama adalah konfigurasi username dan email,

`git config --global user.name "username"`.

`git config --global user.email "email@example.com"`

## repository

repository merupakan sebutah project di git, kita bisa membuat folder kosong atau folder yang sudah berisi file, lalu membuatnya sebagai git repository, atau bisa melakukan clone repository yang sudah ada dari server git.

untuk membuat repository, kita hanya perlu menggunakan perintah `git init`, dan dilakukan dari dalam folder yang akan dijadikan sebagai git repository.

## workflow

### the three states

git memiliki 3 state terhadap file kita, yaitu : `modified`, `staged`, `commited`,

- `modified` artinya kita mengubah file, namun belum di simpan secara permanen ke repository.
- `staged` artinya kita menandai modifikasi yang kita lakukan terhadap file akan disimpan secara permanen ke repository.
- `commited` artinya data sudah aman disimpan di repository.

### Three Section

Tiga state sebelumnya di dalam Git dilakukan di section yang berbeda-beda, yaitu Working Directory, Staging Area dan Repository. saat kita melakukan modifikasi file, itu dilakukan di `Working Directory`, `Staging Area` atau `Staging Index` merupakan section dimana file sudah disiapkan untuk disimpan secara permanen, di Staging Area semua informasi perubahan file akan disimpan. `Repository` merupakan tempat dimana semua file dan database riwayat versi file disimpan

secara sederhana, setiap perubahan akan dilakukan di `Working Directory`, jika ada yang mau kita siapkan untuk di simpan secara permanen, kita bawa perubahan tersebut ke dalam `Staging Index` atau `Staging Area`, selanjutnya, kita bisa melakukan penyimpanan versi baru secara permanen ke repository.

## Hash

### snapshot

sebenarnya perubahan yang dilakukan bisa jadi dilakukan secara bersamaan untuk beberapa file, hal ini berarti sebenarnya tidak ada yang namanya versi file. Semua perubahan yang terjadi akan di rekam, dan kita sebut namanya snapshot. snapshot berisikan semua perubahan yang terjadi di semua file yang kita commit, dan setiap snapshot akan menghasilkan hash (sebagai id dari snapshot).

### Hash

setiap snapshot yang dilakukan, semua akan menghasilkan hash sebagai identitas dari snapshot-nya. Hash merupakan checksum untuk menghitung perubahan yang terjadi, git menggunakan algoritma SHA-1 untuk menghitung hash, hash dibutuhkan untuk menjaga data integrity, sehingga tiap snapshot yang sudah dilakukan tidak bisa diubah.

### Head

head merupakan pointer menuju hash paling akhir, karena kadang sangat menyulitkan jika harus menuliskan hash value, jika ingin menuju ke hash paling baru, bisa dengan menggunakan kata `HEAD`.

## menambahkan file

untuk menambahkan file baru ke repository, cukup tambahkan file nya saja. Secara otomatis file yang di tambahkan awalnya akan berada di working directory, secara default saat menambahkan file baru, file tersebut tidak akan di track perubahannya, agar perubahannya di track, maka harus di pindahkan ke Staging index.

## mengubah file

untuk melakukan perubahan file, cukup lakukan perubahan terhadap file yang sudah ada di repository maka secara otomatis git bisa mendeteksi perubahannya, sama seperti dengan menambahkan file, jika perubahan ingin disimpan secara permanen, maka bisa dipindahkan ke staging index, lalu commit ke repository.

## menghapus file

untuk menghapus file di repository, cukup lakukan delete file di folder-nya maka secara otomatis git akan mendeteksi file yang hilang. Sama seperti menambah dan menghapus, jika perubahan ingin disimpan secara premanen di repository, maka harus menambahkan operasi tersebut ke staging index, lalu commit ke repository.

#### command

- `git status` : digunakan untuk mengecek perubahan apa yang terjadi di repository.
- `git add *namaFile* ` : digunakan untuk memindahkan file ke Staging index / Staging area.
- `git commit -m *pesan commit*` : digunakan untuk memindahkan semua file yang berada di staging index ke dalam repository.
- `git diff` : digunakan untuk melihat perubahan apa saja yang terjadi didalam file tertentu.
- `git clean -f` : digunakan untuk membatalkan penambahan file yang ada didalam working directory.
- `git restore namaFile` : digunakan untuk membatalkan perubahan pada file.
- `git restore --staged namaFile` : digunakan untuk mengembalikan posisi file dari Staging Index ke Working Directory.
- `git log` : digunakan untuk melihat commit log.
- `git show hash` : digunakan untuk melihat detail perubahan yang terjadi pada sebuah commit.

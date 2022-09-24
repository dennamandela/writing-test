# First Week Writing and Presentation Test
## Command Line Interface
- Shell merupakan program yang digunakan untuk berkomunikasi atau memerintah sistem.
- Command Line Interface (CLI) yaitu jenis shell yang berbasis teks.

  Command Line Interface ada banyak macamnya. CLI bawaan sistem operasi contoh nya adalah cmd.exe milik windows atau bash dan zsh di sistem operasi mirip Unix.
  
- mengakses CLI dan menggunakan bash ![Command Line Interface](/week-1/mengakses-cli.png)
### A. Filesystem
- Sebuah filesystem mengatur bagaimana data disimpan di dalam sebuah system
  
  Cara sistem operasi menyusun file-filenya dalam bentuk hierarki atau tree

  ![Command Line Interface](/week-1/filesystem.png)

### B. Command untuk Navigasi
- pwd (print working directory) untuk melihat nama direktori kita berada saat ini.
- ls (lists) untuk melihat isi dari direktori.
- cd (change directory) untuk pindah ke direktori lain.
### C. Membuat files & direktori
- touch untuk membuat sebuah file
- mkdir untuk membuat sebuah direktori
### D. Melihat isi files
- head untuk melihat beberapa line awal dari sebuah file text
- tail untuk melihat beberapa line awal dari sebuah file text
- cat untuk melihat isi sebuah file
### E. Menyalin, memindahkan, dan menghapus file & direktori
- cp untuk mengcopy files atau direktori
- mv untuk memindahkan files atau direktori. bisa digunakan untuk rename.
- rm untuk menghapus file atau direktori.

## Git & GitHub Dasar
- GIT adalah Tools untuk programmer
- GIT sebagai Version Control System, tugasnya adalah **mencatat** setiap **perubahan** pada **File** (termasuk code yang kita buat) pada suatu proyek baik dikerjakan secara **individu** maupun **tim**.
- Git adalah aplikasi yang dapat melacak setiap perubahan yang terjadi pada suatu folder atau file.
- Perbedaan Git dan GitHub yaitu: Developer yang menggunakan Git dapat menggunakan command-line tool, yaitu pengubah kode dan dapat digabungkan menuju perangkat lokal. sedangkan, GitHub menyediakan interface grafis berbasis cloud sebagai tempat untuk melakukan seluruh tugas.
- MENGAPA harus menggunakan GIT dan Github? Dengan menggunakan GIT dan Github, akan bisa bekerja dalam sebuat tim. Tujuan besarnya adalah bisa berkolaborasi mengerjakan proyek yang sama tanpa harus repot copy paste folder aplikasi yang terupdate.
Dan juga tidak perlu menunggu rekan dalam satu tim menyelesaikan suatu program dahulu untuk berkolaborasi. Kamu bisa membuat file didalam projek yang sama atau membuat code di file yang sama dan menyatukannya saat sudah selesai.

### Setup Awal
- konfigurasi git

  git config --global user.name "dennamandela"
  
  git config --global user.email denna.mandela13@gmail.com
  
- Membuat repository

  git init (dilakukan didalam folder yang dibuat)
  
- git status digunakan untuk mengetahui sebuah status dari repository lokal.
- git add digunakan untuk menambahkan file baru di repository yang dipilih.
- git commit -m "commit pertama "digunakan untuk menyimpan perubahan yang sudah dilakukan, namun tidak ada perubahan yang terjadi pada remote repository.
- git branch -m [nama branch] digunakan untuk menambahkan fitur baru atau memperbaiki bug.
- git remote digunakan untuk petunjuk ke versi repositori yang biasanya disimpan di server lain.
- git push -u origin main digunakan untuk mengirimkan perubahan file yang dilakukan setelah di commit ke remote repository.
- git clone digunakan untuk membuat salinan repository lokal.

## HTML
- HTML atau Hyoertext Markup Language digunakan untuk menampilkan konten pada browser.
- Tools yang dibutuhkan untuk membuat HTML yaitu Browser dan Code Editor.
- Visual Studio Code adalah code editor yang dikembangkan oleh tim Engineer Microsoft.
- Keunggulan Visual Studio Code dapat digunakan di Windows, Mac, dan juga Linux.
- HTML Structure
```
<!DOCTYPE html>
<html lang="en"
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
</title>
<body>
  This is my very first page writing with HTML
</body>
</html>
```
- Tag-tag wajib

1. ```<!DOCTYPE html>``` yaitu tag untuk deklarasi type dokumen.
2. ```<html>``` yaitu tag utama dalam HTML.
3. ```<head>``` yaitu tag untuk bagian kepala dari dokumen.
4. ```<title>``` yaitu tag untuk judul web
5. ```<body>``` yaitu tag bagian body dari dokumen.

- HTML Element terdiri opening tag dan closing tag.
1. opening tag: ```<p>```
2. content: Hello World
3. closing tag: ```</p>```

- Attribute adalah properties dari sebuah HTML Element seperti id, class, src, href, dll.
- HTML Comment dapat memberikan penjelasan atau keterangan maksud dari line code yang kita kerjakan ```<!-- -->```
- Cara menjalankan HTML bisa secara manual pada browser dan bisa menggunakan live server dari VS Code.
- Tag HTML Populer yang Wajib Programmer Pemula Ketahui
1. Tag untuk Membuat tulisan tebal dan miring, code ```<b>Bold</b>``` dan ```<i>Miring</i>```
2. Tag HTML untuk membuat tulisan dengan link ```<a href=”https://mandela.com”> Mandela </a>```
3. Tag Untuk Membuat Daftar/List
  **Ordered List**
    ```<ol> Mandela </ol>```
  **Unordered List**
    ```<ul> Mandela </ul>```
4. Tag Untuk Menyisipkan Gambar
```<img src=framework.jpg”>```

  




  






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
-konfigurasi git

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



  






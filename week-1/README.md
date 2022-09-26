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

### B. Perintah Dasar CLI (Command Line Interface 
- pwd (print working directory) untuk melihat nama direktori kita berada saat ini.
- ls (lists) untuk melihat isi dari direktori.
- cd (change directory) untuk pindah ke direktori lain.
- touch untuk membuat sebuah file
- mkdir untuk membuat sebuah direktori
- head untuk melihat beberapa line awal dari sebuah file text
- tail untuk melihat beberapa line awal dari sebuah file text
- cat untuk melihat isi sebuah file
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
- Tag HTML Populer yang Wajib Programmer Pemula Ketahui yaitu img, video, table, dan form.

  Contoh Pembuatan Video:
  
```
<!DOCTYPE html>
<html lang="en">
  <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Document</title>
  </head> 
  <body>
    
    <video controls>
      <source src="movie.mp4" type="video/mp4">
    </video>
    
  </body>
</html>
```
- Semantic HTMl yaitu menggunakan element HTMl sesuai dengan kebutukan konten. contohnya: article, aside, details, figcaption, footer, dll.
- Kegunaan Semantic HTML yaitu, meningkatkan Accessibility, meningkatkan SEO, lebih mudah di maintain.
- contoh kode Semantic HTML:
```
<header>
    <h1>Belajar Elemen Semantik di HTML</h1>
  </header>

  <nav>
    <a href="#">Home</a> |
    <a href="#">About</a> |
    <a href="#">Contact</a>
  </nav>

  <article>
    <h1>Tutorial Semantik Elemen untuk Pemula</h1>
    <p>Semantik elemen adalah elemen yang memiliki makna dan tujuan.
      Tujuannya agar kode HTML mudah dibaca dan tidak ada penyalahgunaan tag.
      Elemen semantik bagus untuk SEO dan juga dapat meningkatkan accessibility.
    </p>
  </article>

  <footer>
    Copyright &copy; 2020 by Denna Mandela
  </footer>
  ```
- Deploy adalah sebuah proses untuk menyebarkan aplikasi yang sudah kita kerjakan supaya bisa digunakan oleh orang-orang.
- Cara mendeploy html menggunakan tools bernama Netlify.

## CSS
- CSS atau *Cascading Style Sheet* adalah bahasa yang digunakan untuk mendesain halaman website.
- Struktur CSS
```
.elementHTML {
  property : value
}
```
- CSS Comment yaitu memberikan keterangan maksud dari line code yang dikerjakan ``` /* */```.
- Ada 3 cara menyisipkan CSS ke dalam HTML.

  Inline styles adalah kita menambahkan CSS pada **attribute** element HTML

  ```
  <p style="color: coral; font-size: 36px;">This is paragraph using inline styles</p>
  ```

  Internal CSS adalah kode CSS yang ditulis dalam tag<style> dan kode HTML yang ditulis di bagian header file HTML.

  ```
  <style></style>
  ```
  
  External CSS adalah kode CSS yang diletakkan di luar dokumen HTML sebagai file .css.

- Sintaks CSS terdiri dari tiga bagian: pemilih atau selektor (selector), sifat atau properti (property), dan nilai (value).
- Contoh sintaks dasar dari CSS:
  
  ```
  h1 {
    color: red;
  }
  ```

- Ada beberapa cara yang bisa digunakan sesuai kebutuhan untuk mendesain element HTML di CSS.
  
  Tag Name: Selektor ini akan memilih elemen berdasarkan nama tag.
  
  ```
  p {
    color: blue;
  }
  ```
  
  Tag Class: selektor yang memilih elemen berdasarkan nama class yang diberikan.
  
  ```
  .pink {
    color: white;
    background: pink;
    padding: 5px;
  }
  ```
  
  Tag ID: Selektor ID hampir sama dengan class. Bedanya, ID bersifat unik. Hanya boleh digunakan oleh satu elemen saja.
  
  ```
  #header {
    background: teal;
    color: white;
    height: 100px;
    padding: 50px;
  }
  ```

  Nested Element: setiap element memiliki parent dan child.
  
  !important CSS: jika pada styling CSS menggunakan !important, maka styling sebelumnya baik itu ID Name atau Class Name akan di override.
  
  ```
  h1.title {
    color: green;
  }
  ```

- Responsive web design atau desain web responsif adalah sebuah teknik atau metode bagi web designer untuk membuat suatu layout website yang dapat menyesuaikan diri sesuai dengan ukuran layar pengguna.
  
  Fluid Grid: sebuah grid atau garis-garis batas yang menentukan letak suatu komponen dalam desain.
  
  Media queries: untuk dapat mengambil data mengenai ukuran layar yang digunakan untuk menampilkan konten.
  
  Responsive media: media seperti foto dan video dapat ditampilkan dengan baik di berbagai ukuran layar.

- Flexbox yaitu memberikan container kemampuan untuk mengatur panjang, lebar, dan posisi item-item yang berada di dalamnya agar memaksimalkan ruang yang ada.
- beberapa property container flexbox diantaranya:
  
  flex-direction: Menentukkan arah (direction) yang akan diberlakukan untuk item-item yang ada pada container flexbox.
  
  flex-wrap: untuk mendefinisikan bahwa elemen item di dalam container flexbox tidak harus disejajarkan dalam satu baris.
  
  justify-content: untuk mensejajarkan item-item diantara flexbox agar container dari flexbox.
  
  align-items: bagaimana item-item pada container flex tersebut diletakkan sepanjang garis tegak lurus pada sumbu utama (cross-axis).  
  
## Algorithms and Data Structures
- Algoritma adalah deskripsi berupa step-step yang dibutuhkan untuk menyelesaikan suatu masalah.
- Struktur data adalah cara penyimpanan , pengorganisasian , dan pengaturan data di dalam media penyimpanan komputer sehingga data tersebut dapat digunakan secara efisien. Algoritma adalah sederetan langkah-langkah logis yang disusun secara sistematis untuk memecahkan suatu masalah.
- Ciri-ciri Algoritma
  
  - Input: memiliki 0 atau lebih inputan.
  - Ouput: memiliki min 1 buah output
  - Definiteness: Instruksi jelas tidak ambigu
  - Finitess: Memiliki titik berhenti (stop)
  - Effectiveness: Sebisa mungkin tepat sasaran dan efisien

- Jenis Proses Algoritma
  
  - Sequence: Instruksi yang dijalankan secara berurutan
  - Selection: Instruksi yang dijalankan jika memenuhi suatu kondisi
  - Iteration: Instruksi yang berulang kali dijalankan selama memenuhi suatu kondisi.
  - Concurrent: Instruksi yang dijalankan secara bersamaan.

- Penyajian Algoritma
  
  - Deskriptif 
  - Flowchart
  - Pseudocode

- Contoh Algoritma
```
Mengambil air minum:
Pergi ke dapur
Ambil gelas di rak
Pergi ke dispenser
Isi Gelas dengan air
Jika air sudah penuh
Air siap diminum
```
  
- Flowchart atau bagan alur adalah diagram yang menampilkan langkah-langkah dan keputusan untuk melakukan sebuah proses dari suatu program.
- Fungsi utama dari flowchart adalah memberi gambaran jalannya sebuah program dari satu proses ke proses lainnya. 
- Jenis flowchart
  - Flowchart dokumen: untuk menelusuri alur form dari satu bagian ke bagian yang lain, termasuk bagaimana laporan diproses, dicatat, dan disimpan.
  - Flowchart program: menggambarkan secara rinci prosedur dari proses program.
  - Flowchart proses: cara penggambaran rekayasa industrial dengan cara merinci dan menganalisis langkah-langkah selanjutnya dalam suatu prosedur atau sistem.
  - Flowchart sistem: flowchart yang menampilkan tahapan atau proses kerja yang sedang berlangsung di dalam sistem secara menyeluruh.
  - Flowchart skematik: menampilkan alur prosedur suatu sistem, hampir sama dengan flowchart sistem.

- Contoh Flowchart:
![Contoh Flowchart](/week-1/Contoh-flowchart.jpg "Contoh Flowchart")

- Pseudocode adalah menuliskan algoritma dengan umumnya bahasa inggris sebelum kita implementasikan ke bahasa pemograman tertentu.
- Panduan menulis Pseudocode
  - Menggunakan HURUF BESAR pada kata kunci (key commands).
  - 1 statement =  1 baris 
  - Gunakan indentasi
  - Please please be specific
  - simpel.

- Contoh Pseudocode
```
Menampilkan deret angka 1 - 10
deklarasi
  i ← 1
deskripsi
  while i <= 10
    print i
    i = i + 1
  end
```
- Jenis-jenis Pseudocode
  - Procedural: cara berpikir secara runtun
  - Conditional: digunakan saat dibutuhkan percabangan kasus.
  - Looping: dapat melakukan sebuah proses yang sama berulang-ulang.
  - Recursive: pola pikir dalam algoritma yang memanggil method/function didalam sebuah function.

## JavaScript
### JavaScript Introduction
- JavaScript adalah bahasa pemrograman yang sangat powerful yang digunakan untuk logic pada sebuah website.
- Cara menjalankan JavaScript yaitu melalui browser pada device setiap user.
- Pada JavaScript dikenal dengan istilah **Syntax** dan **Statement**.
  > Syntax adalah seperangkat aturan yang menentukan program JavaScript yang terstruktur dengan benar.
  >
  > Statement adalah sebuah intruksi untuk dieksekusi oleh web browser.

- Contoh Syntax JavaScript
  - Alert()
  - Prompt()
  - Confirm()

- Console Log adalah tempat untuk cek logic dan tempat untuk melakukan debugging (mengetahui error pada code) pada pemograman web. 
- Comments adalah sintaks yang digunakan untuk memberi keterangan tentang suatu statement. 
  - Single Comments ```//```
  - Multiline Comments ```/* */```

### Tipe Data (Data Types)
- *Tipe Data* adalah jenis-jenis data yang bisa disimpan di dalam variabel.
- Ada 6 Tipe data pada JavaScript:
  - number: tipe data yang mengandung semua angka termasuk angka desimal.
  - string: grup karakter yang ada pada keyboard laptop/PC kita yaitu letters (huruf), number (angka), spaces (spasi), symbol, dan lainnya. 
  - boolean: tipe data yang hanya mempunyai 2 buah nilai.
  - null: tipe data yang diartikan bahwa sebuah variable/data tidak memiliki nilai.
  - undefined: tipe data yang merepresentasikan varibel/data yang tidak memiliki nilai.
  - object: koleksi data yang saling berhubungan (related). Tipe data pbject dapat menyimpan data dengan tipe data apapun (number, string, boolean, dan lainnya).

### Variabel
- Variabel adalah container/tempat untuk menyimpan sebuah nilai.
- 3 hal yang dapat dilakukan pada variabel
  - Membuat variabel dengan nama yang jelas dan menggambarkan tentang data tersebut
  - Menyimpan dan mengupdate informasi/data yang disimpan
  - Mendapatkan/menampilan data yang tersimpan
	
- Ada 3 cara mendefinisikan sebuah variabel.
  - var
  - let
  - const

### Operator
- Assignment Operator (=) digunakan untuk menyimpan sebuah nilai pada variabel, Contohnya: ```let myName = 'Mandela';```
- Mathematical Assignment Operator merupakan **Operator** yang biasa digunakan pada operasi perhitungan matematis, atau bisa disebut juga dengan **Operator** yang digunakan untuk melakukan perhitungan.
- Contohnya:
``` 
let 4 = 4;
w = w + 1;

console.log(w); // Output: 5
```
- Increment dan Decrement untuk menambah atau mengurangi sebesar 1 nilai.
- Contohnya:
```
let a = 10;
a++;
console.log(a); // Output: 11

let b = 20;
b--;
console.log(b); // Output: 19
```
- Arithmetic Operator adalah operator yang melibatkan operasi matematika.
  - Tambah (+)
  - Kurang (-) 
  - Perkalian (*)
  - Pembagian (/)
  - Modulus (%)

- Comparison Operator adalah operator yang membandingkan satu nilai dengan nilai lainnya.
  - Lebih kecil dari: ```<```
  - Lebih besar dari: ```>```
  - Lebih kecil atau sama dengan: ```<=```
  - Lebih besar atau sama dengan: ```>=```
  - Sama dengan: ```===```
  - Tidak sama dengan: ```!==```

- Logical Operator digunakan untuk sebuah CONDITIONAL pada pemograman.
- Menghasilkan nilai BOOLEAN yaitu TRUE or FALSE.
- Simbol dari Logical Operator adalah sebagai berikut:
  - AND operator: menghasilkan nilai true jika kedua atau semua premis bernilai TRUE ```&&```
  - OR operator: menghasilkan nilai true jika salah satu premis mengandung nilai TRUE ```||```
  - NOT operator: membalikkan sebuah nilai BOOLEAN. TRUE menjadi FALSE dan sebaliknya. ```!```

### Conditional
- Conditional merupakan *statement percabangan* yang menggambarkan suatu *kondisi*.
- Conditional statement akan mengecek kondisi spesifik dan menjalankan perintah berdasarkan kondisi tersebut
- Contoh Conditional dalam kehidupan
  - Jika cuaca cerah hari ini, maka kita akan pergi keluar
  - Jika alarm berbunyi, maka kita akan bangun dari tidur
  - Jika lelah, maka kita akan istirahat
  - Jika lapar, kita akan makan
- Contoh IF Statement
```
let lapar = true;
if (lapar) {
  console.log('Yuk makan');
};
```
- IF ... ELSE Statement: Else akan mengeksekusi sebuah statement/code jika suatu kondisi bernilai **FALSE**
- Contoh IF ... ELSE Statement
```
let lapar = false;
if (lapar) {
  console.log('Yuk makan');
} else {
  console.log('Tidak makan');
}
```
- IF .. ELSE IF Statement dapat digunakan jika mempunyai berbagai kondisi.
Contoh IF .. ELSE IF Statement
```
let stopLight = 'red';
	
if(stopLight === 'red') {
  console.log('Stop!');
} else if (stopLight === 'yellow') {
  console.log('Slow down.');
} else if(stopLight === 'green') {
  console.log('Go!');
} else {
  console.log('Caution, unknown!');
}
```
- Truthy and Falsy digunakan untuk mengecek apakah variabel telah terisi namun tidak mementingkan nilainya.
- Contoh Truthy and Falsy
```
let myVariable = 'Hacktiv8';
if (myVariable) {
  console.log(myVariable)
} else {
  console.log('Variable tidak ada')
}
```
- Truthy and Falsy Assignment: Analoginya adalah jika memiliki sebuah website dan meminta inputan username lalu menampilkannya. Jika usernamenya kosong bisa isi nilai tersebut.
- Contoh Truthy and Falsy Assignment
```
let defaultName;
if (username) {
  defaultName = username;
} else {
  defaultName = 'Stranger';
}
```
- Switch Case Conditional digunakan untuk jika kondisi dan percabangan terlalu banyak
- Contoh Switch Case
```
let warna = 'merah';
 
switch (warna){
  case 'hitam':
    console.log('Warna Hitam');
    break;
  case 'merah':
    console.log('Warna Merah');
    break;
  case 'Kuning':
    console.log('Warna Kuning');
    break;
  default:
    console.log('warna tidak ada');
}
```










 





  




  






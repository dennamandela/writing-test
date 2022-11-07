# Seventh Week Writing Test Back End Development
## MySQL Basic
### Apa itu Database ?
- **Database** merupakan sekumpulan tabel yang berisikan informasi untuk diolah yang kemudian data tersebut bisa digunakan di dalam sebuah sistem.
### Database Management System
- **DBMS** adalah software yang dapat digunakan oleh user untuk berkomunikasi dengan data yang ada dalam media penyimpanan.
- Tipe utama pada Database management System antara lain: 
  - Hierarchical 
  - Network 
  - Relational 
  - Non Relational
  - Object Oriented.
### Apa itu MySQL
- MySQL adalah sistem manajemen basis data relasional open source berbasis SQL. Itu dirancang dan dioptimalkan untuk aplikasi web dan dapat berjalan di platform apa pun. Sebagai persyaratan baru dan berbeda muncul dengan internet, MySQL menjadi platform pilihan untuk pengembang web dan aplikasi berbasis web.
### Kenapa Harus Belajar MySQL?
- Portabilitas
  - MySQL dapat berjalan stabil pada berbagai sistem operasi seperti Windows, Linux, MacOS dll.
- Open Source
  - Mysql didistribusikan sebagai open source sehingga dapat digunakan secara gratis.
- Multi User
  - MySQL dapat digunakan oleh beberapa pengguna dalam waktu yang bersamaan tanpa mengalami masalah / konflik.
### Instalasi MySQL
- **Install MySQL Windows**: https://dev.mysql.com/downloads/installer
  - Download software dari link diatas
  - Install software MySQL
- **Install MySQL MacOS**: https://dev.mysql.com/downloads/mysql
  - Download software dari link diatas
  - Install software MySQL 
- Atau dapat menggunakan homebrew
  - Command : ```brew install mysql```
- **Install MySQL Linux**
```
sudo apt update

sudo apt install mysql-server
```
### Data type SQL
- **Number**: Tipe data Number adalah data yang berisi kumpulan karakter angka
- **String**: Tipe data string adalah tipe data berupa kumpulan karakter termasuk karakter simbol
- **boolean**: Tipe ini hanya menyimpan 2 tipe data yaitu TRUE dan FALSE, dan dapat di convert menjadi int dengan representasi TRUE = 1, dan FALSE = 0
- **Date time**: Tipe ini merupakan tipe data untuk menyimpan tanggal dan waktu
- **Other data type**
  - DEFAULT: Tipe data untuk set default value jika tidak di assign dengan value
  - NULL: Tipe data kosong atau tipe data yang belum di assign dengan value / data
### Key
- **Primary Key**: Secara sederhana, Primary Key disebut juga dengan Kunci Primer. Kunci Primer tersebut dipilih sebagai identifikasi untuk membedakan satu baris dengan baris lainnya dalam suatu tabel. Pada dasarnya, setiap tabel hanya memiliki satu primary key saja.
```
Column data_type1 PRIMARY KEY
```
- **Foreign Key**: Secara sederhana, foreign key dapat diartikan sebagai kunci asing. Definisi tersebut juga berlaku dalam pengolahan relasional database. Kunci asing (Foreign Key) adalah sebuah atribut atau gabungan atribut yang terdapat dalam suatu tabel yang digunakan untuk menciptakan hubungan (relasi) antara dua tabel.
### SQL Command
- **Database Command**
  - ```SHOW DATABASES;``` digunakan untuk menunjukkan seluruh list database di mysql kita
  - ```CREATE DATABASES bookstore;``` digunakan untuk membuat database baru.
  - ```USE bookstore;``` digunakan untuk menggunakan database yang sudah ada.
  - ```DROP DATABASES bookstore;``` digunakan untuk menghapus / menghilangkan database yang dipilih dari MySQL kita.
- **Table Command**
  - ```SHOW TABLES;``` digunakan untuk melihat semua isi table di database.
  - 
  ``` 
  CREATE TABLE books (
    id INT (10) AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(100) NOT NULL,
    description TEXT,
    place_sell CHAR (3),
    stock INT DEFAULT(0),
    creation_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
  );
  ```
     





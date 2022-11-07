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
  - Kita membuat table baru di database tersebut dengan nama “books”. Sintaks yang dibuat menggunakan CREATE TABLE [name] dan memberikan definisi tiap kolom di table tersebut.

  ``` 
  CREATE TABLE books (
    id INT (10) AUTO_INCREMENT PRIMARY KEY,
    title VARCHAR(100) NOT NULL,
    description TEXT,
    price INT DEFAULT (0),
    stock INT DEFAULT(0),
    creation_date TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
  );
  ```
  - ```DROP TABLES books;``` digunakan untuk menghapus table yang diinginkan jika ingin dihapus.
  - Ketika ingin menambah atau menghilangkap kolom di table yang dipilih, kita bisa menggunakan ALTER dan menggunakan ADD untuk menambah kolom atau DROP COLUMN untuk menghapus kolom seperti contoh diatas.
  ```
  ALTER TABLE books
  ADD price INT,
    status ENUM ('available', 'out of stock', 'limited');
  
  ALTER TABLE books
  DROP COLUMN place_shell;
  ```
- **INSERT INTO**: Ketika ingin menambah lebih dari 1 atau multiple kita dapat menggunakan query INSERT INTO lebih dari 1 assign values
```
INSERT INTO books (id, title, description, price, stock, creation_date) VALUES (1, 'JavaScript Dasar', 'buku ini adalah bahasa pemrograman JavaScript', 150000, 50, '2022-11-07');
```
- **SELECT** 
  - ```SELECT * FROM books;``` digunakan untuk melakukan query melihat isi seluruh data di table yang dipilih
  - ```SELECT id, title``` dapat melakukan query untuk beberapa kolom yang ingin dilihat seperti query diatas, jadi kita ingin melihat id, title di table books.
  - ```SELECT id AS ID, title AS judul FROM books``` dapat menggunakan alias / AS untuk menggunakan mengubah nama kolom agar output kolomnya sesuai dengan yang kita inginkan
- **WHERE** 
  - Query WHERE digunakan untuk mencari data dengan kondisi tertentu dengan command WHERE [column_name] = condition. 
  - Kita juga dapat menggunakan WHERE lebih dari 1 parameter kondisi menggunakan IN.
- **AND, OR, NOT** 
  - Kita juga bisa mengkolaborasikan WHERE menggunakan kondisi lebih dari  1 menggunakan AND, OR dan NOT. Contoh dibawah kita menggunakan AND untuk mencari kondisi id = 1 dan title = ‘PHP’ maka kita akan memunculkan row dengan 2 kondisi tersebut.
  ``` 
  SELECT * FROM books WHERE id = 1 and title = 'PHP';
  ```
  - Kita dapat menggunakan OR untuk mencari query dengan kondisi salah satu. Contoh dibawah kita akan mencari row dengan kondisi id = 1 atau title = ‘PHP’. Maka kita akan muncul 2 row dengan salah satu kondisi yang di declare.
  ```
  SELECT * FROM books WHERE id = 1 OR title = 'PHP';
  ```
  - Dan yang terakhir kita dapat menggunakan NOT untuk mencari query yang tidak ada dalam kondisi yang di definisikan. Contoh dibawah kita mencari query yang tidak mengandung id = 1, maka muncul 3 data dengan id yang tidak sama dengan 1.
  ```
  SELECT * FROM books WHERE NOT id = 1;
  ```
- **ORDER BY**
  - Terdapat command yang bisa kita gunakan untuk melakukan ordering menggunakan ORDER BY dengan menggunakan 2 kondisi yaitu ASC dan DESC. Struktur commandnya adalah ORDER BY [column_name] ASC / DESC.
  ```
  SELECT * FROM books WHERE NOT id = 1 ORDER BY id DESC;

  SELECT * FROM books WHERE NOT id = 1 ORDER BY id ASC;
  ```
- **LIMIT** digunakan untuk membatasi berapa query yang akan dimunculkan dengan urutan dari atas. Contoh dibawah adalah query dan memunculkan hanya 2 data.
```
SELECT * FROM books LIMIT 2;
```
- **UPDATE** digunakan untuk melakukan perbaruan data di table.
```
UPDATE books
SET id=1, title='Java'
WHERE id =1
```
- **DELETE** digunakan untuk melakukan penghapusan data. Contoh dibawah kita melakukan penghapusan data di id = 1
```
DELETE FROM books 
WHERE id = 4;
```
## MySQL Lanjutan
### Tools
- Terminal
- DBeaver
### Relations di SQL
- **One to Many**
  - Paling Sering Digunakan
  - Satu baris dalam tabel dapat memiliki beberapa baris di table relasinya
  ![One To Many](/week-2-be/onetomany.jpg)



     





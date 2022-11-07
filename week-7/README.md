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
  
  ![One To Many](/week-7/onetomany.jpg)

- **Many to Many**
  - Digunakan ketika kedua tabel yang berelasi dapat memiliki beberapa baris di tabel relasinya.

  ![Many to Many](/week-7/many-to-many.png)

- **One to One**
  - Sangat jarang digunakan
  - Diimplementasikan dengan cara yang sama seperti One to Many tetapi dengan kondisi tambahan (foreign key merupakan primary key)

  ![One to One](/week-7/notasi-relasi-one-to-one.png)

### Database Normalization
- **Database Normalization**
Merupakan teknik analisis data yang mengorganisasikan atribut-atribut data dengan cara mengelompokkan sehingga terbentuk entitas yang non-redundant, stabil, dan fleksible.
- Tujuan Database Normalization
  - Menghilangkan redundan data pada database.
  - Memudahkan juka ada perubahan struktur table database.
  - Memperkecil pengaruh jika ada perubahan dari struktur table database.
- Efek jika tidak melakukan Database Normalization
  - **INSERT Anomali** : Situasi dimana tidak memungkinkan memasukkan beberapa jenis data secara langsung di database.
  - **DELETE Anomali** : Penghapusan data yang tidak sesuai dengan yang diharapkan, artinya data yang harusnya tidak terhapus mungkin ikut terhapus.
  - **UPDATE Anomali** : Situasi dimana nilai yang diubah menyebabkan inkonsistensi database, dalam artian data yang diubah tidak sesuai dengan yang diperintahkan atau yang diinginkan.
- Bentuk Database Normalization
- **First Normal Form (1NF)**
  - Menghilangkan multiple value pada sebuah kolom table database
    - Sebuah table memenuhi kaidah 1NF jika :
      - Setiap kolom bernilai tunggal (single value)
      - Setiap kolom memiliki nama yang unik
      - Urutan penyimpanan data tidak menjadi masalah
- **Second Normal Form (2NF)**
  - Harus sudah dalam bentuk 1NF untuk mendapatkan 2NF
  - Menghapus beberapa subset data yang ada pada tabel dan menempatkan mereka pada tabel terpisah.
- **Third Normal Form (3NF)**
  - Menghilangkan seluruh atribut atau field yang tidak berhubungan dengan primary key. Dengan demikian tidak ada ketergantungan transitif pada setiap kandidat key.
### Keys di SQL
- **Super Key**
  - Kumpulan dari satu atau lebih dari satu key yang dapat digunakan untuk mengidentifikasi record secara unik dalam sebuah tabel.
  - Super Key adalah superset dari Candidate Key.
- **Candidate Key** 
  - kumpulan satu atau lebih fields/columns yang dapat mengidentifikasi record secara unik dalam tabel.
  - Bisa jadi ada beberapa Candidate Keys di dalam satu tabel
  - Setiap Candidate Key bisa digunakan sebagai Primary Key.
  - Candidate Key adalah super key yang tidak mempunyai value yang berulang
- **Primary Key**
  - kumpulan satu atau lebih fields/columns dari sebuah tabel yang secara unik mengidentifikasi sebuah record dalam tabel database.
  - Valuenya tidak boleh berupa null ataupun duplicate value.
  - Hanya boleh salah satu Candidate Key yang bisa menjadi Primary Key.
- **Alternate Key**
  - key yang bisa digunakan menjadi primary key.
  - Pada dasarnya, Key ini merupakan candidate key yang tidak dijadikan primary key.
- **Unique Key**
  - Kumpulan dari satu atau lebih fields/columns di sebuah table database yang secara unik mengidentifikasi sebuah record dalam table database tersebut.
  - Hampir sama dengan Primary key, namun value dari Unique Key bisa berupa satu buah null value di dalam sebuah table database, dan Unique Key tidak bisa memiliki duplicate values
- **Foreign Key**
  - Field di sebuah table database yang menjadi Primary Key di table database lain.
  - Value dari Foreign key bisa menerima multiple null dan duplicate values.
### Join Multiple Tables
- Mengambil records dari dua atau lebih table database yang memiliki relationship dan akan di sajikan dalam single result set.
- **INNER JOIN** 
  - Semua baris akan diambil dari kedua table yang akan di JOIN, selama columns cocok dengan kondisi yang sudah di tentukan.
  - Memungkinkan baris dari salah satu tabel muncul di hasil jika dan hanya jika kedua tabel memenuhi kondisi yang ditentukan dalam klausa ON.
  ```
  SELECT column_name(s)
  FROM table1
  INNER JOIN table2
  ON table1.column_name = table2.column_name;
  ```
- **LEFT JOIN**
  - Pada JOIN ini, semua records dari table di sisi kiri JOIN statement akan di pilih.
  - Jika record yang di pilih dari table kiri tidak memiliki record yang cocok pada table JOIN yang kanan, maka record tersebut masih dipilih, dan kolom pada table yang kanan akan bernilai NULL.
  ```
  SELECT column_name(s)
  FROM table1
  LEFT JOIN table2
  ON table1.column_name = table2.column_name;
  ```
- **RIGHT JOIN**
  - Pada JOIN ini, semua records dari table di sisi kiri JOIN statement akan di pilih, bahkan jika table di sebelah kiri tidak memiliki record yang cocok.
  ```
  SELECT column_name(S)
  FROM table1
  RIGHT JOIN table2
  ON table1.column_name = table2.column_name;
  ```
- **Aggregate Functions** 
- Mengambil satu nilai setelah melakukan perhitugan pada sekumpulan nilai
- **Type of Aggregate Functions**
  - **MAX**
    - fungsi mengembalikan nilai terbesar dari kolom yang dipilih.
    ```
    SELECT MAX (column_name)
    FROM table_name
    WHERE condition;
    ```
  - **MIN**
    - fungsi mengembalikan nilai terkecil dari kolom yang dipilih.
    ```
    SELECT MIN (column_name)
    FROM table_name
    WHERE condition;
    ```
  - **SUM**
    - fungsi mengembalikan jumlah total kolom numerik.
    ```
    SELECT SUM(column_name)
    FROM table_name
    WHERE condition;
    ```
  - **COUNT**
    - fungsi mengembalikan jumlah baris yang cocok dengan kriteria yang ditentukan.
    ```
    SELECT COUNT(column_name)
    FROM table_name
    WHERE condition;
    ```
  - **AVG**
    - fungsi mengembalikan nilai rata-rata kolom numerik
    ```
    SELECT AVG(column_name)
    FROM table_name
    WHERE condition;
    ```
  - **UNION**
    - Digunakan untuk menggabungkan kumpulan hasil dari dua atau lebih pernyataan SELECT.
    - Setiap pernyataan SELECT dalam UNION harus memiliki jumlah kolom yang sama
    - Kolom juga harus memiliki tipe data yang serupa
    - Kolom dalam setiap pernyataan SELECT juga harus dalam urutan yang sama
    ```
    SELECT column_name(s) FROM table1
    UNION
    SELECT column_name(s) FROM table2;
    ```
  - **GROUP BY**
    - Mengelompokkan baris yang memiliki nilai yang sama ke dalam baris ringkasan
    - Sering digunakan dengan fungsi agregat untuk mengelompokkan kumpulan hasil dengan satu atau lebih kolom.
    ```
    SELECT column_name(s)
    FROM table_name
    WHERE condition
    GROUP BY column_name(s);
    ```
  - **HAVING**
    - HAVING ditambahkan ke SQL karena kata kunci WHERE tidak dapat digunakan dengan aggregate functions.
    ```
    SELECT column_name(s)
    FROM table_name
    WHERE condition
    GROUP BY column_name(s)
    HAVING condition
    ORDER BY column_name(s);
    ```
  - **LIKE & Wildcards**
    - Operator LIKE digunakan dalam klausa WHERE untuk mencari pola tertentu dalam kolom.
    - Karakter wildcard digunakan untuk menggantikan satu atau lebih karakter dalam sebuah string.
    ```
    SELECT column1, column2, ...
    FROM table_name
    WHERE columN LIKE pattern;
    ```
  - Wildcard Characters di SQL
    - % Mewakili nol atau lebih karakter.
    - _ Mewakili satu karakter.
## Authentication & Authorization
### Authentication
- Authentication adalah proses dimana seorang user (melalui berbagai macam akses fisik berupa komputer , melalui jaringan , atau melalui remote access ) mendapatkan hak akses kepada suatu entity (dalam hal ini jaringan suatu corporate).
![Authentication](/week-7/1_lH8l0qjavg9eMKadijsufQ.gif)
- Metode authentication yang berbasis pada kerahasiaan informasi adalah:
  - Password/PIN: Hanya pemiliknya yang tahu password/pin.
  - Digital Certificate: Berbasis pada asymmetric cryptography yang mengandung informasi rahasia yaitu private key.
  - Private Key: Hanya pemiliknya yang tahu private key, orang lain hanya tahu public key.
- Sedangkan metode authentication yang berbasis pada keunikan adalah:
  - Retina: Tidak mungkin ada 2 orang yang pola retinanya sama.
  - Fingerprint: Tidak mungkin ada 2 orang yang sidik jarinya sama.
  - Paspor: Hanya pemiliknya yang bisa menunjukkan foto di paspor sesuai dengan wajahnya.
  - Tandatangan: Hanya pemiliknya yang bisa menuliskan tandatangan dengan sempurna. 
![Auth](/week-7/1_ynx8R7wDlW9b8OE_iGA-4w.png)
### Session Based Authentication
- Pada session based authentication, server akan membuat session untuk user setelah user log in. Session id akan disimpan di dalam cookie pada browser yang digunakan user.
### Token Based Authentication
- Terdapat banyak aplikasi web menggunakan JSON Web Token (JWT) dibandingkan sessions untuk authentication. Pada aplikasi token based, server akan membuat JWT dengan rahasia dan mengirim JTW kepada client. Client kemudian menyimpan JWT (biasanya pada local storage) dan memasukan JWT kedalam headers untuk setiap request yang dilakukan oleh client.
### Authorization
- Authorization adalah proses penentuan apakah user tersebut diijinkan / ditolak untuk melakukan satu atau beberapa action atau akses terhadap resources tertentu dalam system.
- Logikanya adalah tanpa mengetahui siapa anda, saya tidak tahu apa saja yang boleh dan tidak boleh untuk anda. Jadi tanpa authentication tidak ada authorization. Biasanya pengguna yang tidak ter-otentikasi (anonymous guest) tetap bisa menikmati layanan, namun dengan akses yang sangat terbatas.
![Authorization](/week-7/1_hqDq0Y1Vcwz8Mh_wJoVcGQ.png)
## Sequelize 
### Apa itu Sequelize?
- Sequelize adalah ORM (Object Relational Mapping) Node JS yang berbasis promise. Sequelize mendukung sebagian besar relational Database seperti MySQL, PostgresQL, MariaDB, SQLite dan Miscrosoft SQL Server.
### Apa itu ORM?
- ORM adalah suatu metode/teknik pemrograman yang digunakan untuk mengkonversi data dari lingkungan bahasa pemrograman berorientasi objek (OOP) dengan lingkungan database relational.
![ORM](/week-7/orm.jpg)
### Installation Sequelize
- Install Sequelize-cli
```
npm install -g sequelize-cli
```
- Installing by NPM
```
npm install --save sequelize
```
- install Driver Database
```
npm install --save mysql
```
### Generate Sequelize
- **Sequelize init**
- Pertama kita perlu melakukan inisialisasi di project kita terlebih dahulu agar dapat melakukan generate code
```
npx sequelize-cli init
```
- **Setting Database**
```
const sequelize = require('sequelize');

// Option 1: Passing parameters separately
const sequelize = new Sequelize('database', 'username', 'password', {
  host: 'localhost',
  dialect: /* one of 'mysql' | 'postgres' */
});
```
- **Generate Model**
```
npx sequelize-cli model:generate --name Todo -- attributes title:string, description:string, startTime:date, status:string
```
- **Generate Model**
```
npx sequelize-cli db:migrate
```
- **Generate Seed**
- Seed adalah data awal yang bisa kita gunakan untuk mengisi data di database untuk keperluan awal project menggunakan sequelize
```
npx sequelize-cli seed:generate --name demo--todo
```
- Menjalankan generate seed menggunakan sequelize
```
npx sequelize-cli db:seed:all
```
- Jika ada yang salah, kita bisa mengembalikan (undo) menggunakan
```
npx sequelize-cli db:seed:undo
```
### Membuat CRUD Dengan Express dan Sequelize
- Beberapa endpoint RESTful:
  1. Get All Todos
  2. Get Todo Detail By Id
  3. Create New Todo
  4. Update Todo By Id
  5. Delete Todo
- **Get All Todo**
  - membuat sebuah routing untuk get all todo dengan syntax berikut
  ```
  const TodoModel = require('./models').Todo;

  app.get('/todos', async function (req, res) {
    try {
      const todos = await TodoModel.findAll();

      req.status(200).json(todos);
    } catch (error) {
      res.status(500).json({
        message: error.message || 'internal server error';
      });
    }
  });
  ```
- **Get Todo Detail By Id**
  - membuat sebuah routing untuk get detail todo berdasarkan Id todo dengan syntax berikut:
  ```
  const TodoModel = require('./models').Todo;

  app.get('/todos/:todoId', async function (req, res) {
    try {
      const {todoId} = req.params;
      const todo = await TodoMode.findOne({id: number(todoId)});

      req.status(200).json(todos);
    } catch (error) {
      res.status(500).json({
        message: error.message || 'internal server error',
      });
    }
  });
  ```
- **Create New Todo**
  - Membuat sebuah routing entuk create new todo dengan syntax berikut:
  ```
  const TodoModel = require('./models').Todo;

  app.get('/todos/', async function (req, res) {
    try {
      const [title, description, startTime] = req.body;

      const newTodoData = [
        title: title,
        description: description,
        startTime: startTime,
        status: 'false'.
      ];

      const newTodo = await TodoModel.create(newTodoData);

      req.status(200).json({
        message: 'new todo created',
        todo: newTodo,
      });
    } catch (error) {
      res.status(500).json({
        message: error.message || 'internal server error',
      });
    }
  });
  ```
- Update Todo By Id
```
const TodoModel = require('./models').Todo;

  app.get('/todos/', async function (req, res) {
    try {
      const {todoId} = req.params
      const [title, description, startTime, status] = req.body;

      const updateTodoData = [
        title: title,
        description: description,
        startTime: startTime,
        status: 'false'.
      ];

      const updateTodoData = await TodoModel.update(updateTodoData, {
        where : [
          id: todoId,
        ],
      });

      req.status(200).json({
        message: 'todo update succesfully',
        todo: newTodo,
      });
    } catch (error) {
      res.status(500).json({
        message: error.message || 'internal server error',
      });
    }
  });
  ```
- Delete Todo By Id
```
const TodoModel = require('./models').Todo;

  app.delete('/todos/', async function (req, res) {
    const {todoId} = req.params;
    await TodoModel.destroy([
      where: {
        id: todoId,
      };
    ]);
    res.status(200).json({
        message: 'delete todo success',
        todo: newTodo,
      });
    } catch (error) {
      res.status(500).json({
        message: error.message || 'internal server error',
      });
    }
  });
```



  





    
















     





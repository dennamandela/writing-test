# 8th Week Writing Test Back End Development
## MongoDB
### Apa itu MongoDB?
- **MongoDB** adalah salah satu database open source NoSQL yang cukup populer digunakan. MongoDB sering dipakai untuk aplikasi berbasis Cloud, Big Data maupun Grid Computing.
- Jika SQL menyimpan data menggunakan relasi tabel, MongoDB menggunakan dokumen dengan format JSON.
- **NoSQL** adalah Not Only SQL artinya bisa mengolah database dengan fleksibel dan tidak membutuhkan Query.
- Kelebihan dan Kekurangan MongoDB sebagai salah satu NoSQL:
- Kelebihan
  - Sistem tidak membutuhkan Tabel
  - Tidak perlu menggunakan Tabel yang terstruktur
  - By Default sudah menggunakan JSON(JavaScript Object Notation), sehingga memudahkan integrasi dengan JavaScript
  - Performa lebih cepat dengan kemampuan menampung banyak data yang bervariasi
- Kekurangan
  - Tidak mendukung transaksi
  - Masalah konsistensi data
  - Menggunakan banyak memory
  - Hanya bisa menampung maksimal 16MB disetiap document
- Sistem database ini menggunakan beberapa komponen penting, yaitu:

  ![Anatomi](/week-8/database-MongoDB.png)

  - **Database**: wadah untuk menyimpan berbagai macam Collection.
  - **Collection**: tempat kumpulan dari berbagai macam document, sehingga collection sering disamakan dengan tabel pada SQL.
  - **Document**: unit terkecil yang berada pada MongoDB.

## Mongoose
- **Mongoose** adalah library yang bisa digunakan sebagai Object Modelling MongoDB untuk NodeJS.
- Mongoose bisa digunakan untuk mengelola hubungan antara data, menyediakan validasi dan juga digunakan untuk menerjemahkan antara objek dalam kode dan representasi Objek tersebut di MongoDB.
- Documentation Website: https://mongoosejs.com/docs/
### Instalasi
- Pastikan NodeJS dan MongoDB juga sudah terinstall
```
npm install mongoose
```
### Create Connection
- Membuat koneksi dengan menggunakan MongoDB database, yang diletakkan di .env
```
const mongoose = require('mongoose');
require('dotenv').config()

const url = process.env.MONGODB_URL;

mongoose.connect(url, {
  useNewUrlParser: true,
  useUnifiedTopology: true,
  useDindAndModify: false});

const db = mongoose.connection;
db.on('error', console.log.bind(console, 'connection error'));
db.once('open', () => console.log('we are connected'));
```
- Kita membiasakan diri dengan menggunakan file .env untuk menyimpan URL atau data rahasia yang tidak perlu dilihat di public.
```
MONGOOSE_URL=mongodb://localhost:27017/dbmongoose
```
### Defining your Schema
```
// defining schema
const Schema = mongoose.Schema;

var userSchema = new Schema({
  name: String,
  password: String,
  email: String,
  phoneNumber: String,
}, {
  timestamps: true
});

const User = mongoose.model('users', userSchema);
```
- Lalu di potongan kode ini, kita menggunakan model users dari schema yang telah kita buat untuk melakukan pengolahan data, atau operasi CRUD.
```
const User = mongoose.model('Users', userSchema)
```
### Simple CRUD
- Sebelum membuat operasi CRUD, jangan lupa untuk menginstall express untuk routing dan body-parser, untuk menggunakan method Post dan testing API di postman.
```
npm install express
npm install body-parser
```
- Untuk menampilkan keseluruhan data (READ) kita bisa menggunakan fungsi find().
```
app.get('/users', (req, res) => {
  User.find({}, (error, users) => {
    if (error) {
      return res.send(error);
    }

    res.json(users);
  })
})
```
- Dengan kode dibawah kita akan mendapatkan data user berdasarkan id, dengan fungsi findById().
```
app.get('/users/:id', (req, res) => {
  User.findById({
    _id : req.params.id
  }, (error, users) => {
    if (error) {
      res.status(400).send({
        message: 'no data found',
      })
    } else {
      res.status(200).send({
        message: "showing data",
        result
      })
    }
  })
})
```
- Dengan kode dibawah kita akan menghapus satu data berdasarkan ID dengan menggunakan deleteOne().
```
app.delete('/users/:id', (req, res) => {
  User.deleteOne({
    _id : req.params.id
  }, (error, users) => {
    if (error) {
      res.status(400).send({
        message: 'error, no id found, cannot delete'
      })
    }else {
      res.status(200).send({
        message: 'delete success',
      })
    }
  })
});
```
### Populate
- **Populate** adalah proses penggabungan 2 collection atau lebih menjadi satu objek JSON.
## Docker
### Apa itu Docker ?
- Docker adalah software yang menjalankan suatu aplikasi menggunakan container.
- Docker men-sharing kernel dari host OS, serta meng-container-kan suatu aplikasi agar dapat dijalankan dimana saja dan kapan saja.
- Docker berfungsi sebagai penyedia layanan virtual bagi aplikasi yg diinstall pada sebuah host. Docker akan menyediakan hal-hal yang diperlukan untuk aplikasi mulai dari akses file, koneksi internet, hingga port agar aplikasi dapat berjalan dengan mulus
### Container vs Virtual Machine

![Container vs Virtual Machine](/week-8/img/containers-vs-virtual-machines.jpg)

- VM memakan banyak resource dan waktu utk booting karena melakukan virtualisasi pada host hardware-nya. Sedangkan container kebalikannya dari vm, container melakukan virtualisasi pada host OS-nya.
### Docker Fundamental

![Docker](/week-8/img/1_zfeWRiR39GiGKh_OZKJEgg.png)

- Docker File: Blueprint untuk membuat image
- Image: Template untuk menjalankan container
- Container: Perwujudan dari Image
- Docker Registry: Tempat untuk upload/download image

### Instalasi Docker
- https://docs.docker.com/get-docker/

### Perintah Dasar
- docker pull: Download image dari docker hub
- docker images: Melihat kumpulan images yang sudah terdownload
- docker run: Menjalankan container
- docker ps: Melihat container yang berjalan
### Docker File
- Merupakan sebuah blueprint untuk membuat image, kamu juga bisa membuat custom image menggunakan docker file.
- Caranya:
  - Buat file Dockerfile di dalam project yang kamu buat
  - Tulis beberapa perintah ke dalam dockerfile
  - Jalankan docker file menggunakan perintah 
    - docker build -t NAMA_IMAGES:TAG . 
    - docker build -t my-app:1.0 
### Docker Compose
- Cara untuk menjalankan lebih dari 1 container secara bersamaan dan saling terhubung.
- Caranya:
  - Buat file NAMA_FILE.yaml di dalam project yang kamu buat
  - Tulis beberapa perintah ke dalam sana
  - Jalankan menggunakan perintah 
    - docker-compose NAMA_FILE.yaml up












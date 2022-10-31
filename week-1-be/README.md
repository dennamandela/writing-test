# First Week Writing Test Back End Development
## Web Server & RESTful API
### Apa itu web server
- Web Server terdiri dari 2 komponen penting:
  - Hardware 
  - Software
- **Hardware**, Di sisi perangkat keras, web server adalah komputer yang menyimpan perangkat lunak server web dan file komponen situs web. (misalnya, dokumen HTML, gambar, CSS stylesheet, dan file JavaScript) Server web terhubung ke Internet dan mendukung pertukaran data fisik dengan perangkat lain yang terhubung ke web.
- **Software**, Di sisi perangkat lunak, server web mencakup beberapa bagian yang mengontrol bagaimana pengguna web mengakses file yang dihosting. ini adalah server HTTP. Server HTTP adalah perangkat lunak yang memahami URL (alamat web) dan HTTP (protokol yang digunakan browser Anda untuk melihat halaman web). Server HTTP dapat diakses melalui nama domain situs web yang disimpannya, dan mengirimkan konten situs web yang dihosting ini ke perangkat pengguna akhir.
### Static Web Server VS Dynamic Web Server
- **Static Web Server** atau tumpukan, terdiri dari komputer (perangkat keras) dengan server HTTP (perangkat lunak). Kami menyebutnya "statis" karena server mengirimkan file yang dihosting apa adanya ke browser.
- **Dynamic Web Server**, Sebuah server web dinamis terdiri dari server web statis ditambah perangkat lunak tambahan, paling sering server aplikasi dan database. Kami menyebutnya "dinamis" karena server aplikasi memperbarui file yang dihosting sebelum mengirim konten ke browser melalui server HTTP.
### Server Side Programming
- Web Server menunggu pesan permintaan klien, memprosesnya saat tiba, dan membalas browser web dengan pesan respons HTTP. Respons berisi baris status yang menunjukkan apakah permintaan berhasil atau tidak (mis. "HTTP/1.1 200 OK" untuk berhasil).
  - **Static Sites**: situs yang mengembalikan konten hard-coded yang sama dari server setiap kali sumber daya tertentu diminta). Saat pengguna ingin menavigasi ke halaman, browser mengirimkan permintaan "GET" HTTP yang menentukan URL-nya.
  - **Dynamic Site**: situs di mana beberapa konten respons dihasilkan secara dinamis, hanya bila diperlukan. Di situs web dinamis, halaman HTML biasanya dibuat dengan memasukkan data dari database ke dalam placeholder di template HTML (ini adalah cara yang jauh lebih efisien untuk menyimpan konten dalam jumlah besar daripada menggunakan situs web statis).
### what is REST
- REST, atau Representational State Transfer, adalah gaya arsitektur untuk menyediakan standar antara sistem komputer di web, sehingga memudahkan sistem untuk berkomunikasi satu sama lain.
- Dalam gaya arsitektur REST, implementasi klien dan implementasi server dapat dilakukan secara independen tanpa saling mengetahui satu sama lain.
### Komunikasi antara Klien dan Server 
- **Making Requests**
- REST mengharuskan klien membuat permintaan ke server untuk mengambil atau mengubah data di server. Permintaan umumnya terdiri dari:
  - kata kerja HTTP, yang mendefinisikan jenis operasi apa yang harus dilakukan
  - header, yang memungkinkan klien untuk menyampaikan informasi tentang request
  - jalan menuju resource
  - message body opsional yang berisi data
- **HTTP VERBS**
- Ada 4 kata kerja HTTP dasar yang kami gunakan dalam permintaan untuk berinteraksi dengan sumber daya dalam sistem REST:
  - GET — mengambil sumber daya tertentu (berdasarkan id) atau kumpulan sumber daya
  - POST — buat sumber daya baru
  - PUT — perbarui sumber daya tertentu (berdasarkan id)
  - DELETE — menghapus sumber daya tertentu dengan id
### Headers and Accept Parameters
- Di header permintaan, klien mengirimkan jenis konten yang dapat diterimanya dari server.
- Tipe lain dan subtipe yang umum digunakan:
  - gambar — gambar/png, gambar/jpeg, gambar/gif
  - audio — audio/wav, audio/mpeg
  - video — video/mp4, video/ogg
  - aplikasi — aplikasi/json, aplikasi/pdf, aplikasi/xml, aplikasi/octet-stream
### Sending Responses
- **Content Types**
- Misalnya, ketika klien mengakses sumber daya dengan id 23 di sumber artikel dengan Permintaan GET ini:
  - GET/articles/23 HTTP/1.1
  - Accept: text/html, application/xhtml
- Server mungkin mengirim kembali konten dengan header respons:
  - HTTP/1.1 200 (OK)
  - Content-Type: text/html
- **Response Codes**
- HTTP status code adalah kode respons standar yang diberikan oleh server website di internet. Kode ini membantu mengidentifikasi penyebab masalah saat laman website atau sumber daya lain tidak dimuat dengan benar.
- Contoh:
  - 200 (OK): Ini adalah respons standar untuk permintaan HTTP yang berhasil.
  - 201 (CREATED): Ini adalah respons standar untuk permintaan HTTP yang menghasilkan item yang berhasil dibuat.
  - 204 (NO CONTENT): Ini adalah respons standar untuk permintaan HTTP yang berhasil, di mana tidak ada yang dikembalikan di badan respons.
  - 400 (BAD REQUEST): Permintaan tidak dapat diproses karena sintaks permintaan yang buruk, ukuran yang berlebihan, atau kesalahan klien lainnya.
  - 403 (FORBIDDEN): Klien tidak memiliki izin untuk mengakses sumber daya ini.
  - 404 (NOT FOUND): Sumber daya tidak dapat ditemukan saat ini. Mungkin sudah dihapus, atau belum ada.
  - 500 (Internal Server Error): HTTP status code ini adalah kode yang dikirimkan ketika server mengalami situasi yang tidak diketahui cara menanganinya.
## Intro & Essential Node JS
- Tools
  - Visual Studio Code (code editor)
  - Browser latest version (Chrome, mozilla, opera, dll).
  - Command Line Interface (mac / linux : terminal, windows : cmd)
  - Node JS
### Apa itu Node JS?
- Node.js adalah runtime development untuk JavaScript yang bersifat open-source dan cross-platform. Node.js menjalankan V8 JavaScript engine (yang juga merupakan inti dari Google Chrome) diluar browser.
### Node JS Architecture
- **Single Thread**, Javascript menggunakan konsep single thread, yang berarti hanya memiliki satu tumpukan panggilan yang digunakan untuk menjalankan program.
- **Event Loop** akan memfasilitasi kondisi ini, event loop akan memeriksa terus menerus, ketika antrian kosong di call stack maka akan menambah antrian baru dari event queue sampai semua perintah selesai di eksekusi.
- **Server side scripting**, dengan menggunakan NodeJS dapat menjalankan javascript di server side menggunakan terminal command line menggunakan perintah “node”.
### JavaScript For Node JS
- Sebelum masuk lebih dalam ke Node JS, terdapat beberapa materi yang perlu direview dan di pahami lagi dari bahasa pemorgraman javascript agar mempermudah memahami Node JS yaitu :
  - Arrow function expression
  - Asynchronous
  - JSON
### Instalasi Node JS
- Install Node JS
- link : https://nodejs.org/en/
- Untuk mengetes apakah berhasil terinstall, dapat menjalankan “node -v” untuk mengecek versi NodeJS yang terinstal.
- Running Node JS
- Kita dapat menggunakan node di terminal kita dengan mengetik “node” kemudian bisa membuat code javascript dan langsung dieksekusi.
### Node JS for Back end Development
- Build In Module Node JS
- **Console** merupakan module bawaan dari javascript yang ada di node JS untuk digunakan sebagai debug atau menampilkan code secara interface.
```
console.log("Hello World!")
```
- **Process** adalah modules yang digunakan untuk menampilkan dan mengontrol prosess Node JS yang sedang dijalankan.
```
const process = require('process');
const env = process.env;

env.foo = 'bar';
console.log(env.foo);
```
- **OS** module merupakan module yang digunakan untuk menyediakan informasi terkait sistem operasi komputer yang digunakan user.
```
const os = require('os');
console.log("Platform: " + os.platform());
console.log("Architecture: " + os.arch());
```
- **Util** Module Util merupakan alat bantu / utilities untuk mendukung kebutuhan internal API di Node JS.
```
const util = require('util);
const debuglog = util.debuglog('foo');

debuglog('hello from foo [%d]', 123);
```
- **Events**
```
const EventEMitter = require('events');

class MyEmitter extends EventEmitter {}

const myEmitter = new MyEmitter();
myEmitter.on('events', () => {
    console.log('an event occurred!');
});
myEmitter.emit('event');
```
- **Errors** merupakan modules yang dapat digunakan untuk mendefinisikan error di Node JS sehingga lebih informatif.
```
try {
    const m = 1;
    const n = m + z;
} catch (err) {
    // Handle the error here.
}
```
- **Buffer** merupakan modules yang digunakan untuk mengakses, mengelola dan mengubah tipe data raw atau tipe data bytes.
```
import { Buffer } from 'buffer';

const buf = Buffer.from('hello world', 'utf8');

console.log(buf.toString('hex'));

console.log(buf.toString('base64'));
```
- **FS** atau “file system” merupakan module yang dapat membantu berinteraksi dengan file yang ada diluar code. FS paling sering digunakan untuk membaca file dengan ekstensi .txt, .csv, dan .json
```
import { readFileSync } from 'fs';

readFileSync('<directory>');

readFileSync('<directory>');
```
- **Timers** merupakan modules yang digunakan untuk melakukan scheduling atau mengatur waktu pemanggilan fungsi yang dapat diatur di waktu tertentu.
```
import {
    setTimeout,
} from 'timers/promises';

const res = await setTimeout(100, 'result');

console.log(res);
```
### Membuat Web Server Dengan Node JS
- **Node JS Web Server**
- Node.js memiliki built-in modul yang disebut HTTP, built-in modul ini memungkinkan Node JS mentransfer data melalui Hyper Text Transfer Protocol (HTTP).
  - Untuk menggunakan modul HTTP, gunakan require()
  - Gunakan method createServer() untuk membuat server HTTP
  - Callback function yang digunakan pada method http.createServer(), akan dijalankan ketika seseorang mencoba mengakses komputer pada port 8080.
```
const http = require('http');

//create a server object:
http.createServer(function (req, res) {
    res.write('Hello World!');
    res.end();
}).listen(8080);
```
- Menambahkan HTTP Header
  - Bisa menggunakan method res.writeHead() untuk menambahkan header HTTP.
  - Argumen pertama dari method res.writeHead() adalah status code, 200 berarti semuanya OK
  - Argumen kedua adalah objek yang berisi header respons.
  - Contoh : Jika respons dari server HTTP seharusnya ditampilkan sebagai HTML, maka kita harus menambahkan header HTTP dengan tipe konten yang benar.
```
const http = require('http');

//create a server object:
http.createServer(function (req, res) {
    res.writeHead(200, {'Content-Type': 'text/html'});
    res.write('Hello World!');
    res.end();
}).listen(8080);
```
- Respons yang dikembalikan dari HTTP web server bisa dalam berbagai format.
- Contohnya, Bisa mengembalikan response dalam format JSON dan HTML, namun juga dapat mengembalikan format teks lain seperti XML dan CSV.
- Selain itu web server dapat mengembalikan data non-teks seperti PDF, file zip, audio, dan video.
- Format ini harus ditambahkan kedalam HTTP Header.
- Membaca Query String
  - Callback function pada method http.createServer() memiliki argumen req yang mewakili request dari klien, sebagai objek (objek http.IncomingMessage).
  - Objek ini memiliki sebuah properti yang disebut "url" yang menyimpan informasi url yang sedang mengakses.
```
const http = require('http');

//create a server object:
http.createServer(function (req, res) {
    res.writeHead(200, {'Content-Type': 'text/html'});
    res.write('Hello World!');
    res.end();
}).listen(8080);
```
- Split Query String
  - Ada build-in module yang bisa kita gunakan untuk split query string menjadi beberapa bagian yang dapat dibaca.
  - Build-in modulenya adalah URL Module.
```
const http = require('http');
const url = require('url');

http.createServer(function (req, res) {
    res.writeHead(200, {'Content-Type': 'text/html'});
    const query = url.parse(req.url, true).query;
    const txt = q.year + " " + q.month;
    res.end(txt);
}).listen(8080);
```
## Express JS
### Apa itu Express JS ?
- Express.js, atau hanya express, adalah kerangka aplikasi web back end untuk Node.js, dirilis sebagai perangkat lunak sumber terbuka dan gratis di bawah lisensi MIT. Ini dirancang untuk membangun aplikasi web dan API. Ini telah disebut sebagai kerangka kerja server standar de facto untuk Node.js.
### Apa itu Back End Web Application?
- Back end app adalah aplikasi yang berjalan di server-side yang bekerja untuk memberikan informasi berupa data sesuai request dari client / browser / front end app.
- Kelebihan dari framework ini terletak pada fitur caching, support dengan Google V8 Engine, JavaScript, serta didukung oleh komunitas dan skalabilitas aplikasi yang baik.
### Apa itu REST API?
- **RESTful API / REST API** merupakan penerapan dari **API (Application Programming Interface)**.
- Sedangkan **REST (Representional State Transfer)** adalah sebuah arsitektur metode komunikasi yang menggunakan protokol HTTP untuk pertukaran data dimana metode ini sering diterapkan dalam pengembangan aplikasi.
- RESTFUL API memiliki 4 komponen penting yaitu:
  - URL Design
  - HTTP Verbs
  - HTTP Response Code
  - Format Response
### Installation and Preparation
- **Install express JS**
- Karena expressJS adalah sebuat modules atau package yang dikembangkan menggunakan bahasa javascript, maka kita bisa menggunakan NPM untuk menginstall express JS
```
npm install express --save
```
- **Preparation**
- Terdapat beberapa module yang perlu diinstal untuk mempermudah develop server side application, seperti nodemon (agar dapat restart application otomatis selama proses development)
```
npm install --save-dev nodemon
```
- **Basic Syntax expressJS**
```
const express = require('express');
const app = express();
const port = 3000

app.get('/', (req res) => {
  res.send('Hello World!')
})

app.listen(port, () => {
  console.log('Example app listening at http://localhost:${port}')
})
```
### Basic Routes
- **Routes** adalah sebuah end point yang diapat kita akses menggunakan URL di website. Didalam routes kita perlu menentukan method API, alamat dan response apa saja yang akan dikeluarkan
```
app.get('/', (req res) => {
  res.send('Hello World!');
}) 
```
- Kita bisa menjalankan aplikasi sederhana kita dengan cara menggunakan “node”. Dan aplikasi kita akan berjalan di alamat ‘http://localhost:3000’
- Kemudian kita dapat mengaksesnya di website dan menambah route yang akan kita akses yaitu “/”
```
node app.js
```
- **method**, Kita dapat menggunakan method yang dalam REST API seperti **POST, PUT, PATCH** dan **DELETE**
```
app.post('/add', (req res) => {
  res.send('Data berhasil ditambahkan')
})

app.delete('/delete', (req res) => {
  res.send('Data berhasil dihapus')
})
```
- **Response** Di dalam route kita dapat mengirim response menggunakan parameter dari route express.js yaitu “res.Send()” untuk mengirim plain text ketika kita mengakses route tersebut.
```
app.get('/hello', (req res) => {
  res.json({
    name : "Mandela",
    umur : 21,
    alamat : "bandung",
  })
})
```
- Kita dapat mengirim response berupa output json yang biasa dipakai untuk back end application. Dengan menggunakan output json maka kita dapat mengirim data yang mudah diakses.
- **Status Code**
- Dalam pengaplikasian back end application, kita sangat perlu memberikan status code sebagai informasi apakah route yang kita akses berjalan sebagaimana mestinya dan tidak terjadi error.
```
app.get('/hello', (req res) => {
  res.status(200).json({
    name : "Mandela",
    umur : 21,
    alamat : "bandung",
  })
})
```
- **Query** merupakan parameter yang digunakan untuk membantu menentukan tindakan yang lebih spesifik daripada hanya sekedar router biasa. Biasanya query ditaruh di akhir route dengan memberikan informasi diawali dengan “?” kemudian tedapat key dan data yang dapat ditindak lanjuti. Ex : “?q=hello&age=23”
```
app.get('/hello', (req res) => {

  let name = req.query.name
  let umur = req.query.umur

  res.status(200).json({
    name : "Mandela",
    umur : 21,
    alamat : "bandung",
  })
})
```
- **Nested route** digunakan ketika terdapat banyak route yang memiliki nama yang sama atau ingin membuat route yang lebih mendalam.
```
app.use("/hello", hello)

const hello = require('express').Router();

hello.get('/denna', (req, res) => {
  res.send("hello saya adalah denna")
})

hello.get('/abil', (req, res) => {
  res.send("hello saya adalah abil")
})

hello.get('/rodhi', (req, res) => {
  res.send("hello saya adalah rodhi")
})
```
### Express Middleware
- **Apa itu Middleware ?**
- **Middleware function** adalah sebuah fungsi yang memiliki akses ke **object request (req)**, **object response (res)**, dan sebuah **fungsi next** didalam request-response cycle.
- Fungsi next biasanya di berikan nama variable next.
- Apa Saja yang Bisa dilakukan oleh Function Middleware?
- Pada Dasarnya, sebuah middleware function dapat melakukan tugas-tugas berikut:
  - Menjalankan kode apapun.
  - Memodifikasi Object Request dan Object Response.
  - Menghentikan request-response cycle.
  - Melanjutkan ke middleware function selanjutnya atau ke handler function dalam suatu request response cycle.
- **Kemampuan Fungsi Middleware : Menjalankan Kode Apapun**
  - Sebuah function middleware bisa digunakan untuk mengeksekusi kode apapun untuk suatu tujuan tertentu.
  - Sebagai contoh, kita akan membuat sebuah middleware function yang akan mencetak tulisan “Halo Skilvul, request diterima!” Ketika sebuah HTTP Request masuk kedalam middleware function ini. 
  - Middleware Function ini akan diberi nama dengan skilvulLogger.

  ```
  const express = require('express')
  const app = express()

  const skilvulLogger = function (req, res, next) {
    console.log('Halo Semua, request diterima')
    next()
  }

  app.use(skilvulLogger)

  app.get('/', function (req, res) {
    res.send('Hello Semua')
  })

  app.listen(3000)
  ```
- **Kemampuan Fungsi Middleware : Memodifikasi Object Request dan Object Response.**
  - Sebuah function middleware bisa digunakan untuk memodifikasi Object Request dan Object Response.
  - Sebagai contoh, kita akan membuat sebuah middleware function yang akan menambahkan informasi request time pada object request.
  - Middleware Function ini akan diberi nama dengan addRequestTime.

  ```
  const express = require('express')
  const app = express()

  const addRequestTime = function (req, res, next) {
    req.requestTime = Date.now()
    next()
  }

  app.use(addRequestTime)

  app.get('/', function (req, res) {
    let responseText = 'Hello Semua!'
    responseText += '<small>Requested at: ' + req.requestTime + '</small>'
    res.send(responseText)
  })

  app.listen(3000)
  ```

- **Kemampuan Fungsi Middleware : Menghentikan Request-Response Cycle.**
  - Sebuah function middleware bisa digunakan untuk menghentikan request-response cycle.
  - Sebagai contoh, kita akan membuat sebuah middleware function yang akan menghentikan request-response cycle.
  - Middleware Function ini akan diberi nama dengan stopHere.
  - Request tidak akan pernah sampai ke handler function, karena middleware
telah menghentikan request-response cycle dengan res.send() dan tidak memanggil next()
  
  ```
  const stopHere = function(req, res, next) {
    res.send('<p>request stop from middleware</p>')
  }
  ```

- Jenis Express Middleware Berdasarkan Cara Penggunaan
- Express Middleware dapat dikelompokkan berdasarkan dari dimana middleware function itu digunakan :
  - Application Level Middleware
  - Router Level Middleware
  - Error Handling Middleware

- Application Level Middleware
  - Application Level Middleware adalah sebuh function middleware yang melekat ke instance object Application Express.
  - Penggunaannya dengan cara memanggil method app.use().
  - Application Level Middleware akan di jalankan setiap kali Express Application menerima sebuah HTTP Request.

  ```
  const addRequestTime = function(req, res, next) {
    req.requestTime = Date.now()
    next()
  }

  app.use(addRequestTime)
  ```

- Router Level Middleware
  - Router Level Middleware adalah sebuh function middleware yang cara kerjanya sama persis dengan application level middleware, yang menjadikan perbedaan adalah middleware function ini melekat ke instance object Router Express.
  - Penggunaannya dengan cara memanggil method express.Router().
  - Router Level Middleware hanya akan di jalankan setiap kali sebuah Express Router yang menggunakan middleware ini menerima sebuah HTTP Request, sedangan pada Router yang lain tidak akan dijalankan.

  ```
  const express = require('express')
  const UserRouter = express.Router()
  const Adminrouter = express.Router()

  const logUserAction = function (req, res, next) {
    const username = req.body.username

    console.log(`username ${username} access the API`)

    next()
  }

  UserRouter.use(logUserAction)

  UserRouter.get('/users', function (req, res) {
    res.send('all user data!')
  })

  AdminRouter.get('/admins', function(req, res) {
    res.send(`all admin data!`)
  })

  ```

- Error Handling Middleware
  - Error Handling mengacu kepada bagaimana cara sebuah Express Application menangkap dan memproses error yang terjadi, baik itu berupa kesalahan yang synchronous maupun asynchronous.
  - Express Application sudah menyediakan error handle function default, sehingga kita tidak perlu lagi membuat sendiri functionnya.
  - Error handle function default milik Express Application hanyalah kerangka functionnya saja, kita tetap harus menuliskan di dalam function ini bagaimana sebuah error akan di handle.
  - Error Handling Middleware digunakan pada Application Level Middleware

  ```
  const express = require('express')
  const app = express()

  const errorHandling = function(req, res, next) {
    console.error(err.stack)
    res.status(500).send('Something broke!')
  }

  app.use(errorHandling)
  ```

- **Jenis Express Middleware Berdasarkan Source Middleware Function**
- Express Middleware dapat juga dikelompokkan berdasarkan dari dimana middleware function itu didapatkan :
  - Express Build-in Middleware
  - Third Party(custom) Middleware
- **Jenis Express Middleware Berdasarkan Source Middleware Function : Express Build-in Middleware**
- Express JS sudah menyediakan 3 buah build-in middleware function yang bisa digunakan :
  - express.static()
  - express.json()
  - express.urlEncoded()
- **express.static()**
  - Adalah salah satu build-in middleware function yang disediakan oleh Express JS.
  - Middleware function ini memungkinkan sebuah express application melayani asset statis berupa file, seperti file HTML, gambar, video, dokumen, dan sebagainya.
  - Dokumentasi lengkap : 

  ```
  const options = {
    dotfiles: 'ignore',
    etag: false,
    extensions: ['htm', 'html'],
    index: false,
    maxAge: 'Id',
    redirect: false,
    setHeaders: function (res, path, stat) {
      res.set('x-timestamp', Date.now())
    }
  }

  app.use(express.static('public'), options)
  ```

- **express.json()**
  - Adalah salah satu build-in middleware function yang disediakan oleh Express JS.
  - Middleware function ini memungkinkan sebuah express application menerima HTTP Request yang membawa payload (data) dalam format JSON.
  - Middleware function ini tersedia di Express JS versi 4.16.0+

  ```
  const express = require('express')
  const app = express ()

  app.use(res.json())
  ```

- **express.urlEncoded()**
  - Adalah salah satu build-in middleware function yang disediakan oleh Express JS.
  - Middleware function ini memungkinkan sebuah express application menerima HTTP Request yang membawa payload (data) dalam format urlencoded.
  - Middleware function ini tersedia di Express JS versi 4.16.0+

  ```
  const express = require('express')
  const app = express()

  app.use(res.urlEncoded())
  ```
- Express Third Party (custom) Middleware
- Membuat custom middleware function atau menggunakan third party middleware function dapat menambahkan fungsionalitas dari sebuah Express Application.
- Berikut adalah contoh third party middleware yang dikelola oleh Express JS Team :
  - cors
  - body-parser
  - errorhandling
  - morgan
  - Multer

## Design Database
### Apa itu Database
- Database atau Basis Data adalah kumpulan data yang saling sinkron (tanpa redundancy) yang disimpan secara bersama-sama yang dapat diakses secara elektronik dari suatu sistem.
### Apa itu RDBMS
- RDBMS atau Relational Database Management System adalah sebuah system yang dirancang khusus untuk management database agar tersusun dan terintegrasi.
- karena system inilah yang memungkinkan user mengelola database, mulai dari membuat database, membaca isi database, mengubah isi database dan menghapus isi database atau CRUD
  - Create
  - Read
  - Update
  - Delete
### Jenis-jenis Database
- Terdapat beberapa jenis database yang populer dan banyak dipakai diantaranya adalah:
  - Oracle
  - MySQL
  - Microsoft SQL Server
  - PostgreSQL
  - MongoDB
  - ElasticSearch
  - Redis
  - SQLite
### Relasi antar tabel 

- Relasi adalah istilah dalam relational database (tabel) yang mengacu ke bagaimana tabel dalam database itu bisa saling terkait. dalam pembuatan relasi database itu dihubungkan dengan Foreign Key pada kolom tabel A dan Primary Key pada kolom tabel B.
- Istilah-istilah relasi antar tabel
  - Primary Key
  - Foreign Key
- **Primary Key** merupakan kunci utama pada field tertentu dalam sebuah tabel yang biasa digunakan untuk mendefinisikan rows data tertentu.
- **Foreign Key** adalah atribut pada tabel yang menunjukan hubungan (relasi) ke tabel induk ( yang mempunyai primary key).
### Jenis-jenis Relasi Antar Tabel di Database
- terdapat pembagian jenis relasi database diantaranya
  - One To One Field
  - One To Many
  - Many To Many 
- **One to One Field** merupakan relasi dari saru baris tabel A ke sau baris ke tabel B
- **One to Many** adalah relasi dimana satu baris tabel (tabel A) dihubungkan ke satu baris atau lebih (Tabel B).
- **Many To Many** adalah relasi yang dimana lebih dari satu baris (tabel A) dihubungkan di lebih dari satu baris (tabel B).
## Normalisasi Basis Data
### Apa itu Normalisasi Database?
- **Normalisasi** merupakan sebuah teknik logical desain dalam sebuah basis data yang mengelompokkan atribut dari berbagai entitas dalam suatu relasi sehingga membentuk struktur relasi yang baik (tanpa redudansi/pengulangan data) serta sebagian besar ambiguity bisa dihilangkan.
### Tujuan Normalisasi Database
- Jika data dalam database tersebut belum di normalisasi maka akan terjadi 3 kemungkinan yang akan merugikan sistem secara keseluruhan.
  - **Insert Anomali**: Situasi dimana tidak memungkinkan memasukkan beberapa jenis data secara langsung di database.
  - **Delete Anomali**: Penghapusan data yang tidak sesuai dengan yang diharapkan, artinya data yang harusnya tidak terhapus mungkin ikut terhapus.
  - **Update Anomali**: Situasi dimana nilai yang diubah menyebabkan inkonsistensi database, dalam artian data yang diubah tidak sesuai dengan yang diperintahkan atau yang diinginkan.
### Database Seperti Apa yang dinormalisasi?
- Tidak semua database bisa dinormalisasi, hanya tipe “relational database“ yang bisa dinormalisasi. Banyak vendor DBMS (Database Management System) diantaranya Oracle, MySQL, SQL Server, PostgreSQL, dll.
### Tahapan Normalisasi Database
- Untuk melakukan normalisasi database kita harus mengidentifikasi data seperti apa yang akan disimpan, dan berikut adalah contohnya:
- **Bentuk Tidak Normal (Unnormalize)**: Bentuk tidak normal (unnormalized) merupakan kumpulan data yang direkam tidak ada keharusan dengan mengikuti suatu format tertentu.
- **1NF / First Normal Form**: 1NF mensyaratkan beberapa kondisi dalam sebuah database, berikut adalah fungsi dari bentuk normal pertama ini.
  - Menghilangkan duplikasi kolom dari tabel yang sama.
  - Buat tabel terpisah untuk masing-masing kelompok data terkait dan mengidentifikasi setiap baris dengan kolom yang unik (primary key).
- **2NF**: Syarat untuk menerapkan normalisasi bentuk kedua ini adalah data telah dibentuk dalam 1NF, berikut adalah beberapa fungsi normalisasi 2NF.
  - Menghapus beberapa subset data yang ada pada tabel dan menempatkan mereka pada tabel terpisah.
  - Menciptakan hubungan antara tabel baru dan tabel lama dengan menciptakan foreign key.
  - Tidak ada atribut dalam tabel yang secara fungsional bergantung pada candidate key tabel tersebut.
- **3NF**: Pada 3NF tidak diperkenankan adanya partial “transitive dependency“ dalam sebuah tabel. Transitive dependency biasanya terjadi pada tabel hasil relasi, atau kondisi dimana terdapat tiga atribut A, B, C. Kondisinya adalah A ⇒ B dan B ⇒ C. Maka C dikatakan sebagai transitive dependency terhadap A melalui B.
- **BCNF Boyce-Codd normal form** Merupakan sebuah teknik normalisasi database yang sering disebut 3.5NF, memiliki hubungan yang sangat erat dengan bentuk 3NF. Pada dasarnya adalah untuk menghandle anomali dan overlooping yang tidak dapat di handle dalam bentuk 3NF.
- Untuk tabel untuk memenuhi Bentuk Normal Boyce-Codd, harus memenuhi dua kondisi berikut:
  - yaitu Table harus dalam Bentuk Normal Ketiga.
  - Dan, untuk ketergantungan apa pun A → B, A harus menjadi super key.
### Pentingnya Normalisasi
- Suatu rancangan database disebut buruk jika :
  - Data yang sama tersimpan di beberapa tempat (file atau record).
  - Ketidakmampuan untuk menghasilkan informasi tertentu.
  - Terjadi kehilangan informasi.
  - Terjadi adanya redudansi (pengulangan) atau duplikasi data sehingga memboroskan ruang penyimpanan dan menyulitkan saat proses updating data.
  - Timbul adanya NULL VALUE..
  - Kehilangan informasi bisa terjadi bila pada waktu merancang database (melakukan proses dekomposisi yang keliru).
  - Bentuk normalisasi yang sering digunakan adalah 1st NF, 2nd NF, 3rd NF,dan BCNF.
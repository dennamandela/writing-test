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
- Web Server 

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
- Kemampuan Fungsi Middleware : Menjalankan Kode Apapun
  - Sebuah function middleware bisa digunakan untuk mengeksekusi kode apapun untuk suatu tujuan tertentu.
  - Sebagai contoh, kita akan membuat sebuah middleware function yang akan mencetak tulisan “Halo Skilvul, request diterima!” Ketika sebuah HTTP Request masuk kedalam middleware function ini. 
  - Middleware Function ini akan diberi nama dengan skilvulLogger.

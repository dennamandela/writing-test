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
- Apa itu Node JS?
- Node.js adalah runtime development untuk JavaScript yang bersifat open-source dan cross-platform. Node.js menjalankan V8 JavaScript engine (yang juga merupakan inti dari Google Chrome) diluar browser.
- Node JS Architecture
  - **Single Thread**, Javascript menggunakan konsep single thread, yang berarti hanya memiliki satu tumpukan panggilan yang digunakan untuk menjalankan program.
  - **Event Loop** akan memfasilitasi kondisi ini, event loop akan memeriksa terus menerus, ketika antrian kosong di call stack maka akan menambah antrian baru dari event queue sampai semua perintah selesai di eksekusi.
  - **Server side scripting**, dengan menggunakan NodeJS dapat menjalankan javascript di server side menggunakan terminal command line menggunakan perintah “node”.
- JavaScript For Node JS
- Sebelum masuk lebih dalam ke Node JS, terdapat beberapa materi yang perlu direview dan di pahami lagi dari bahasa pemorgraman javascript agar mempermudah memahami Node JS yaitu :
  - Arrow function expression
  - Asynchronous
  - JSON
- Install Node JS
- link : https://nodejs.org/en/
- Untuk mengetes apakah berhasil terinstall, dapat menjalankan “node -v” untuk mengecek versi NodeJS yang terinstal.
- Running Node JS
- Kita dapat menggunakan node di terminal kita dengan mengetik “node” kemudian bisa membuat code javascript dan langsung dieksekusi.
- Node JS for Back end Development
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
- Membuat Web Server Dengan Node JS
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


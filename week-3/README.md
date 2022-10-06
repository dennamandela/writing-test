# Third Week Writing and Presentation Test
## JavaScript Intermediate
### Array
- **Array** adalah tipe data **list order** yang dapat menyimpan tipe data apapun di dalamnya. Array dapat menyimpan tipe data String, Number, Boolean, dan lainnya.
- Contoh Array
```
let toDoList = [
    'Belajar javascript',
    'Mencuci Baju',
    'Latihan membuat aplikasi javascript'
];
console.log(toDoList);
```
- Membuat Array: Array didefinisikan menggunakan square brackets ```[]```
- Mengakses Array: Array pada javascript dihitung dari index data ke-0.
```
let productTeam = ['Product Manager', 'Machine Learning Engineer', 'Back End Developer'];
console.log(productTeam);
```
- **Update Array**
```
let productTeam = ['Product Manager', 'Machine Learning Engineer', 'Back End Developer'];

productTeam['0'] = 'Front End Developer';
console.log(productTeam);
```
- **Const Array**
  - Const tidak bisa melakukan update data. Namun pada Array kita dapat melakukan update konten nilai di dalam array (mutable).
  - Yang tidak bisa adalah mengubah array dengan array yang baru jika menggunakan const.
- Contoh Const Array
```
const cars = ['tesla', 'mazda', 'toyota'];
cars[2] = 'ferrari';
console.log(cars);
```
- Array memiliki 5 properti yang sering digunakan yaitu:
  - constructor
  - length
  - index
  - input
  - prototype
- **Array Properties** adalah fitur yang sudah disediakan oleh Javascript untuk memudahkan developer.
  - .length akan mengembalikan nilai dari jumlah panjang data suatu array.
```
let productTeam = ['Product Manager', 'Machine Learning Engineer', 'Back End Developer'];
console.log(productTeam.length);
// Output: 3
```
- **Array Method**. memiliki method atau bisa disebut **built-in methods**. Artinya Javascript sudah memudahkan kita dengan menyediakan function/method umum yang bisa kita gunakan.
- Array Built-in Methods memiliki 5 yaitu:
  - .push() adalah method untuk menambahkan item array pada urutan yang paling akhir.

  ```
  let toDoList = [
    'Belajar javascript',
    'Mencuci Baju',
    'Latihan membuat aplikasi javascript'
  ];
  toDoList.push('Mengikuti kelas Online Programming');
  console.log(toDoList);
  ```

  - .pop() adalah method yang menghapus item array index terakhir.

  ```
  let toDoList = [
    'Belajar javascript',
    'Mencuci Baju',
    'Latihan membuat aplikasi javascript'
  ];
  toDoList.pop();
  console.log(toDoList);
  ```

  - .shift() adalah method untuk menghapus item Array pada index pertama

  ```
  let toDoList = [
    'Belajar javascript',
    'Mencuci Baju',
    'Latihan membuat aplikasi javascript'
  ];
  toDoList.shift();
  console.log(toDoList);
  ```

  - .unshift() adalah method untuk menambahkan item Array pada index pertama

  ```
  let toDoList = [
    'Belajar javascript',
    'Mencuci Baju',
    'Latihan membuat aplikasi javascript'
  ];
  toDoList.unshift('Mengikuti kelas online programming');
  console.log(toDoList);
  ```

  - .sort() adalah method untuk mengurutkan secara Ascending atau Descending Alphanumeric

  ```
  const numbers = [1, 5, 6, 7, 4];
  numbers.sort();
  console.log(numbers);
  ```

- **Looping pada Array**. Array memiliki built in methods untuk melakukan looping yaitu .map() dan .forEach()
  - .forEach() adalah method untuk melakukan looping pada setiap elemen array.

  ```
  const cars = ['tesla', 'honda', 'toyota'];
  cars.forEach(item => {
    console.log(item);
  });
  ```

  - .map() melakukan perulangan/looping dengan membuat array baru.

  ```
  let arr = [1, 2, 3, 4, 5];

  let doubled = arr.map(num => {
    return num * 2;
  });

  console.log(doubled);
  ```

### Multidimensional Array
- **Multidimensional Array** bisa dianalogikan dengan array of array. Ada array didalam array.
- Contoh Multidimensional Array
```
let inventory = [
  ['Kaos Polos', 10],
  ['Jaket Hoodie', 12],
  ['Topi', 24],
  ['Celana Jeans', 8],
];

console.log(inventory);
```

- Akses index Multidimensional Array
```
let inventory = [
  ['Kaos Polos', 10],
  ['Jaket Hoodie', 12],
  ['Topi', 24],
  ['Celana Jeans', 8],
];

console.log(inventory[1][0]);
```
- Multidimensional array dapat menggunakan Property dan Method built-in Array.
```
let inventory = [
  ['Kaos Polos', 10],
  ['Jaket Hoodie', 12],
  ['Topi', 24],
  ['Celana Jeans', 8],
];

inventory.push(['Jaket Sweater', 7])
console.log(inventory);
```
- Operation using map in multidimensional array
```
let inventory = [
  ['Kaos Polos', 10],
  ['Jaket Hoodie', 12],
  ['Topi', 24],
  ['Celana Jeans', 8],
];

inventory.map(dataInventory => {
  let terjual = 100 - dataInventory[1];
  dataInventory[2] = terjual;
});

console.log(inventory);
```
- Looping FOR Multidimensional Array
```
let inventory = [
  ['Kaos Polos', 10],
  ['Jaket Hoodie', 12],
  ['Topi', 24],
  ['Celana Jeans', 8],
];

inventory.forEach((baris) => {
  baris.forEach((column) => {
    console.log(column);
  });
});
```
### Object
- **Object** adalah sebuah tipe data pada variabel yang menyimpan properti dan fungsi (method).
  - **Properti** adalah data lengkap dari sebuah object.
  - **Method** adalah action dari sebuah object. Apa saja yang dapat dilakukan dari suatu object.
- Membuat sebuah object sama seperti tipe data sebelumnya. Object dapat diassign kedalam sebuah variabel.
- Contoh object person dengan properti
```
let person = {
  name: 'Denna Mandela',
  age: 21,
  isVerified: true,
};
```
- Mengakses Object dan Property Object
```
let person = {
  name: 'Denna Mandela',
  age: 21,
  isVerified: true,
};

console.log(person.name);
```
- Gunakan single quote pada key jika menggunakan spasi seperti 'current address'
```
let person = {
  name: 'Denna Mandela',
  age: 21,
  'current address': 'Bandung, Indonesia',
};

console.log(person);
```
- Bracket Notation
- Kita juga bisa menggunakan bracket notation saat memanggil properti dari sebuah object.
```
let person = {
  name: 'Denna Mandela',
  age: 21,
  'current address': 'Bandung, Indonesia',
};

console.log(person['name']);
console.log(person['current address']);
```
- Update Object
  - Object dapat mengupdate value dari key yang sudah tersedia
  - Object dapat menambahkan key dan value baru
- Contoh update data pada object
```
let person = {
  name: 'Denna Mandela',
  age: 21,
  'current address': 'Bandung, Indonesia',
};

// update current key key with the new value
person.age = 22;

// Add new key and value
person.telepon = 089646615043;

console.log(person);
```
- Update data object harus menggunakan let pada deklarasi variabel
```
let person = {
  name: 'Denna Mandela',
  age: 21,
  'current address': 'Bandung, Indonesia',
};

person = {
  fullname: 'Denna Mandela Putra'
}

console.log(person);
```
- Delete Object Property
- Kita dapat menghapus properti dari object menggunakan delete operator.
- Contoh delete property object age dari data people
```
let people = {
  name: 'Denna',
  age: 21,
  isVerified: true,
}

delete people.age;
console.log(people);
```
- **Method**: Jika value yang kita masukkan pada property berupa function. Maka itu disebut method.
- **log()** adalah property yang berupa function dari object console.
- Ada 2 method pada object greeting.
```
const greeting = {
  welcome: function() {
    return 'Halo selamat datang';
  },
  afterTransaction: function() {
    return 'Terima kasih sudah membeli produk kami';
  },
};

console.log(greeting.welcome());
```
- **Nested Object**: Pada real application nanti kalian pasti menemukan data object yang kompleks. Object yang berasal dari turunan object lainnya. 
- Contoh Nested Object Data article pada sebuah aplikasi berita
```
const news = {
  title: 'Impact Byte menjadi Unicorn',
  description: 'Lorem ipsum dolor sit amet.',
  author: {
    people: {
      name: 'Denna Mandela',
      age: 21,
      city: 'Bandung',
    }
  }
};

console.log('News:', news.title);
console.log('Article published by', news.author.people.name);
```
- **Pass by reference**: Kita bisa mengubah data yang ada pada object melalui sebuah function dan memasukkan object sebagai parameter function.
```
let number = {
  originA: 2,
  originB: 3,
};

function changeData (obj) {
  obj.originA = 4;
  obj.originB = 6;
}; 

changeData(number)
console.log(number.originA);
console.log(number.originB);
```
- **Looping Object**
```
const news = {
  title: 'Impact Byte menjadi Unicorn',
  description: 'Lorem ipsum dolor sit amet.',
  author: {
    people: {
      name: 'Denna Mandela',
      age: 21,
      city: 'Bandung',
    }
  }
};

for(let data in news) {
  console.log(news[data]);
};

for(let author in news.author.people) {
  console.log(news.author.people[author]);
}
```
- **Array Object**: Object sama seperti Array yang bisa menyimpan banyak data. Kita dapat menggunakan array of object untuk data yang lebih dari satu. 
- Looping pada Data array of object students
```
let students = [
  {
    name: 'Denna Mandela',
    age: 21,
    isVerified: true,
  },
  {
    name: 'Feby Setia Cipta',
    age: 21,
    isVerified: true,
  },
];

students.forEach((listStudents) => {
  console.log(listStudents);
});
```
### Recursive
- **Recursive** adalah function yang memanggil dirinya sendiri sampai kondisi tertentu.
- Recursive kebanyakan digunakan untuk case matematika, fisika, kimia, dan yang berhubungan dengan calculation.
- Struktur recursive
```
function recursive() {
  // ...
  recursive();
  // ...
}
```
- Recursive akan berhenti memanggil dirinya sendiri jika kondisi terpenuhi
```
function recursive() {
  if(condition) {
    // stop calling itself
    // ...
  } else {
    recursive();
  }
}
```
- Paradigma Baru:
  - procedural
  - conditional
  - looping
  - modular (function)
  - recursive
- Ciri dari rekursif:
  - Fungsi rekursif selalu memiliki kondisi yang menyatakan kapan fungsi tersebut berhenti.
  - Fungsi rekursif selalu memanggil dirinya sendiri sambil mengurangi atau memecahkan data masukan setiap panggilannya.
- Contoh kasus rekursif 
- Fungsi rekursif menghitung mundur number
```
function countDown(fromNumber) {
  console.log(fromNumber);

  let nextNumber - fromNumber - 1;

  //jika kondisi ini bernilai false maka recursive berhenti
  if (nextNumber > 0) {
    countDown(nextNumber);
  }
}

countDown(3);
```
### Asynchronous
- **Asynchronous** mengizinkan komputer memproses task yang lain sambil menunggu proses yang masih berlangsung.
- Beberapa cara untuk membuat asynchronous:
  - Callback
  - Promises
  - Async/Await
- **Callback** function adalah function yang kita letakan di dalam argumen/parameter pada function, dan function tersebut akan dieksekusi setelah function pertama menyelesaikan tugasnya.
- Contoh Callback
```
const mainFunc = (number1,number2,callBack) => {
  console.log(number1 + number2)
  callBack()
}

const myCallback = () => {
  console.log ('Done !')
}

main(1,2,myCallback) // output 3 Done!
```
- Proses asynchronous identik dengan delay, dimana hasil dari proses tersebut membutuhkan selang waktu tertentu untuk menghasilkan output.
- Pada asynchronous kita menggunakan setTimeOut untuk simulasinya. Proses function pada p2 kita lewati sambil menunggu selesai, program lanjut ke function p3
```
const p1 = () => {
  console.log('p1 telah selesai dijalankan');
};

const p2 = () => {
  setTimeout(() => {
    console.log('p2 selesai dijalankan')
  }, 3000)
};

const p3 = () => {
  p1()
  p2()
  console.log('p3 selesai dijalankan');
};

p3();
```
- setTimeout digunakan untuk simulasi asynchronous. Karena sebenarnya kita tidak bisa membuat proses asynchronous murni.
- **Promises** adalah salah satu fitur baru di ES6, biasa digunakan untuk melakukan http request/fetch data dari API.
- Dalam pengambilan data, promise memiliki 3 kemungkinan state yaitu:
  - Pending(sedang dalam proses)
  - Fulfilled (berhasil)
  - Rejected (gagal)
```
const contohPromise = () => {
  new Promise((resolve, rejected) => {
    let condition = true;
    if (condition) {
      resolve('request fulfilled)
    } else {
      reject(new Error('terjadi kesalahan, rejected'))
    }
  }).then(result => console.log(result))
    .catch(error => console.log(error))
}
contohPromise()
```
- **Async-Await** adalah salah satu fitur baru dari javascript yang digunakan untuk menangani hasil dari sebuah Promise.
- Sedangkan await berfungsi untuk menunda sebuah kode dijalankan sampai proses asynchronous berhasil.
- Cara penulisan Async/Await menggunakan es6 dan tidak menggunakan es6.
```
async function hello() {
  let result = await 'Hellooo'
  return result
}
// es6
const hello1 = async () => {
  let result = await 'Helloo'
  result result
}
```
- HTTP Request fetch()
- **Fetch** adalah native web API untuk melakukan HTTP calls dari external network.
- fetch() memiliki parameter utama yaitu URL/endpoint API, dan parameter kedua yaitu options, options ini berisi method, headers dan body.
```
const URL = "https://5e92be81bbff810016969173.mockapi.io/api/v1/users"
const options = {
  method: "GET" / "POST",
  headers: {
    "Content-type": "application/json"
  },
  body: user
}

fetch(URL, options)
```
- Contoh function untuk mengambil data dari API menggunakan fetch(), Promise based.
```
const getDataAPI = () => {
  //deklarasi API endpoint
  const URL = "https://5e92be81bbff810016969173.mockapi.io/api/v1/users";
  // buat option method untuk fetch()
  const options = {
    method: "GET"
  }
  // jalankan fetch dengan api dan option yang kita buat
  fetch(API, option)
  // response pertama, kita ambil data json
  .then(response => response.json())
  .then(result => console.log(result))
  //jika terjadi kesalahan kita tangkap errornya
  .catch(error => console.log(error, "ERROR))
}
```
- Contoh function untuk mengambil data dari API menggunakan fetch(), Dengan Async Await..
```
const getDataAPIwithAsync = async () => {
  const API = "https://5e92be81bbff810016969173.mockapi.io/api/v1/users";
  const option = {
    method = "GET";
  }

  let response = await fetch(API, option)
  response = await response.json()
  console.log(response);
}

getDataAPIwithAsync()
```
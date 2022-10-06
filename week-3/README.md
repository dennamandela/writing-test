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
  - **Properi** adalah data lengkap dari sebuah object.
  - **Method** adalah action dari sebuah object. Apa saja yang dapat dilakukan dari suatu object.
- Membuat sebuah object Sama seperti tipe data sebelumnya. Object dapat diassign kedalam sebuah variabel.
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


















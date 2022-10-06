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








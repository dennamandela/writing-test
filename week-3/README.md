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
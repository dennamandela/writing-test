# Second Week Writing and Presentation Test
## Scope & Function
### Scope
-  **Scope** adalah konsep dalam flow data variabel. Menentukan suatu variabel bisa diakses pada scope tertentu atau tidak.
- Scope ada 2 macam yaitu **Global Scope** dan **Local Scope**.
- **Global Scope** berarti variabel yang kita buat dapat diakses dimanapun dalam suatu file.
- Contoh code global scope
```
let myName = 'Denna';

function greeting() {
    return myName; // Denna
}

console.log(myName); // Denna
```
- **Local Scope** berarti kita mendeklarasikan variabel didalam blocks seperti function, conditional, dan looping.
- Contoh code local scope
```
// Variable declare in function blocks
function greeting() {
    let myName = 'Denna';
    return myName; // Denna
}

console.log(greeting()) // Denna
console.log(myName); // Uncaught ReferenceError: myName is not defined because local scope
```
- **Blocks** adalah code yang berada didalam curly braces ```{}```. Conditional, function, dan  looping menggunakan blocks.
### Function
- **Function** adalah sebuah blok kode dalam sebuah grup untuk menyelesaikan 1 task/1 fitur.
- Membuat Function
```
function greeting() {
  return 'Hello world';
};
```
- Memanggil Function
```
greeting() { // Call the function name
console.log(greeting()); // Output: 'Hello world'
```
### Parameter dan Argumen
- **Parameter** adalah variabel yang digunakan dalam deklarasi fungsi.
- Contoh kode parameter
```
function penambahan (a, b) {
  return a + b;
}
```
- **Argumen** adalah nilai yang digunakan saat memanggil function. Jumlah argumen harus sama dengan jumlah parameternya.
```
function penambahan(a, b) {
  return a + b;
}
console.log(penambahan(5, 5)) // Output: 10
```
- **Default Parameters** digunakan untuk memberikan nilai awal/default pada parameter function.
- Contoh kode default parameters
```
function greetOnWebsite(name = 'Stranger') {
  return 'Hello ' + name;
}
console.log(greetOnWebsite('David')); // Output: 'Hello David'
console.log(greetOnWebsite()); // Output: 'Hello Stranger'
```
- **Function Helper** bisa menggunakan function yang sudah dibuat pada function lain.
- Contoh kode function helpers
```
function multiplyByNineFifths(number) {
  return number * (9/5);
};

function getFahrenheit(celsius) {
  return multiplyByNineFifths(celsius) + 32;
};

getFahrenheit(15); // Returns 59
```
### Arrow Function
- **Arrow Function** adalah cara lain menuliskan function. Ini adalah fitur terbaru yang ada pada ES6 (Javascript Version)
- Contoh kode arrow function
```
const greeting = () => {
  return 'Hello World';
};

const penambahan = (a, b) => {
  return a + b;
};
```


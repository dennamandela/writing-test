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

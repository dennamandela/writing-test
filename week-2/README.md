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

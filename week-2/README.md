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
### Short Syntax Function
- **Single-Line Block**
```
const sumNumbers = number => number + number;
```
- **Multi-Line Block**
```
const sumNumbers = number => {
  const sum = number + number;
  return sum;
};
```
## Data Type Built in Prototypes
## DOM Manipulation
- DOM bukan bagian dari JavaScript, melainkan browser (Web API). Fungsinya untuk memanipulasi tampilan web agar website lebih dinamis dan interaktif.
- Cara memanggil DOM Value yaitu :
  - Memanggil tag HTML berdasarkan ID
  `` console.log(document.getElementByID("header))``
  - Memanggil tag HTML berdasarkan Class Name 
  `` console.log(document.getElementByClassName("text-color-blue"))``
  - Memanggil tag html berdasarkan query selector
  `` console.log(document.querySelector("#header "))`` 
  `` console.log(document.querySelector(".text-color-blue"))``
  - Memanipulasi content
  Cara memanipulasi content :
    - Deklarasi varible header sebagai wadah untuk menyimpan tag HTML
  `` let header = document.getElementById("header"); ``
    - Memanipulasi Content pada Header Content dari pemilik element dengan ID Header dengan text.Content
  `` document.getElementById("header").textContent = "Teks Heading" `` <br />
     Memanipulasi Content didalam sebuah element dengan .innerHTML
  ```
  <ul id= "list"></ul>

  document.getElementById("list").innerHTML = "<li> item1 </li> <li> item2 </li>"
  ```
- Membuat Element HTML
- Contoh :
  ```
  <div id ="header"></div>

  //untuk membuat sebuah elemnt heading
  const heading = dosument.createElement("h1)
  heading.textContent = "Ini Heading"

  document.getElemntByID("header").appendChild(heading)
  ```

- **DOM Events** merupakan object model yang bertugas untuk membantu interaksi user dengan document HTML
- Contoh HTML DOM events
  - Click
  - Scroll
  - Change
  - Focus
  - Hover
  - Submit
  - Blur
- Menangkap Interaksi User
  - Element.addEventListener("event)
  - Element.onevent
- EventListener <br />
  Dengan menggunakan Element.addEventListener("event") dapat menerapkan beberapa hal yaitu :
  - Bisa dihilangkan
  - Bisa ada beberapa event listener yang sama untuk 1 element
  - Memiliki argument tambahan {options}
- Contoh EventListener :
  - EventListener - Click 
    `` <input id="user-input"/> ``
    `` <button id="alert-button">show</button> ``
    Memanggil element berdasarkan id
    `` const input = document.getElementById("user-input") ``
    `` const button = dosument.getElementById("alert-button") ``

    ```
     button.addEventListener("click", function()) {
      alert(input.value)
    } 
    ```
- EventListener - Blur : event dimana sebuah element kehilangan fokus dari user 
- Contoh EventListener - Blur <br />
  Misalkan saat ingin memvalidasi isi dari ``<input id = "username" />`` agar panjangnya minimal 6 karakter

  `` const input = document.getElementById("username") ``

  ```
  input.addEventListener("blur", () => {
    if(input.value.length < 6) alert("Panjang username minimal 6")
  })
  ```
- EventListener - Form Submission
- Contoh EvenListener - Form Submission <br />
  Misalkan terdapat beberapa input dalam sebuah form `` <input name="email"/> `` dan ``<input type="password" name="password"/>`` <br />
  Untuk mendapatkan isi dari kedua inputan tersebut terdapat 2 cara :
  - Memasang event listener di kedua input dan tombol submit, lalu saat tombol diklik, baca value dari kedua input tersebut
  - Memasang event listener di form, lalu gunakan FormData untuk menggambil data dari masing-masing input
  ``` 
    const form = document.getElementById("form")

    form.addEventListener("submit", function(event)){
    event.preventDefault()

    const formData = new FormData(form)
    const values = Object.fromEntries(formData) {
      email: ....
    }
  })
  ```


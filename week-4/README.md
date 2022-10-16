# Fourth Week Writing Test
<<<<<<< HEAD
## Responsive Web Design
### Apa itu Responsive web design?
- Responsive Web Design (RWD) adalah bertujuan membuat desain website kita dapat diakses dalam device apapun.
- Device yang umumnya digunakan adalah laptop/PC, smartphone, dan tablet.
### Setting up Chrome Dev Tools
- Setiap developer website wajib menggunakan tools bawaan dari setiap browser yang memudahkan proses development website.
- Pada browser chrome biasa disebut dengan **Chrome Dev Tools**
- Akses Chrome Dev Tools
  - Jika sudah membuka browser Chrome, kita bisa menggunakan shortcut ini:
  - windows: ```ctrl + shift + j```
### Add Viewport in HTML
- Meta Viewport required on mobile responsive
```
<meta name="viewport" content="width=device-width, initial-scale=1.0">
```
### Use Max-width element
- Panjang Image menjadi overflow karena mengikuti width real bawaan dari file image.
- Add styling max-width
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Responsive Web Design</title>
</head>
<body>
  <img style="max-width: 100%;" src="images/nature.jpg" alt="image">
</body>
</html>
```
### Media Query
- **Media Query** digunakan untuk membuat beberapa styles tergantung pada jenis device.
- Jenis media query
  - Media query untuk responsive web design umumnya hanya menggunakan 2 jenis media query.
  - Keduanya yaitu min-width dan max-width
- Setting up media query
```
@media screen and (min-width: your pixel) {
  /* your tag element html and your css*/
}

@media screen and (max-width: your pixel) {
  /* your tag element html and your css*/
}
```
=======
## Git & GitHub Intermediate
- Git adalah
- https://www.canva.com/design/DAFPHS5H2b4/W-Jg1VIYmKiIDB4f5PXgjA/edit?utm_content=DAFPHS5H2b4&utm_campaign=designshare&utm_medium=link2&utm_source=sharebutton
>>>>>>> cb29e2c1d10b63778ac3a308794476004e648740

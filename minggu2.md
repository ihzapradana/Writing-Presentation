# **Ringkasan Materi Minggu 2 Bootcamp Coding**

# **Scoop & Function**<br>
- **Scoop**<br>
Scope atau disebut juga dengan ruang lingkup adalah konsep dalam flow data variabel. Menentukan suatu variabel bisa diakses pada scope tertentu atau tidak. <br>
Komponen yang perlu diperhatikan dalam scoop diantaranya : <br>
<ol>
<li>Block</li>
Block adalah code yang berada didalam curly braces {}. Conditional, function, dan  looping menggunakan blocks.
<li>Global Scoop</li>
Global scope berarti variabel yang kita buat dapat diakses dimanapun dalam suatu file. Agar menjadi Global Scope, suatu variabel harus dideklarasikan diluar Blocks.
<li>Local Scoope</li>
Local scope berarti kita mendeklarasikan variabel didalam blocks seperti function, conditional, dan looping. Maka variabel hanya bisa diakses didalam blocks saja. Tidak bisa diakses diluar blocks.
</ol>

- **Function**<br>
Function adalah sebuah blok kode dalam sebuah grup untuk menyelesaikan 1 task/1 fitur. Saat kita membutuhkan fitur tersebut nantinya, kita bisa kembali menggunakannya.<br>
<ol>
<li>Cara Membuat dan Memanggil Function</li>

```javascript 
    function greeting(){
    console.log('Hello World!!') ;
}
greeting()
```
<li>Parameter & Argument</li>

```javascript
    function pengurangan(a,b){
    return a - b ;
}
pengurangan(10-5);
```
Pada code program di atas, a & b merupakan parameter, sedangkan 10 & 5 adalah argument.
<li>Macam-macam Function</li>

- Function Classic<br>

```javascript
function myFunction( kondisi ){
     statement;
}
```
- Function Variabel<br>
```javascript
    let myFunction = function(){
        statement;
    }
```

- Arrow Function<br>
```javascript
    let myFunction = () => {

    }
```
</ol>
<br>

# **Data Type Built in Prototype & Method**<br>
Berikut adalah macam-macam tipe data yang ada di Javascript :
<br>

```javascript
    let angka = 42; // angka adalah bertipe data number
    angka = "bar"; // angka adalah bertipe data string
    angka = true; // angka adalah bertipe data boolean
```
JavaScript juga merupakan bahasa yang diketik dengan lemah, yang berarti memungkinkan konversi tipe implisit saat operasi melibatkan tipe yang tidak sama, misalnya :<br>

```javascript
    const angka = 42; // angka adalah bertipe data number
    const result = angka + "1"; // JavaScript memaksa angka ke string, sehingga dapat digabungkan dengan operand lainnya
    console.log(result); // Output => 421
```
Himpunan tipe dalam bahasa JavaScript terdiri dari Primitive dan Non Promitive. <br>
<B>Primitive</B> :
<ol>
<li>Numbers</li>
<li>Strings</li>
<li>Boolean</li>
<li>undefined</li>
<li>null</li>
</ol>
<B>Non Primitive :</B>
<ol> 
<li>Objects</li>
<li>Array</li>
<li>Functions</li>
</ol>

## **String** <br>
Objek String digunakan untuk mewakili dan memanipulasi urutan karakter. String dapat dibuat dengan menggunakan petik dua (" "), petik satu (' ') atau menggunakan backtick (``). <br>

```javascript
    const string1 = "A string primitive";
    const string2 = 'Also a string primitive';
    const string3 = `Yet another string primitive`;
```
Ada banyak cara untuk dapat mengakses karakter dalam string, beberapa diantaranya :<br>
- charAt() <br>
Digunakan untuk mengambil index karakter. <br>
```javascript
    'cat'.charAt(1) // karakter yang didapatkan yaitu : "a"
```
- toUppercase(), toLowerCase() & .length<br>
toUppercase() : untuk membuat semua karakter dalam string menjadi huruf kapital semua. Sedangkan toLowerCase() : untuk membuat semua karakter dalam string menjadi huruf kecil semua. Kemudian (.length) adalah untuk menghitung jumlah karakter dari string tersebut.<br>
```javascript
    let hewan = "kanCil"
    console.log(hewan.length) // Output : 6
    console.log(hewan.toUpperCase())  // Output "KANCIL"
    console.log(hewan.toLowerCase()) // Output "kancil"
```
## **Number** <br>
Number adalah objek pembungkus yang digunakan untuk mewakili dan memanipulasi angka seperti 28 atau -3,14. <br>
Ada banyak cara untuk dapat mengakses karakter dalam number, beberapa diantaranya : <br>
- isNan() , untuk mengecek apakah bukan angka / Not A Number. <br>
- toString() , untuk mengubah number menjadi angka. <br>
- toFixed() , untuk membulatkan sebuah bilangan desimal. <br>

## **Object Math** <br>
Math adalah objek bawaan yang memiliki properti dan metode untuk konstanta dan fungsi matematika. <br>
Ada beberapa properti object math : <br>
- Math.E => untuk Bilangan Euler. <br>
- Math.LN2 => Untuk mencari Log 2 <br>
- Math.LN10 => Untuk mencari Log 10 <br>
- Math.LOG2E => Untuk mencari Log E di basis 2 <br>
- Math.Log10E => Untuk mencari Log E dibasis 10 <br>
- Math.PI => pi / 3,14
- Math.sqrt1_2 => Untuk mencari akar 1/2 <br>
- Math.sqrt2 => Untuk mencari akar kuadrat. <br>

Selain itu juga ada object method, diantaranya : <br>
- Math.random() => Untuk menampilkan angka random.<br>
- Math.sqrt(number) => Untuk mencari akar kuadrat <br>
- Math.cbrt(number) => Untuk mencari akar kubik <br>
- Math.max() => Untuk mencari bilangan terbesar <br>
- Math.min() => Untuk mencari bilangan terkecil <br>
- Math.round() => Untuk membuulatkan bilangan desimal >= 5. <br>
- Math.ceil() => Berapapun angka dibalekang koma, akan dibulatkan ke yang terbesar. <br>
- Math.floor() =>  Berapapun angka dibalekang koma, akan dibulatkan ke yang terkecil. <br>
- Math.abs() => Mengubah nilai (-) menjadi (+).<br>
- Math.pow(x,y) => Untuk menghitung x pangkat y. <br> <br>

# **Javascript DOM** <br>
## **DOM Introduction** <br>
DOM adalah singkatan dari Document Object Model. Jadi, ketika halaman website kita diload, browser kita akan membuat Document Object Model dari halaman website kita. Dengan adanya DOM ini, JavaScript diberi akses untuk membuat HTML menjadi dinamis, seperti:<br>
<ol>
<li>Mengubah element HTML pada halaman website.</li>
<li>Mengubah attribute HTML pada halaman website.</li>
<li>Mengubah CSS style pada halaman website.</li>
<li>
Menambah dan/atau menghapus element maupun attribute HTML.</li>
<li>Menambah HTML event (contoh: efek klik pada mouse, hover pada mouse, dan lain-lain) pada halaman website.</li>
<li>Berinteraksi dengan semua HTML event di website.</li>
</ol>
<br>
Di HTML DOM, semua element HTML dari sebuah website dianggap sebagai objek. Dan sama seperti objek JavaScript pada umumnya, objek element HTML di HTML DOM juga mempunyai properti dan method atau yang lebih dikenal dengan istilah DOM Property dan DOM Method. Jadi untuk mengubah nilai properti dari element HTML, kita bisa menggunakan DOM Property dan untuk memanggil fungsi dari suatu element HTML, kita bisa menggunakan DOM Method.<br> <br>

## **Selecting Element & Traversing** <br>
Dalam menggunakan HTML DOM, kita bisa melakukan traversing untuk mengakses element HTML, diantaranya : <br>
Berikut adalah code program file HTML nya : <br>
```javascript
    <body>
        <h1 id="title">Hallo</h1>
        <ul class="list">
            <li class="item">satu</li>
            <li class="item">dua</li>
            <li class="item">tiga</li>
        </ul>

        <div class="hewan">
            <ul class="Ternak">
                <li>Sapi</li>
                <li>Kambing</li>
                <li>Ayam</li>
            </ul>
        </div>
    </body>
```
Berikut adalah macam-macam traversing ke bawah :
- **getElementById(id)** <br>
Kita bisa menggunakan getElementById untuk mengakses element HTML berdasarkan nilai id-nya. <br>
```javascript
    let title = document.getElementById("title")
    console.log(title)
```
- **getElementsByTagName(tag)**<br>
Untuk mengakses element-element HTML berdasarkan jenis tag-nya, kita bisa menggunakan getElementsByTagName. <br>
```javascript
    let itemByTag = document.getElementsByTagName("li")
    console.log(itemByTag[1])
```
- **getElementsByClassName(className)** <br>
Untuk mengakses element-element HTML berdasarkan nilai attribute class-nya, kita bisa menggunakan getElementsByClassName. <br>
```javascript
    let list = document.getElementsByClassName("list")
    console.log(list[0])
```
- **querySelectorAll(cssSelector)**<br>
Untuk mengakses element-element HTML berdasarkan CSS Selector-nya HTML, kita bisa menggunakan querySelectorAll. <br>
```javascript
    let itemAueryAll = document.querySelectorAll(".item")
    console.log(itemAueryAll[1])
```
Kemudian ada traversing ke atas :
- **parentElement** <br>
Digunakan untuk mencari parent terdekatnya. Berikut syntaxnya :
```javascript
    console.log(queryItem.parentElement);
```
- **closset()**<br>
Digunakan untuk mencari parent terjauhnya. Berikut syntaxnya :
```javascript
    console.log(queryItem.closest("body"))
    console.log(queryItem.closest(".list"))
```

Kemudian ada traversing ke samping :
- **previusElementSibling** <br>
Digunakan untuk mencari kakak dari sebuah element. Berikut syntaxnya :
```javascript
    console.log(queryItem.previousElementSibling);
```
- **nextElementSibling** <br>
Digunakan untuk mencari adik dari sebuah element. Berikut syntaxnya :
```javascript
    console.log(queryItem.nextElementSibling);
```
<br>

# **DOM Manipulating Element & Style** <br>
## **Mengubah Konten HTML** <br>
Berikut adalah contoh code HTML nya : <br>
```javascript
    <body>
        <div id="tess"></div>
        <div id="app"></div>
        <div id="end">
            <a href="google.com" class="link">google</a>
        </div>
    </body>
```
Kita dapat mengubah konten dalam contoh HTML di atas menggunakan beberapa cara, diantranya : <br>
- **Element.innerHTML = " "** <br>
Element.innerHTML dapat kita gunakan untuk mengubah konten HTML di dalam sebuah element. <br>
Berikut adalah contoh penerapannya : <br>
```javascript
    let app = document.getElementById("app")
    console.log(app)

    app.innerHTML = "<h1>Hallo</h1>"
```
- **Element.innerText = " "** <br>
Element.innertext dapat kita gunakan untuk mengubah teks di dalam sebuah element. <br>
Berikut adalah contoh penerapannya : <br>
```javascript
    let paragraf = document.createElement("p")
    paragraf.innerText = "ini adalah paragraph"
```
Selain itu, kita juga dapat menyisipkan teks p yang disimpan dalam variabel paragraf ke dalam tag h1 yaitu dengan menggunakan .append(). <br> 
Berikut adalah penerapannya : <br>
```javascript
    app.append(paragraf)
```
## **Melakukan Styling Menggunakan DOM** <br>
Selain dapat mengubah konten yang ada dalam HTML, kita juga dapat malakukan styling seperti halnya di CSS, tapi di Javascript dengan menggunakan DOM. <br>
Berikut untuk penerapannya : <br>
```javascript
    let link = document.getElementsByClassName("link")[0]
    link.style.color = "red"
    link.style.border = "2px solid red"
    link.style.padding = "5px 10px"
    link.style.backgroundColor = "aqua" 
```
<br>

# **DOM Events** <br>
Event adalah tindakan yang terjadi di browser web, berupa umpan balik browser web kepada kita sehingga kita dapat meresponsnya. Misalnya, saat pengguna mengklik tombol di halaman web, kita sebagai developer mungkin ingin merespons peristiwa klik ini dengan menampilkan kotak dialog. Setiap event mungkin memiliki event handler yang merupakan blok kode yang akan dieksekusi ketika event terjadi. Event handler juga dikenal sebagai event listener yang mendengarkan event dan mengeksekusi ketika event itu terjadi. <br>

File HTML :
```javascript
    <body>
        <h1 onclick="alert('selamat datang')">Hallo</h1>
        <p id="paragraf">Click Me</p>
        <button id="btn">ini button</button>
    </body>
```
Ada banyak event yang dapat kita gunakan, berikut contoh penerapan yang diajarkan di kelas : <br>
- **Event onclick** , yang ketika diklik akan memunculkan sebuah pop up.
```javascript
    let paragraf = document.getElementById("paragraf")
    paragraf.onclick = function() { 
        alert("in dari paragraf")
    }
```
- **Event onmouseover** , yang ketika kita menggerakkan mouse terhadap element yang dipilih akan memunculkan pop up.<br>
```javascript
    let paragraf = document.getElementById("paragraf")
    paragraf.onmouseover = function() { 
        alert("in dari paragraf")
    }
```
- **Event addEventListener** , yang dapat multiple action (bisa memunculkan >1 aksi). Misal ketika mnegklik tombol "ini button" akan memunculkan alert dan confirm. <br>
```javascript
    let button = document.getElementById("btn")
    button.addEventListener("click", function(event){
        alert("ini adalah button")
        confirm("apakah ini button?")
    })
```
<br>

# **DOM Forms** <br>
Seringkali kita menjumpai beberapa form inputan untuk user dalam sebuah website, yang mana form inputan tersebut digunakan agar sistem bisa mendapatkan data informasi user, seperti email & password yang sering kita jumpai. Untuk itu, kita memerlukan DOM untuk mendapatkan data inputan dari user tersebut.<br>
Nah kali ini, method yang digunakan untuk mengatasi permasalahan tersebut yaitu method addEventListener(). <br>
Berikut adalah contoh penerapannya : <br> <br>
File HTML
```javascript
  <body>
    <div class="container">
      <form id="sign-in">
        <h1>Sign In</h1>

        <div class="field">
          <label for="username">username</label>
          <input type="text" id="username" name="username" />
        </div>

        <div class="field">
          <label for="password">password</label>
          <input type="text" id="password" name="password" />
        </div>

        <button type="submit">login</button>
      </form>
    </div>
  </body>
```
File Javascript <br>
```javascript
let loginForm = document.querySelector("#sign-in")
let inputUsername = document.querySelector('#username')
let inputPassword = document.querySelector('#password')

// Setting username & password dalam variabel
let user = {
  username: "ganif",
  password: "123"
}

loginForm.addEventListener("submit", (event) => {
  event.preventDefault() // Untuk menghilangkan settingan default HTML yang melakukan refresh otomatis

  let userLogin = { //Untuk mendapatkan data inputan user
    username: inputUsername.value,
    password: inputPassword.value
  }

  console.log(userLogin); // Menampilkan hasil inputan user di console

// Melakukan pengecekan, apakah inputan user sesuai dengan username & password yg telah di setting di variabel user
  let login = userLogin.username == user.username && 
              userLogin.password == user.password;

  if (login) {
    console.log("selamat anda berhasil login")
  } else {
    console.log("username dan password anda salah");
  }

  loginForm.reset() // Untuk membersihkan Form
```
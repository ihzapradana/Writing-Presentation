# **Ringkasan Materi Minggu 3 Bootcamp Coding**

# **Array & Multidimensional Array** <br>
## **Array** <br>
Array pada Javascript adalah variabel yang dapat menyimpan banyak data dengan tipe data apapun. Array mempunyai beberapa method diantaranya : <br>
<ol>
<li>pop()</li>
Untuk menghapus element terakhir.
<li>push()</li>
Untuk menambahkan element ditaruh di posisi paling akhir.
<li>shift()</li>
Untuk menghapus element pertama.
<li>unshift()</li>
Untuk menambahkan element ditaruh di posisi paling awal.
<li>splice()</li>
Digunakan untuk memotong array, menambahkan elemen array, bahkan melakukan keduanya sekaligus.
<li>slice()</li>
digunakan untuk ’memotong’ array menjadi array baru, atau menjadi ’sub-array’ dari array asal.
<li>join()</li>
Digunakan untuk menggabungkan elemen array menjadi sebuah string.
<li>reverse()</li>
Digunakan untuk membalikkan urutan dari elemen di dalam array.
<li>sort()</li>
Digunakan untuk mengurutkan elemen pada array baik secara ascending atau descending.
<li>filter()</li>
Digunakan untuk melakukan filter data dengan kondisi tertentu pada setiap elemen dari array yang sudah ada.
<li>toString()</li>
Digunakan untuk mengubah isi di array menjadi string. <br>
Dan masih banyak lagi method-method array yang lainnya.
</ol>

- **Array Loop** <br>
Untuk dapat melakukan looping dalam array kita dapat menggunakan perulangan for, for...of, forEach() & map(). <br>
```javascript
    let motor = [
    'CBR',
    'Ninja',
    'R1',
    'GSX',
    'R6'
    ]   
```
**for()**<br>
```javascript
    for (let i = 0; i < motor.length; i++) {
    console.log(motor[i])
    }
```
**for...of**()
```javascript
    for (let kendaraan of motor){
    console.log(kendaraan);
    }
```
**forEach()**
```javascript
    motor.forEach((item) => {
    console.log(item)
    })
```
**map()**
```javascript
    let motorKeren = motor.map((item) => {
    return item + " " + "keren boss"
    })
    console.log(motorKeren)
```
**Perbedaan for(), forEach() & map() :** <br>
- forEach() digunakan jika hanya ingin melakukan looping biasa saja & forEach tidak bisa di **return**, sedangkan map() bisa di **return**.<br>
- for() digunakan jika membutuhkan looping yang dapat dihentikan. <br>
- map() digunakan jika membutuhkan looping yang dapat mengembalikan data array sebanyak array yang di looping.<br>

## Array Multidimensional <br>
Multidimensional Array bisa dianalogikan dengan array of array (ada array di dalam array). Baris pada table itu menunjukan jumlah array. Sedangkan Column pada table itu menunjukan isi dari tiap array. <br>
Berikut adalah implementasinya :   <br>
```javascript
    let profil = [
    ["nama", "ihza"],
    ["umur", 19],
    ["semester", "5"],
    ]

    console.log(profil[0][1]); // Output : ihza
    console.log(profil[2][1]) // Output : 5

    profil[2][1] = "6" // untuk mengubah value 5 menjadi 6 pada key semester
    console.log(profil); 
```
<br>

# Object & Array Of Object <br>
## Object
Object adalah sebuah tipe data pada variabel yang menyimpan properti dan fungsi (method). Properti adalah data lengkap dari sebuah object. Method adalah action dari sebuah object.
Berikut adalah implementasi cara mengakses objek : <br>
```javascript
    let siswa = {
    nama : 'Ihza',
    umur : 19,
    'nomor hp' : 08832472
    }
```
<ol>
<li> <B>Menggunakan Dot Notation</B></li>

```javascript
    console.log(siswa.umur) // Output 19
```

<li><B>Menggunakan Bracket</B></li>

```javascript
    console.log(siswa['umur']) // Output 19
    console.log(siswa["nomor hp"]) // Output 08832472
```
<li><B>Memanggil nama objek dengan variabel</B></li>

```javascript
    let property = 'umur'
    console.log(siswa[property]); // Output 19
```
</ol>

- **Cara menambah property baru dalam objek** <br>
```javascript
    let buku = {
        judul : 'mantan jadi manten',
        penulis : 'hayati',
        'jumlah halaman': 250
    }

    buku.tahun = 2022 // Menambahkan property tahun = 2022
    buku['penerbit'] = 'gramedia' // Menambahkan property penerbit = gramedia
    console.log(buku)
```
- **Cara mengganti property dalam objek** <br>
```javascript
    let hewan = {
        nama : 'kucing',
        warna : 'putih',
        kaki : 4
    }
    hewan.nama = 'anjing' // Mengganti value property nama  menjadi anjing
    hewan['kaki'] = 2 // Mengganti value property kaki menjadi 2
    console.log(hewan);
```

- **Cara menghapus property** <br>
```javascript
    let hewan = {
        nama : 'kucing',
        warna : 'putih',
        kaki : 4
    }
    delete hewan.warna // Menghapus property warna dari objek hewan
    console.log(hewan);
```

## Array Of Object <br>
Yaitu adanya objek di dalam sebuah array. Karena berada dalam sebuah array, maka objek-objek tesebut akan mempunyai index. Berikut implementasinya :
```javascript
    let user = [
    {
        nama : 'himawan',
        umur : 19,
        alamat : 'jember'
    },

    {
        nama : 'ihza',
        umur : 19,
        alamat : 'jakarta'
    },

    {
        nama : 'pradana',
        umur : 19,
        alamat : 'Malang'
    }
    ]

    console.log(user);
```
Kemudian melakukan Looping menggunakan map() <br>
```javascript
    let data = user.map((item) =>{
    item.status = 'aktif' // Menambahkan property status dengan value aktif pada setiap objek
    return item
    })
    console.log(data);
    console.log(user[0].nama); // Ouput : himawan
```
Cara contructor
```javascript
    let data = user.map(({nama}) => {
        console.log(nama) // Menampilkan semua nama pada masing-masing objek : himawan, ihza, pradana
    })
```
<br>

# **Moduls & Rekursif** <br>
## **Moduls**
Moduls adalah cara untuk memisahkan kode ke file yang berbeda. Keuntungan ketika kita menggunakan moduls diantaranya : <br>
<ol>
<li>Mudah untuk mengelola kode</li>
<li>Kode tidak tertumpuk dalam 1 file</li>
</ol>
Contoh penerapan moduls yaitu : <br>
Misalkan terdapat 3 file javascript yang berbeda, yaitu (indonesia.js , jepang.js , amerika.js) dan file indonesia.js yang ditautkan dalam file HTML nya. Maka, file indonesia.js dapat mengakses / mengimport file (jepang.js) & (amerika.js). Kemudian file (jepang.js) dapat mengakses / mengimport file (amerika.js). Namun, file (jepang.js & amerika.js) tidak mengakses file indonesia.js & file (amerika.js) tidak dapat mengakses file (jepang.js). <br>
Berikut untuk penerapannya : <br>

**File indonesia.js**
```javascript
// File indonesia.js => import dari file jepang dan amerika
import Entertainment, { motor as motorJepang, smartPhoneJepang, sayHello } from "./jepang.js"
import {apple} from './amerika.js';

sayHello()

console.log(Entertainment);
console.log(smartPhoneJepang);

console.log(motorJepang);
console.log(apple);
```
**File jepang.js**
```javascript
    import {apple} from './amerika.js'; // import dari amerika.js
    console.log(apple);

    let motor = ["suzuki", "yamaha", "honda", "kawasaki"]
    const smartPhone = ["sony", "samsung", "fujitsu", "LG"]

    export function sayHello() {
    console.log("hallooo")
    }
    let entertainment = ["anime", "manga", "wibu", "dorama"]
    export default entertainment //untuk mengexport produk utama
    //export default cuma bisa 1 yg di export
```
**FIle amerika.js** 
```javascript
    let apple = ["iphone", "macbook", "imac"]
    export {apple} // mengekspor variabel apple ke luar
```
## Rekusif 
Rekursif adalah function yang memanggil dirinya sendiri sampai kondisi tertentu. Rekursif biasanya diguanakan dalam permasalahan matematika, kimia, fisika dan yang berhubungan dengan kalkulasi. <br>
Dalam rekursif, terdapat 2 komponen utama yaitu: <br>
- **Base case** , yaitu titik paling kecil (berhenti). <br>
- **Recursion case** , yaitu titik memanggil dirinya sendiri.<br>

Berikut implementasinya dalam case mencari angka faktorial :<br>
```javascript
    function faktorial(n) {
    if (n == 1) { // Base cae
      return 1
    } else { 
      return n * faktorial(n - 1) // Recursion case
    }
  }
  console.log(faktorial(5)) // Output 120
```
<br>

# **Asynchronus**
Javasvript mempunyai 3 sifat, diantaranya : <br>
<ol>
<li> <B>Single Thread</B> (Punya 1 jalur saja)</li>
<li><B>Non-Blocking</B></li>
Kalau ada proses yang lama, maka dia akan di pending dulu (mengalah) mengijinkan untuk mengeksekusi perintah yang selanjutnya.
<li><B>Asynchronus</B></li> 
Adalah proses yang tidak berurutan / eksekusi tidak selalu berdasarkan urutan kode, tetapi berdasarkan waktu proses (yang dieksekusi yaitu prosesnya yang pendek terlebih dahulu). Eksekusi dengan asynchronous tidak akan membloking atau menunggu suatu perintah sampai selesai. Daripada menunggu, asynchronous akan mengeksekusi perintah selanjutnya. 
</ol>
Ada 3 teknik yang digunakan dalam asynchronus ini, yaitu <B>Callback</B>, <B>Promise</B>, <B>Async-await</B>. Namun, pada minggu ini yang dipelajari hanya sampai callback & promise.

- **Callback** <br>
Adalah function yang dijadikan argument. Berikut untuk penerapannya : <br>
```javascript
    console.log("A")

    setTimeout(() => {
    console.log("B")
    }, 1000)

    console.log("C")
```
Jika kode program di atas dijalankan, maka urutan outputnya akan :<br>
<ol>
<li>A</li>
<li>C</li>
<li>B</li>
</ol>
Mengapa bisa terjadi urutan seperti itu? Urutan tersebut terjadi karena setelah mengeksekusi console.log("A"), akan mengeksekusi console.log("B"). Namun, terdapat setTimeout yang membuat proses untuk menampilkan string B membutuhkan waktu. Oleh karena itu, proses tersebut akan dipending dulu & lanjut untuk mengeksekusi perintah selanjutnya yaitu menampilkan string C. <br><br>

- **Promise** <br>
Dalam pengertian harfiah promise adalah janji. Dalam Javascript promise merepresentasikan sebuah object request pengolahan data yang dilakukan secara asynchronous dan promise ini mewakili sebuah operasi yang belum selesai, tetapi diharapkan di masa mendatang. Berikut untuk penerapannya : <br>
```javascript
    let jalanPromise = new Promise((resolve, reject) => {
    if (true){
        resolve('jalan terpenuhi') // jika berhasil
    }
    
    reject('gagal jalan') //jika gagal
});

jalanPromise
.then((result) => { // nangkap yg berhasil
    return `${result} bareng doi`;
})
.then((result) => {
    return `${result} nih boss`;
})
.then((result) => {
    console.log(result); // Output : jalan terpenuhi bareng doi nih boss
})
.catch((err) => { // nangkap yg gagal
    console.log(err);
});
```
Dari kode program di atas, Output yang didapatkan yaitu berupa string "jalan terpenuhi bareng doi nih boss", karena kondisinya adalah true. Jika kondisinya dalam if adalah false, maka outputnya adalah "gagal jalan". <br><br>

# **Web Storage**
Dengan web storage, aplikasi web dapat menyimpan data secara lokal di dalam browser pengguna. Kemudian Web API adalah jembatan agar HTML & Javascript bisa berinteraksi dengan browser. Selain web storage, ada cookies yang juga merupakan penyimpan data namun cookies hanya dapat menyimpan kurang dari 100 sampai 200 bytes. Sedangkan web storage dapat meniympan data hingga 5 MB. Tujuan menggunakan web storage diantaranya adalah : <br>
<ol>
<li>Preferensi user, ex : dark mode</li>
<li>Setting</li>
<li>Menyimpan Score</li>
<li>Menyimpan posisi video terkhir dilihat</li>
</ol>
Dalam web storage, ada 2 objek untuk menyimpan data client : <br>
<ol>
<li><B>window.localStorage</B> = menyimpan data tanpa tanggal kedaluwarsa / unlimited</li>
<li><B>window.sessionStorage</B> = menyimpan data untuk satu sesi (data hilang saat tab browser ditutup).</li>
</ol>
Ada beberapa metode yang dapat digunakan dalam menggunakan localStorage, yaitu : <br>

- **setItem()** <br>
Metode ini digunakan untuk menyimpan data kedalam localStorage. Dalam penggunaannya dibutuhkan dua parameter yaitu key dan value. Pada localStorage data yang disimpan dapat berupa object atau array, hanya saja sebelum data disimpan harus diubah terlebih dahulu menjadi string karena localStorage hanya menerima tipe data string. Untuk mengubahnya kita dapat menggunakan JSON.Stringfy(NamaVariabel).<br>
- **getItem()** <br>
Metode ini memungkinkan kalian untuk mengakses data yang disimpan pada localStorage. Nah setelah berhasil mengakses, untuk mengambil data localStorage berupa object atau array kita dapat menggunakan JSON.parse(NamaVariabel). <br>
Berikut untuk implementasi dengan case membuat to do list aktivitas : <br>
```javascript
    const todos = [];
    if (localStorage.getItem("todo")) { // untuk mengkases todo
    const todoStore = JSON.parse(localStorage.getItem("todo")); // mengakses todo & merubah string ke objek

    todoStore.map((todo) => { // melakukan mapping
    const li = document.createElement("li"); // membuat list untuk menampilkan todo
    li.innerText = todo; // menyisipkan teks ke dalam tag li

    const container = document.querySelector("#list-container");
    return container.appendChild(li); // Mengembalikan isi dalam tag li yang ditambahkan ke dalam variabel container
  });
}

document.querySelector("form").addEventListener("submit", (ev) => { 
    ev.preventDefault();
    const userInput = document.querySelector("input").value; // Mendapatkan value dari inputan
  
    const li = document.createElement("li"); // membuat list untuk menampilkan todo inputan user
    li.innerText = userInput; // Menyisipkan teks inputan user ke dalam tag li
  
    todos.push(userInput); // Menambahkan value inputan user ke dalam list variabel todos di atas
  
    localStorage.setItem("todo", JSON.stringify(todos)); // Menyimpan list todos & mengubahnya menjadi string
  
    const container = document.querySelector("#list-container");
    container.appendChild(li); // Menambahkan isi dalam tag li ke dalam variabel container
  });
```
Berikut contoh implementasi dalam case membuat dark mode : <br>
```javascript
if (localStorage.getItem("theme") === "dark") { // Untuk mengakses theme & memberikan kondisi
    document.body.classList.add("dark"); // Membuat class dark dalam body jika memenuhi kondisi
  } else {
    document.body.classList.remove("dark"); // Menghapus class dark jika tidak memenuhi kondisi
  }
  
  document.getElementById("toggle").onclick = () => { // Memberikan event onclick pada id toggle
    if (localStorage.getItem("theme")) { // Untuk mengakses theme
      localStorage.removeItem("theme"); // Menghapus theme
      document.body.classList.remove("dark"); // Menghapus class dark jika memenuhi kondisi
    } else {
      localStorage.setItem("theme", "dark"); // Menyimpan theme & dark jika tidak memenuhi kondisi
      document.body.classList.add("dark"); // Membuat class dark dalam body jika tidak memnuhi kondisi
    }
  };
```
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
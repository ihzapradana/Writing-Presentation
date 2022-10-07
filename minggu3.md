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
Object adalah sebuah tipe data pada variabel yang menyimpan properti dan fungsi (method). Properti adalah data lengkap dari sebuah object. Method adalah action dari sebuah object.
Berikut adalah implementasi 
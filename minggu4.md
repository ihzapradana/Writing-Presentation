# **Ringkasan Materi Minggu 3 Bootcamp Coding**

# **Asynchronus ~ Fetch & Async Await** <br>
## **Async-Await()**<br>
Async-await adalah salah satu cara untuk menangkap promise selain menggunakan then() & catch(). <br>
Berikut untuk implementasi penggunakan async-await : <br>

```javascript
    async function asyncNonton() {
    try { //Akan ditampilkan ketika kondisinya true
        let result = await nonton("jalan")
        console.log(result);
    } catch (error) { //Akan ditampilkan ketika kondisinya false
        console.log(error)
    }
}
asyncNonton() //Memanggil fungsi
```
Pada contoh diatas, pertama kita memiliki function dengan menambahkan async didepan function yang mana berfungsi untuk menjadikan function tersebut asynchronous, dan await berfungsi menunda eksekusi hingga proses asynchronous selesai. <br>

## **Fetch()** <br>
Fetch adalah sebuah objek promise untuk mengambil data dari API yang di handle menggunakan promise atau async-await. Nah, lalu apa itu API? API adalah jembatan komunikasi ke server untuk mendapatkan data. <br>
Berikut untuk implementasi penggunaan fetch untuk mendapatkan data digimon: <br>

```javascript
    fetch("https://digimon-api.vercel.app/api/digimon") //Mengambil data dari API
    .then(result => result.json()) //Membuka (unboxing) data yang telah diambil
    .then(result => { 
    console.log(result) //Menampilkan data yang telah diambil dari API
    })
```
<br>

# **Git & Github Lanjutan**
Dalam materi ini, kami diajarkan untuk berkolaborasi dalam mengerjakan di satu tim yaitu dengan membuat sebuah organisasi baru di github. Untuk team leader, ada beberapa step yang harus dilakukan diantaranya : <br>
- Terlebih dahulu membuat organisasi, caranya yaitu : <br>
<ol>
<li>Dengan mengklik tombol (+) di pojok kanan atas.</li>
<li>Lalu pilih "new organitation".</li>
<li>Repo dibuat public, dan ceklist README.</li>
<li>Kemudian buat branch bernama dev.</li>
</ol>

- Mengecek pull request
<ol>
<li>setiap ada pull request, team lead akan mengeceknya
</li>
<li>Jika pull request belum sesuai, bisa dikasih komen atau beri kabar anggota yg melakukan pull request tersebut
</li>
<li>Jika sudah sesuai, lakukan merge</li>
</ol>

- Saat aplikasi sudah selesai
<ol>
<li>saat ini semua perubahan ada pada branch dev</li>
<li>Jika sekiranya sudah tidak ada update terbaru dari development, saatnya menggabungkan antara branch dev ke branc main</li>
<li>lakukan pull request utk menggabungkan branch dev ke branc main</li>
</ol>

Untuk semua anggota step yang harus dilakukan diantaranya : <br>
<ol>
<li>masing-masing anggota lakukan git clone pada repo yg sudah dibuat (1x aja</li>
<li>Bagi tugas pada masing-masing anggota kelompok</li>
<li>pindah ke branch dev git switch dev</li>
<li>sebelum ngoding, lakukan git pull pada branch dev untuk update kode terbaru</li>
<li>Anggota membuat branch dari dev git branch [nama-branch]</li>
<li>Pindah ke dalam branch yg sudah dibuat git switch [nama-branch]</li>
<li>lakukan pengerjaan di dlm branch tersebut</li>
<li>lakukan git pull origin dev</li>
<li>Jika ada conflict, bereskan semuanya</li>
<li>jika sudah aman, commit lalu git push origin [nama-branch]</li>
<li>lakukan pull request untuk merge ke branch dev</li>
<li>tunggu pull request di acc oleh team lead</li>
<li>Jika sudah, ulangi proses dari no 2</li>
</ol>
Jika terjadi conflict (terjadi jika terdapat 1 file yang diedit oleh lebih dari 1 orang), cara meneyelesaikannya yaitu : <br>
<ol>
<li>lakukan git merge dev ( dilakukan di branch yang sedang conflict</li>
<li>kemudian pilih mau ambil update an yang mana</li>
<li>lakukan git add, git commit & git push seperti biasa.</li>
</ol> <br>

# **Responsive Web Design**
Responsive web design adalah tampilan website yang bisa menyesuaikan dengan device pengguna. Device yang umumnya digunakan adalah laptop/PC, smartphone & tablet. <br>
Ada beberapa teknik untuk dapat menerapkan responsive web design ini diantaranya : <br>
- viewport <br>
Teknik yang pertama yaitu menambahkan viewport di HTML yang digunakan untuk  menetapkan area mana saja yang terlihat di situs web sekaligus menentukan skala kontennya.
```javascript
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
```

- Menggunakan max-width element
 max-width digunakan untuk mengatur batas lebar maksimal dari sebuah elemen, jadi apabila kita menyisipkan gambar di halaman website kita maka gambar tersebut lebarnya akan 100% menyesuaikan dengan ukuran layar.
 ```javascript
    <img style "max-width : 100%;" src="images/nature.jpg" alt="image">
```
 - Menggunakan CSS Unit
 Ada beberapa macam satuan dalam CSS unit : <br>
 <ol>
<li>em = mengikuti ukuran huruf element dia berada (parent)</li>
<li>rem = mengikuti ukuran huruf element root</li>
<li>vw = relative terhadap 1% dari lebar viewport</li>
<li>vh = relative terhadap 1% dari tinggi viewport</li>
<li>% = realtive terhadap parent.</li>
 </ol> <br>
 
 - Menggunakan Media Query
 Media query digunakan untuk membuat beberapa styles tergantung pada jenis device. Media query untuk responsive web design umumnya menggunakan 2 jenis media query, diantaranya : min-width & max-width. 
 Ada 2 cara dalam menggunakan media query, diantaranya : <br>
 <ol>
<li>Membuat file CSS berbeda untuk masing-masing device.</li>
<li>Menggabungkan 1 file CSS untuk setting stying berbagai device.</li>
 </ol>

 - Menggunakan Flexbox <br>
 Flexbox atau Flexible Box merupakan sebuah mode pengaturan atau konsep layout pada CSS yang digunakan untuk mengatur elemen atau container beserta item didalamnya pada halaman web. <br>
 Ada dua istilah penting saat belajar flexbox:
 <ol>
 <li><B>Container</B> adalah element yang membungkus dan mengatur tampilan dari element di dalamnya.</li>
 <li><B>Item</B> adalah element dalam container yang diatur tampilannya.</li>
 </ol>

 - Menggunakan Grids <br>
 Secara sederhana CSS Grid adalah CSS yang dapat membagi kolom pada website menjadi beberapa bagian sesuai yang diinginkan, baik secara horizontal maupun vertikal. Penggunaan CSS Grid bertujuan untuk mempermudah developer untuk membuat layout dari design yang telah dibuat.
 - Menggunakan Bootstrap <br>
 Bootstrap adalah framework HTML, CSS, dan JavaScript yang berfungsi untuk mendesain website responsive dengan cepat dan mudah. Framework open source ini diciptakan pada tahun 2011 oleh Mark Otto dan Jacob Thornton dari Twitter.<br>
 Kegunaan bootstrap diantaranya : <br>
 <ol>
<li>Menciptakan website Mobile Friendly</li>
Dengan adanya sistem grid, proses membuat website mobile friendly tak akan membutuhkan waktu lama.
<li>Memudahkan resize gambar</li>
Dengan menambahkan class .img-responsive ke gambar, maka gambar tersebut akan otomatis di-resize sesuai ukuran layar pengguna.
<li>Menambahkan elemen website tanpa ribet</li>
Bootstrap menyediakan berbagai elemen yang bisa langsung kita gunakan di website. Misalnya, navigasi, menu dropdown, thumbnail, dan sebagainya
<li>Membuat website lebih interaktif</li>
Bootstrap juga memungkinkan kita untuk menggunakan plugin custom seperti JQuery. Jadi, kita bisa menambahkan berbagai elemen interaktif ke website dengan mudah. Misalnya, popup, transisi, image carousel, dan sebagainya.
 </ol>
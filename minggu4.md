# **Ringkasan Materi Minggu 3 Bootcamp Coding**

# **Asynchronus ~ Fetch & Async Await** <br>
## **Async-Await**<br>
Async-await adalah salah satu cara untuk menangkap promise selain menggunakan then() & catch(). <br>
Berikut untuk implementasi penggunakan async-await : <br>

```javascript
    async function asyncNonton() {
    try {
        let result = await nonton("jalan")
        console.log(result);
    } catch (error) {
        console.log(error)
    }
}
asyncNonton()
```
Pada contoh diatas, pertama kita memiliki function dengan menambahkan async didepan function yang mana berfungsi untuk menjadikan function tersebut asynchronous, dan await berfungsi menunda eksekusi hingga proses asynchronous selesai. <br>

## **Fetch** <br>
Fetch adalah sebuah objek promise untuk mengambil data dari API yang di handle menggunakan promise atau async-await. Nah, lalu apa itu API? API adalah jembatan komunikasi ke server untuk mendapatkan data. <br>
Berikut untuk implementasi penggunaan fetch untuk mendapatkan data digimon: <br>

```javascript
    fetch("https://digimon-api.vercel.app/api/digimon")
    .then(result => result.json())
    .then(result => {
    console.log(result)
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
</ol>
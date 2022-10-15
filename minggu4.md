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

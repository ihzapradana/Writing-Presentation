# **Ringkasan Materi Minggu 6 Bootcamp Coding**

# **Intro to React** <br>
<B>React JS</B> adalah library JavaScript yang biasa digunakan saat membangun UI suatu website atau aplikasi web. React JS dibuat oleh tim enginer Facebook yang mereka gunakan pada sisi front-end. Banyak framework lain selain React JS seperti Vue JS, Angular, Next JS, Express JS, dan masih banyak yang lainnya. Mengapa kita harus menggunakan React JS? <br>
Kelebihan menggunakan React JS diantaranya : <br>
<ol>
<li>React JS membuat aplikasi Front-end menjadi lebih cepat walaupun harus menghandle berbagai data.</li>
<li>Dengan adanya konsep Modular pada React JS kita dapat membagi 1 tampilan pada website menjadi komponen-komponen kecil.</li>
<li>React JS dapat digunakan pada aplikasi berskala kecil hingga besar & kompleks.</li>
<li>Komunitas React JS di seluruh dunia sangatlah besar & kebanyakan perusahaan teknologi sudah menggunakan React JS.</li>
</ol>

Ketika kita ngoding React JS, kita pasti akan menjumpai JSX. JSX (Javascript XML) adalah syntax extension untuk Javascript yang dikembangkan untuk digunakan pada React JS. JSX perlu dicompile terlebih dahulu agar bisa menjadi Javascript. Jadi sebelum ditampilkan di browser, JSX harus dicompile menjadi Javascript. Nah, dengan JSX inilah kita dapat menggunakan HTML di dalam file extension Javascript. <br><br>
Setiap JSX hanya bisa memiliki 1 parent element saja. Jadi, jika kita mempunyai banyak komponen, maka komponen-komponen tersebut harus dibungkus dalam 1 element tag div atau bisa juga menggunakan tag fragment <>.<br><br>
Berikut untuk implementasinya : <br>
- Buat file baru bernama Home.js pada direktori src
```javascript
    import React from 'react'

    export const Home = () => {
    return (
        <div>
            <h1>Ini Tampilan Home</h1>
        </div>
    )
};
```
- Edit file App.js
```javascript
    import Home from "./Home";
    function app(params) {
    return (
        <div>
            <Home />
        </div>
    )
};
```
Kita sudah berhasil membuat element komponen text Ini Tampilan Home menggunakan React JS.
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
Kita sudah berhasil membuat element komponen text Ini Tampilan Home menggunakan React JS. <br><br>

# **Functional Component** <br>
Untuk dapat mendefinisikan komponen, langkah pertama yang harus kita lakukan adalah mengimpor Komponen Inti Teks React dan React Native, kemudian memulai komponen dengan sebuah fungsi yang diawali dengan huruf kapiital / capitalize.
```javascript
    import React from 'react';
    import { Text } from 'react-native';

    const Fungsi = () => {};
```
Di dalam komponen fungsi dikembalikan sebagai elemen react yang di dalamnya bisa kita isi dengan teks / tag-tag lain yang ingin ditampilkan di layar. Kemudian kita juga harus mengekspor komponen fungsi yang telah kita buat agar bisa diakses di komponen lain.<br>
```javascript
    const Fungsi = () => {
    return <h1>Hello, I am Himawan Ihza Pradana</h1>;
};

export default Fungsi;
```
<br>

# **Props and State** <br>
**Props** adalah singkatan dari Property. Pengertian mudahnya, props adalah data yang diaksihkan (pemberian data). Props umumnya digunakan untuk komunikasi data component dari parent komponent ke child component. Prop ini mirip seperti attribute jika dalam HTML, namun dalam pembuatannya jika dalam functional component maka prop ini adalah parameternya. <br>
Berikut untuk contoh penerapannya : <br>
```javascript
    // Membuat functional component
    function Ringkasan(props) {
        // Membaca component props
        let color = props.materi
    };
    // Render component dengan props
    <Ringkasan materi ="props & state" />
``` 
**State** adalah data private sebuah component atau pengertian mudahnya, state adalah data yang tinggal di component tersebut. Data ini hanya tersedia untuk component tersebut dan tidak bisa di akses dari component lain. Component dapat merubah statenya sendiri. Kesimpulannya State adalah sebuah object untuk menyimpan data pada React dan akan di render atau muat ulang ketika data mengalami perubahan.<br> <br>

# **Styling React JS** <br>
Untuk dapat memberikan styling saat kita menggunakan React, kita bisa menggunakan cara inline CSS seperti yang selama ini kita terapkan di HTML dan juga bisa external CSS. <br>
Berikut untuk penerapannya : <br>
```javascript
    // File jsx
    const Member = ({ name, age, info, imgUrl, nameColor }) => {
    return (
      <div className="profile-container">
        <img src={imgUrl} alt="" className="profile-img" />
        <div className="profile-info">
          <h2 style={{ color: nameColor }}>{name}</h2>
          <h3>{age} Tahun</h3>
          <p>{info}</p>
        </div>
      </div>
    );
  };
  
  export default Member;

    // File CSS
    .profile-img {
    width: 150px;
    height: 150px;
    overflow: hidden;
    border-radius: 100%;
    object-fit: cover;
    }

    .profile-info {
    margin-left: 20px;
    }

    .profile-container {
    margin-left: 100px;
    display: flex;
    }
```
<br><br>

# **Handling Events & Conditional Rendering** <br>
## **Handling Events**
Untuk dapat memberikan event dalam react, kita bisa memakai onClick, onChange, dan attribute-attribute lain seperti halnya yang kita gunakan di HTML JS biasanya. Nah, ketika kita ingin menerapkan sebuah event handler kita tidak bisa memakai varaibel biasa sebagai penampung, seperti set nilai awal = 0 ketika mau melakukan counter. Maka dari itu, ketika kita ingin menerapkan sebuah event handler dengan ada data yang mau ditampilkan / berubah kita harus menggunakan **state**. <br>
Berikut untuk contoh penerapannya dengan study case membuat tombol counter tamabah & kurang : <br>
```javascript
    import { useState } from "react";

    function Counter () {
    const [count, setCount] = useState(0) // untuk menampung counternya

    const increment = () => {
        setCount(count + 1)   // fungsi untuk meng-increment kan (ditambah 1)
    }

    const decrement = () => {
        setCount(count - 1) // fungsi untuk meng-decrement kan (dikurang 1)
    }

    return (
        <>
        {/* diberi event click */}
        <button onClick={decrement}>-</button>
        <span>{count}</span>
        <button onClick={increment}>+</button>
        </>
    )
    }

export default Counter;
```

## **Conditional Rendering** <br>
Adalah sebuah kondisi ketika terjadi sebuah event seperti di klik atau event yang lain. Untuk penerapannya, kita bisa menggunakan if else & operator ternary seperti halnya kita di Javascript biasanya, tinngal bermain logicnya saja mau di beri pengondisian seperti apa. <br>
Berikut untuk contoh penerapannya dengan study case user harus login terlebih dahulu sebelum dapat melakukan counting pada case di atas : <br>
```javascript
    import Counter from "./components/Counter";

    function App() {
    // untuk conditional renderingnya
    const [isLogin, setIsLogin] = useState(false);

    return (
        <div>
        {/* memunculkan button ketika belum login */}
        {!isLogin && <button onClick={() => setIsLogin(true)}>Login</button>}

        <br />

        {/* jika sudah login, akan munculkan counternya  */}
        {isLogin ? <Counter /> : <span>login dulu cuuuy...</span>}

        </div>
    );
    }

export default App;
```

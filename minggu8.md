# **Ringkasan Materi Minggu ke-3 Front-End Bootcamp**

# **React Context**
<B>React Context </B>bisa dibilang adalah pembaruan lebih lanjut dari react redux yang mana react context juga hadir untuk mengatasi permasalahan yang sama seperti react redux yaitu mengatasi props drilling (lempar-lemparan data dari parent ke child). React context digunakan untuk membuat data agar dapat diakses secara global.<br>
Untuk dapat menggunakan react context, kita harus melakukan beberapa hal, diantaranya : <br> 
- Menginstallnya terlebih dahulu dengan mengetikkan perintah "npm install react-context --save" pada terminal.
```javascript
    npm install react-context --save
```
- Kemudian menyediakan variabel untuk membuat contextnya dengan perintah "createContext()".
```javascript
    export const UserContext = createContext()
```
- Setelah itu kita buat provider di komponen parent. 
```javascript
    function UserProvider({children}) {
    const [user, setUser] = useState({
        name: "ihza",
        email: "ihza@gmail.com"
    })

    return (
        <UserContext.Provider value={{user, setUser}}>
        {children}
        </UserContext.Provider>
    )
    }

    export default UserProvider;
```
- Nah, dalam contoh kasus ini UserProvider adalah parent yang mempunyai child yaitu KeranjangCountProvider & App.
```javascript
    ReactDOM.createRoot(document.getElementById("root")).render(
    <UserProvider>
        <KeranjangCountProvider>
            <App />
        </KeranjangCountProvider>
    </UserProvider>
);
```
Setelah itu kita buat KeranjangCountProvider nya
```javascript
    import React, { createContext, useState } from 'react'

    export const KeranjangCountContext = createContext()

    function KeranjangCountProvider({children}) {
    const [keranjangCount, setKeranjangCount] = useState(0)

    //Karena KeranjangCountProvider punya child yaitu App, maka dikasih paramater berupa destrukturisasi children

    return (
        <KeranjangCountContext.Provider value={{keranjangCount, setKeranjangCount}}>
        {children}
        </KeranjangCountContext.Provider>
    )
    }

    export default KeranjangCountProvider;
```
- Kemudian kita buat App nya yang berisi komponen-komponen yang dibutuhkan. Di sini sebagai contoh saja saya panggil komponen Keranjang, ListProduct, & SummaryPembelian
```javascript
    import { useContext } from "react";
    import Keranjang from "./components/Keranjang";
    import ListProduct from "./components/ListProduct";
    import SummaryPembelian from "./components/SummaryPembelian";
    import { UserContext } from "./UserProvider";

    // Karena App mambutuhkan data yang ada di variabel UserContext dalam komponen UserProvider, maka perlu menggunakan keyword "useContext" dengan mengimportnya terleibh dahulu

    function App() {
    const { user } = useContext(UserContext); //Untuk dapat mengakses data di userContext

    return (
        <div className="App">
        <Keranjang />
        <br />

        <ListProduct />
        <SummaryPembelian />

        <h1>{user.name}</h1>
        </div>
    );
    }

    export default App;
```
<br>

# **React Context with useReducer**
React context dengan useReducer digunakan jika menemukan state yang ingin diubah dengan pengubahan yang kompleks, seperti menambah, menghapus, dan mengedit data. Dalam materi ini diajarkan cara mengombinasikan antara react context dengan reducer yang sebelumnnya sudah dibahas di materi redux.<br>
Berikut untuk contoh implementasinya dengan case membuat sebuah counter tambah & kurang : <br>
- Pertama seperti pada react context, kita buatkan dulu contextnya
```javascript
    export const CounterContext = createContext();
```
- Kemudian kita buat reducernya
```javascript
    function reducer(state, action) {
    switch (action.type) {
        //kondisi jika tambah
        case INCREMENT:
        return { count: state.count + 1 };
        //kondisi jika kurang
        case DECREMENT:
        return { count: state.count - 1 };
        default:
        return state;
    }
};
```
- Lalu kita buatkan komponen counter
```javascript
    function Counter() {
    const { 
        state, 
        increment, 
        decrement 
    } = useContext(CounterContext); //agar terhubung dengan Counter2Provider

    return (
        <div>
        <button onClick={decrement}>-</button>
        <span>{state.count}</span>
        <button onClick={increment}>+</button>
        </div>
    );
}
```

export default Counter;
- Kemudian kita buatkan provider untuk counternnya
```javascript
    function Counter2Provider({ children }) {
    const [state, dispatch] = useReducer(reducer, initialState);

    const increment = () => {
        dispatch({ type: INCREMENT });
    };

    const decrement = () => {
        dispatch({ type: DECREMENT });
    };

    return (
        <CounterContext.Provider value={{ state, increment, decrement }}>
        {children}
        </CounterContext.Provider>
    );
}

export default Counter2Provider;
```
<br>

# **React Testing ~ Jest & RTL**
Testing adalah melakukan uji coba terhadap aplikasi yang telah dibuat apakah sudha sesuai dengan ekspektasi atau belum. Terdapat 2 macam tipe testing, diantaranya : <br>
<ol>
<li><B>Manual Testing</B></li>
Yaitu testing yang dilakukan dengan melakukan pengecekan terhadap masing-masing fitur yang telah dibuat. Misalnya telah membuat fitur login, di cek apakah fitur login tersebut sudah jalan sesuai ekpektasi apa belum, apakah masih ada bug ketika user mengklik tombol loginnya, dll.
<li><B>Automation Testing</B></li>
Yaitu testing yang dilakukan olah kode porgram yang telah kita buat, kode program tersebut nantinya akan mengecek tiap fitur yang telah dibuat. Automation testing sendiri ada 3 macam, diantaranya : <br>
- <B>unit testing</B> = testing yang dilakukan pada bagian paling terkecil, seperti function.<br>
- <B>integration</B> = testing yang dilakukan dengan mengintegrasikan / menyambungkan dengan aplikasi / sistem lain, seperti database.<br>
- <B>end to end</B> = testing yang dilakukan terhadap software mulai dari awal sampai akhir mencakup experience dari user. Testing ini merupakan testing yang membutuhkan banyak biaya karena bisa dibilang testing ini adalah testing yang kompleks / testing yang tidak bisa dilakukan oleh programmer sendiri, tidak seperti unit testing yang masih bisa dilakukan oleh programmer sendiri.
</ol>
Berikut untuk contoh implementasi menggunakan Jest : <br>

```javascript
    //app.js
    function sum(x,y) { //untuk melakukan penjumlahan
    return x + y
    };

    function cekGG(n) { //untuk mengecek genap
        if (n % 2== 1) return 'ganjil'
        return 'genap'
    }

    function cekTF(n) { //untuk mengecek true/false dari ganjil/genap
        if (n % 2== 1) return 'ganjil'
        return 'genap'
    }

    module.exports = {sum, cekGG, cekTF}; 

    //app.test.js
    const {sum, cekGG, cekTF} = require('./app');

    test('menjumlahkan angka dengan sum()', () => { //Untuk mengecek fungsi penjumlahan
        expect(sum(1,1)).toBe(2),
        expect(sum(1,2)).toBe(3)
    })

    test('cek ganjil / genap', () => { //Untuk mengecek fungsi GG (ganjil/genap)
        expect(cekGG(1)).toBe('ganjil'),
        expect(cekGG(2)).toBe('genap')
    })

    test('cek ganjil / genap', () => { //Untuk mengecek fungsi TF (true/flase)
        expect(cekTF(1)).toBeTruthy(),
        expect(cekTF(2)).toBeFalsy()
    });
```
Berikut adalah contoh implementasi menggunakan RTL (React Testing Library)<br>
```javascript
    //Counter.js
    import React, { useState } from 'react'

    function Counter() { //Membuat komponen Counter
    const [count, setCount] = useState(0)

    return (
        <div>
        <button onClick={() => setCount(count-1)}>-</button>
        <span>{count}</span>
        <button onClick={() => setCount(count+1)}>+</button>
        </div>
    )
    }

    export default Counter;

    //Counter.test.js
    import { fireEvent, render, screen } from '@testing-library/react';
    import Counter from './Counter';

    test("render counter", () => {
    render(<Counter/>) //untuk merender komponen Counter
    const decrementBtn = screen.getByText("-") //untuk mendapatkan text "-"
    const count = screen.getByText("0") //untuk mendapatkan text "0"
    const incrementBtn = screen.getByText("+") //untuk mendapatkan text "+"

    expect(decrementBtn).toBeInTheDocument() //untuk mengecek apakah "-" itu ada
    expect(count).toBeInTheDocument() //untuk mengecek apakah "0" itu ada
    expect(incrementBtn).toBeInTheDocument() //untuk mengecek apakah "+" itu ada
    })

    test('click increment button', () => { //function untuk melakukan testing
    render(<Counter/>)
    const incrementBtn = screen.getByText("+")
    const count = screen.getByText("0")

    expect(count.textContent).toBe("0")

    //untuk mengecek apakah ketika diklik "+" yang awalnya 0 akan bertambah jadi 1
    fireEvent.click(incrementBtn)
    expect(count.textContent).toBe("1")
    });
```
Dalam melakukan testing juga terdapat yang namanya TDD (Test Driven Development). Pada umumnya testing dilakukan setelah fitur selesai dibuat, proses ini terjadi pada development biasa. Sedangkan pada proses TDD, testing dilakukan lebih dulu sebelum membuat fitur. Dalam TDD, terdapat sebuah lifecycle diantaranya yaitu :
- Red zone (Test Fails) = berisi sebuah ekspektasi (masih belum ada code program, hanya ekspektasi saja).
- Green zone (Test Passess)= realasasi dari ekspektasi tersebut (proses pembuatan code program).
- Blue zone (Refactor) = tahap efisiensi dari code program, seprti membuat codingan yang simple, mudah dimengerti, dan rapi. Intinya untuk membuat code yang telah dibuat sebelumnya agar lebih rapi & efisien.
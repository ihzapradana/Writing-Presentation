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
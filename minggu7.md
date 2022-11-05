# **Ringkasan Materi Minggu ke-2 Front-End Bootcamp**

# **React ~ Prop Types** <br>
<B>Prop Types</B> merupakan sebuah library yang dapat membantu untuk memeriksa tipe data props yang kita kirim agar sesuai dengan ekspektasi kita. Untuk dapat menggunakan PropTypes ini, terlebih dahulu kira harus menginstallnya dengan mengetikkan perintah "npm install prop-types". Kemudian meng-importnya dengan menuliskan code "import PropTypes from 'prop-types';" <br>
Berikut untuk contoh penerapannya : <br>

```javascript
    import PropTypes from "prop-types";

    const MotorInfo = (props) => {
    return (
        <>
        <h2>Name : {props.char}</h2>
        <h2>Tahun : {props.tahun}</h2>
        <h2>Detai info : {props.detail}</h2>
        </>
    );
    };

    MotorInfo.propTypes = {
        char : PropTypes.string,
        tahun : PropTypes.number,
        detail : PropTypes.string
    }

    MotorInfo.propTypes = {
        //tipe data string
        name: PropTypes.string,
        //tipe data number
        age: PropTypes.number,
        //tipe data bebas & harus diisi
        name: PropTypes.any.isRequired,
        // memberikan pilihan tipe data / salah satu
        age: PropTypes.oneOfType([PropTypes.string, PropTypes.number]),
        //tipe data array
        name: PropTypes.array,
        // mengecek value dari props
        name: PropTypes.arrayOf(PropTypes.number),
        // array dengan memberikan opsi terhadap berbagai tipe data
        age: PropTypes.arrayOf(PropTypes.oneOfType([PropTypes.number, PropTypes.string])),
        // tipe data object
        info: PropTypes.object,
    };
```
<br><br>

# **React Router 6** <br>
Jika kita ingin berganti dari satu halaman ke halaman yang lainnya dalam website diperlukan suatu proses routing. Perpindahan halam tersebut diantaranya seperti halaman Home, About Me, Contact Us, dan halaman-halaman lainnya. Routing sendiri adalah proses pemetaan antara sebuah URL ke dalam sebuah halaman yang terdapat konten / UI (User Interface) sesuai dengan URL yang dituju. Untuk dapat membuat routing kita membutuhkan library tambahan karena tidak secara langsung tersedia. Library tersebut yaitu "react-router-dom". Untuk dapat menggunakan reacr-router, terlebih dahulu kita harus mengimport BorwserRouter & Route yang nantinya tag tersebut akan dipakai sebagai pembungkus terluar. <br><br>
```javascript
    import { Routes, Route, Link } from "react-router-dom";
    import { BrowserRouter } from "react-router-dom";
```

Dalam penggunaanya, react-router secara garis besar hampir mirip dengan HTML biasanya hanya saja sedikit ada perbedaan dalam penerapannya. Kalau dalam HTML ketika kita hendak menyisipkan link / file HTML untuk berpindah halaman kita menggunakan tag "anchor", sedangkan dalam react-router menggunakan tag "Link". Selain tag "Link" untuk dapat berindah halaman, terdapat salah satu Hook yang bernama useNavigate() yang sebenarnya juga sama seperti tag "Lin" untuk berpindah halaman, namun useNavigate lebih disarankan karena lebih kompatibel. <br><br>
```javascript
    <nav>
        <Link to={"/"}>Home |</Link>
        <Link to={"/about"}>About</Link>
    </nav>
```

Selain itu ada juga yang namanya outlet yang digunakan untuk memanggil anak-anak dari induk. Misalnya kita punya sebuah halam about yang di dalamnya ada halaman about teachers & about students. Nah, halaman about teachers & students merupakan anak dan halaman about merupakan induknya. <br>
```javascript
    import { Outlet, Link } from "react-router-dom";

    const About = () => {
    return (
        <>
        <Outlet />
        <Link to={"student"}>About Student |</Link>
        <Link to={"teacher"}>About Teacher</Link>
        </>
    );
    };
    
    export default About;
```

Lalu bagaimana jika kita ingin menampilkan suatu halaman sebagai halaman pertama yang ingin ditampilkan? jawabannya adalah dengan menambahlan attribute index di dalam tag "Route" di file halaman yang ingin kita jadikan halaman pertama yang ingin ditampilkan.
```javascript
    <Routes>
        <Route path="/" element={<Home />} />
        {/* route params*/}
        <Route path="/detail/:id" element={<Detail />} />

        {/* penggunaan nested route */}
        <Route path="/about" element={<About />}>
          <Route path="student" element={<AboutStudent />} />
          <Route path="teacher" element={<AboutTeacher />} />
          {/* index digunakan agar element AboutSchool langsung ditampilkan pertama kali ketika page about dibuka */}
          <Route index element={<AboutSchool />} />
        </Route>
        {/* tambahkan path="*" untuk menampilkan halaman yg tidak ditemukan. case nya adalah ketika user mengakses path tertentu yang tidak terdaftar di routingan yang kita miliki*/}
        <Route path="*" element={<NotFound />} />
    </Routes>
```
<br><br>

# **State Management ~ Redux** <br>
<B>Redux </B>adalah sebuah aplikasi state management. State management adalah cara untuk memfasilitasi komunikasi dan berbagai data lintas komponen. Redux berfungsi untuk melakukan perubahan state yang dibutuhkan oleh setiap fungsional yang ada di suatu aplikasi. Tujuan redux untuk mengatasi props drilling (props nya di oper-oper). Untuk membuat perubahan tersebut, Redux memiliki tiga komponen utama yaitu action, reducer, dan store. Langkah-langkah dalam menggunakan redux dalam react yaitu : <br>
<ol>
<li>Buat Store</li>

```javascript
    import { createStore } from 'redux'
    import keranjangReducer from '../reducer/keranjangReducer'

    const store = createStore(keranjangReducer)

    export default store;
```
<li>Buat Reducer</li>

```javascript
    const initialState = {
    totalKeranjang: 0,
    };
  
  function keranjangReducer(state = initialState, action) {
    console.log(action);
  
    switch (action.type) { 
      default:
        return state;
    }
  };
  
  export default keranjangReducer;
```
<li>Buat Provider (untuk membari tahu bahwa storenya sudah tersedia</li>

```javascript
    import { Provider } from 'react-redux';

    ReactDOM.createRoot(document.getElementById('root')).render(
        <Provider store={store}>
            <App />
        </Provider>
    );
```
<li>Ambil Data dari Store menggunakan useSelector()</li>

```javascript
    import { useSelector } from 'react-redux'

    function Keranjang() {
    const {totalKeranjang} = useSelector(state => state)


    return (
        <div>
        <span>Keranjang</span>
        <span> {totalKeranjang}</span>
        </div>
    )
    }

    export default Keranjang;
```
<li>Ubah Data di Store menggunakan dispatch(action)</li>

```javascript
    import { useDispatch } from "react-redux";

    export function incrementKeranjang(payload) {
    return {
        type: INCREMENT_KERANJANG,
        payload
    }
    }

    export function decrementKeranjang(payload) {
    return {
        type: DECREMENT_KERANJANG,
        payload
    }
    }

    function Counter() {
    const dispatch = useDispatch(); //untuk meng-trigger action agar mengubah data di store
    const [count, setCount] = useState(0);

    const increment = () => {
        dispatch(incrementKeranjang())
        setCount(count + 1);
    };

    const decrement = () => {
        dispatch({
        type: "DECREMENT_KERANJANG"
        })
        setCount(count - 1);
    };
```
Dalam mengirimkan action menggunakan dispatch, kita juga bisa menampung data / memberikan info tambahan dalam aksi itu menggunakan "payload". Caranya adalah dengan menjadikan "payload" tersebut sebagai parameter dalam function action nya. Kemudian saat function action dengan parameter payload tersebut dipanggil function lain yang menggunakan dispatch, kita ganti parameter function action itu dengan data / pesan sesuai keinginan kita. <br>
Berikut untuk contoh penerapannya : <br>
```javascript
    //payload dijadikan sebagai parameter dalam function action yang mengembalikan tipe dari masing-masing action
    export const INCREMENT_KERANJANG = "INCREMENT_KERANJANG"
    export const DECREMENT_KERANJANG = "DECREMENT_KERANJANG"

    export function incrementKeranjang(payload) {
    return {
        type: INCREMENT_KERANJANG,
        payload
    }
    }

    export function decrementKeranjang(payload) {
    return {
        type: DECREMENT_KERANJANG,
        payload
    }
};
    //Kemudian saat function action dengan parameter payload tersebut dipanggil function lain yang menggunakan dispatch, kita ganti parameter function action itu dengan data / pesan sesuai keinginan. Misal menampilkan pesan "oke. ditambah / dikurangi"
    function Counter() {
    const dispatch = useDispatch();
    const [count, setCount] = useState(0);

    const increment = () => {
        dispatch(incrementKeranjang('oke, ditambah'))
        setCount(count + 1);
    };

    const increment = () => {
        dispatch(decrementKeranjang('oke, dikurangi'))
        setCount(count - 1);
    };

    return (
        <>
        <button onClick={decrement}>-</button>
        <span>{count}</span>
        <button onClick={increment}>+</button>
        </>
    );
};
```

</ol>
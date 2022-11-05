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



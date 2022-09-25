
#**Ringkasan Materi Minggu 1 Bootcamp Coding**

# **Unix Command Line**<br>
- **Shell** adalah program yang digunakan untuk berkomunikasi atau memerintahkan sistem. <br>
- **Command Line Interface** adalah jenis shell yang berbasis teks.
- **Terminal Emulator** adalah aplikasi untuk mengakses CLI.<br>
- <B>Filesystem</B>, yaitu mengatur bagaimana data disimpan di dalam sebuah system. Sistem operasi Windows & Unix-like menyusun file & direktory menggunakan struktur yang bentuknya mirip tree.

## Berikut adalah command-command yang digunakan : <br>
- <B>pwd</B>, yaitu command untuk mengetahui lokasi kita berada. <br>
- <B>ls</B>,  adalah coomand untuk melihat isi file direktory. <br>
sedangkan <B>ls -a</B> adalah command untuk melihat file yang diembunyikan.
- <B>cd</B>,  adalah comand untuk pindah file atau direktory.<br>
- <B>head</B>, adalah command untuk melihat beberapa line awal dari sebuah file text.<br>
- <B>tail</B>, adalah command untuk melihat beberapa line terakhir dari sebuah file text.<br>
-<B>cat</B>, adalah command untuk melihat semua isi file.<br>
- <B>mkdir</B>, adalah command untuk membuat folder baru<br>
-<B>touch</B>, adalah command untuk membuat sebuah file.<br>
-<B>cp</B>, adalah command untuk meng-copy file atau direktory.
-<B>mv</B>, adalah command untuk memindah dan me-rename file/direktory.<br>
-<B>rm</B>, adalah command untuk menghapus file.<br>
-<B>rm -d / rm -R</B>, adalah command untuk menghapus direktory.<br><br>

#**Git & Github** <br>
- <B>Git</B> adalah tools untuk para progrmmer yang digunakan sebagai <em> version control system</em>, yaitu untuk mencatat setiap perubahan pada file (termasuk code yang kita buat) pada suatu proyek yang bisa dikerjakan secara individu maupun tim. Jadi, Git merupakan aplikasi yang dapat melacak setiap perubahan yang terjadi pada suatu folder / file.<br>
- <B>Github</B> merupakan layanan cloud yang berguna untuk menyimpan dan mengelola sebuah project yang dinamakan repository (repo git).
- <B>Mengapa perlu Git & Github?</B> tujuannya adalah agar kita bisa bekerja dalam sebuah tim dan bisa berkolaborasi mengerjakan sebuah proyek tanpa harus repot copy paste, serta kita juga tidak perlu menunggu rekan satu tim untuk menyelesaikan suatu program dahulu untuk berkolaborasi.<br>

- <B>Alur kerja Git</B> <br>
<em>Pertama</em>, kita bisa set up terlebih dahulu dengan melakukan git config --global user.name "Himawan Ihza", kemudian melakukan git config --global user.email himawanihza@gmail.com <br>
<em>Kedua</em>, membuat repository dengan melakukan : git init (nama repo), jika folder sudah ada sebelumnya maka lakukan : git init . <br>
<em>Ketiga</em>, buat file codingan pada direktory yang telah dibuat. Kemudian lakukan : git status (untuk melacak perubahan yang terjadi).<br>
<em>Keempat</em>, lakukan : git add . (untuk mengubah status "untracked & unmodified" menjadi "Modified".<br>
<em>Kelima</em>, lakukan : git commit -m "pesan" (untuk menyimpan perubahan pada version control).<br>
Langkah-langkah tersebut akan terus diulang jika nanti terdapat revisi dalam proyek kita. apabila kita ingin melihat catatan log dari revisi-revisi yang telah kita lakukan kita dapat melihatnya dengan melakukan : <B>git log</B> <br>
Selanjutnya ada <B>git checkout</B> yang digunakan untuk pindah commit an / pindah branch (cabang) dan membatalkan perubahan saat belum stagged & belum commit.<br>
Kemudian ada <B>git reset</B> untuk membatalkan perubahan saat sudah stagged & belum commit. <br>
Kemudian ada <B>git revert</B> untuk membatalkan semua perubahan yang ada tanpa menghapus commit terakhir. Jika kita menggunakan git reset, maka commit yang terakhir akan hilang.

- <B>Membuat repository Git</B> <br>
<em>Pertama</em>, buka github.com dan login / daftar<br>
<em>Kedua</em>, klik icon (+) yang ada di pojok kanan atas lalu pilih "new repository" atau klik tombol "new" berwarna hijau di kiri atas. kemudian beri nama repository yang mau kita buat dan klik "create repository".

- <B>Melakukan commit di git</B> <br>
Untuk melakukan commit di git, kita cukup menggunakan perintah <em>git commit -m "pesan"</em>

- <B>Mempublish aplikasi ke github</B> <br>
Untuk mempublish aplikasi yang telah kita buat di github, perintah-perintahnya bisa kita copy paste dari repository yang telah kita buat tadi. : <br>
<em>Pertama</em>, lakukan : git remote add origin https://github.com/ihzapradana/Writing-Presentation.git .<br>
<em>Kedua</em>, lakukan git push -u origin main

- <B>Melakukan cloning github ke local</B> <br>
Untuk melakukan clonning github ke local, saya biasanya menggunakan cara : <br>
<em>Pertama</em>, masuk di file explorer kemudian pilih di folder / lokasi mana kita akan menyimpan file hasil clone nantinya.<br>
<em>Kedua</em>, jika sudah berada di folder tersebut klik kotak atas yang berisi informasi lokasi kita saat ini, kemudian klik "delete" dan ketik "cmd". Maka akan muncul tampilan command prompt.<br>
<em>Ketiga</em>, ketik git clone https://github.com/ihzapradana/Writing-Presentation.git . Lalu tekan enter<br>
<em>Proses clonning github selesai.</em> <br>

#**HTML Dasar** <br>
- <B>Peran HTML pada web development</B> <br>
HTML adalah singkatan dari Hypertext Markup Language. HTML digunakan untuk menampilkan konten pada browser. HTML bukanlah bahasa pemrograman, artinya HTML tidak bisa dinamis mengolah data.

- <B>Menggunakan tools pendukung dalam menggunakan HTML</B> <br>
Ada 2 tools utama yang harus dipersiapkan untuk membuat HTML, diantaranya : <br>
<ol>
<li><B>Browser</B></li>
Untuk browser bisa menggunakan Google Chrome / Microsoft Edge, tergantung setelan default dari komputer masing-masing. 
<li><B>Code Editor</B></li>
Untuk code editor yang sering dipakai dalam pembelajaran di skilvul ini adalah memakai visual studio code.
</ol>

- <B>Membuat HTML sederhana</B> <br>
Pada pembelajaran di minggu pertama program basic coding ini praktik membuat HTML sederhananya yaitu membuat sebuah halaman profile sederhana yang berisikan foto, list media sosial dan sebuah form input email.

- <B>Menjalankan HTML secara manual & menggunakan live server dari VS Code</B> <br>
Setelah kita membuat sebuah halaman profile sederhana, selanjutnya kita lihat hasilnya di browser dengan menggunakan fitur live server dari vs code. Jika tidak menggunakan fitur tersebut sebenarnya kita masih bisa melihat hasilnya di browser, namun jika ada perubahan dalam HTML kita harus melakukan refresh website terlebih dahulu.

- <B>Implementasi tag HTML yang populer</B> <br>
Pada pembelajaran di minggu pertama program basic coding ini praktik membuat HTML sederhananya yaitu membuat sebuah halaman profile sederhana yang berisikan nama (menggunakan tag H1), foto (menggunakan tag img <img>), list media sosial (menggunakan tag order list & list) dan sebuah form input nama &email (menggunakan tag form bertipe kan email).

- <B>Implementasi semantic HTML</B> <br>
Pada pembelajaran di minggu pertama program basic coding ini praktik membuat HTML sederhananya yaitu membuat sebuah halaman profile sederhana yang berisikan nama (menggunakan tag H1) , foto (menggunakan tag <img>, list media sosial(menggunakan tag order list & list) yang dibungkus dalam tag <section> dengan id = profile dan sebuah form input nama & email yang dibungkus dalam tag <section> dengan id = contact-me

- <B>Mempublish website sampai tahap deployment</B>
Untuk dapat mempublish website yang telah kita buat ke Netlify yaitu dengan melakukan :<br>
<em>Pertama</em>, buka website netlify.com, kemudian login menggunanakan akun github. <br>
<em>Kedua</em>, pilih menu sites dan klik "Add new site", kemudian pilih "Import existing project", Kemudian pilih Github.<br>
<em>ketiga</em>, pilih project yang mau di deploy, kemudian kilk "Deploy site".<br>
Proses deployment website sudah selesai dan website yang telah kita buat tadi bisa diakses oleh orang lain :) <br>

#**CSS Dasar** <br>
- <B>Peran CSS pada web development</B> <br>
- <B>Cara menyisipkan CSS ke dalam HTML</B> <br>
- <B>Menggunakan syntax dasar CSS</B> <br>
- <B>Menerapkan styling CSS pada sebuah halaman HTML</B><br>
- <B>Menggunkan metode responsive web design menggunakan CSS</B> <br>
- <B>Menggunakan Flexbox</B>


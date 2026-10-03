# Lab2Web - Praktikum HTML Lanjutan

Repositori ini dibuat untuk memenuhi tugas Praktikum Pemrograman Web.

## Informasi Mahasiswa
* **Nama:** Nabila Lutfia Sari
* **NIM:** 312510040
* **Kelas:** I253A
* **Program studi:** Teknik Informatika
* **Dosen Pengampu:** Agung Nugroho, S.Kom., M.Kom.
* **Kampus:** Universitas Pelita Bangsa 

Panduan Screenshot Tugas
Simpan semua file tangkapan layar (screenshot) di dalam folder screenshots/ dengan format nama angka (1.png sampai 7.png) sesuai tabel berikut:

No File	Aplikasi / Lokasi	Yang Harus Di-Screenshot
1.png	Browser (index.html)	Tampilan tabel data nilai mahasiswa yang memiliki header (<thead>), baris data (<tbody>), dan footer (<tfoot>) dengan colspan.
2.png	Browser (index.html)	Tampilan form registrasi mahasiswa lengkap dengan input teks, email, password, tanggal lahir, umur, radio button jenis kelamin, checkbox keahlian, dropdown program studi, dan textarea alamat.
3.png	Browser (index.html)	Uji coba validasi form dasar: saat kolom required dikosongkan lalu tombol submit diklik, muncul pesan peringatan validasi dari browser.
4.png	Browser (index.html)	Tampilan pemutar multimedia audio dan video yang berhasil memuat file dari folder media/.
5.png	Browser (biodata.html)	Tampilan bagian atas proyek mini: header semantik, navigasi, dan tabel biodata diri mahasiswa (NIM, Nama, Kelas, Prodi).
6.png	Browser (biodata.html)	Tampilan bagian form pembaruan biodata mahasiswa dengan validasi atribut required.
7.png	Browser (biodata.html)	Tampilan bagian bawah proyek mini: pemutar multimedia video/audio profil, aside, dan footer halaman.
Struktur Direktori Proyek
Lab2Web/
├── index.html
├── biodata.html
├── media/
│   ├── audio.mp3
│   └── video.mp4
├── screenshots/
│   ├── 1.png
│   ├── 2.png
│   ├── 3.png
│   ├── 4.png
│   ├── 5.png
│   ├── 6.png
│   └── 7.png
└── README.md
Langkah-Langkah Pengerjaan Praktikum
1. Membuat dan Mengembangkan Tabel HTML
Tabel digunakan untuk menampilkan data dalam bentuk baris dan kolom. Pada tahap ini dibuat tabel data nilai mahasiswa yang terstruktur menggunakan:

<table>: Membungkus seluruh elemen tabel.
<caption>: Memberikan judul keterangan pada tabel.
<thead>: Menampung baris header kolom dengan tag <th>.
<tbody>: Menampung kumpulan data utama mahasiswa dengan tag <td>.
<tfoot>: Menampung baris ringkasan di bagian bawah.
Atribut colspan="4": Menggabungkan empat sel kolom menjadi satu pada baris nilai rata-rata.
Potongan kode tabel pada index.html:

<table border="1" cellpadding="8" cellspacing="0">
    <caption>Daftar Nilai Praktikum Pemrograman Web</caption>
    <thead>
        <tr>
            <th>No</th>
            <th>NIM</th>
            <th>Nama Mahasiswa</th>
            <th>Program Studi</th>
            <th>Nilai</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>1</td>
            <td>312510054</td>
            <td>Angger Cakra Wicaksono</td>
            <td>Teknik Informatika</td>
            <td>95</td>
        </tr>
        <tr>
            <td>2</td>
            <td>312510001</td>
            <td>Andi Pratama</td>
            <td>Teknik Informatika</td>
            <td>85</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="4" align="center"><b>Nilai Rata-rata</b></td>
            <td><b>90</b></td>
        </tr>
    </tfoot>
</table>
Screenshot Hasil:
Langkah 1 - Tabel Data Mahasiswa

2. Membuat Form Registrasi dengan Berbagai Jenis Input
Membuat form registrasi mahasiswa menggunakan tag <form> yang menampung beragam kontrol input data:

type="text" untuk nama lengkap.
type="email" untuk alamat email.
type="password" untuk kata sandi.
type="date" untuk pemilihan tanggal lahir.
type="number" untuk umur dengan batas nilai menggunakan min dan max.
type="radio" untuk pilihan tunggal jenis kelamin.
type="checkbox" untuk pilihan banyak pada keahlian/skill.
<select> dan <option> untuk menu pilihan dropdown program studi.
<textarea> untuk isian alamat yang membutuhkan beberapa baris teks.
Hubungan label dengan kontrol input dibuat menggunakan atribut for yang merujuk ke atribut id pada input terkait.
Potongan kode form pada index.html:

<form action="#" method="post">
    <label for="nama">Nama Lengkap:</label><br>
    <input type="text" id="nama" name="nama" required minlength="3"><br><br>

    <label for="email">Alamat Email:</label><br>
    <input type="email" id="email" name="email" required><br><br>

    <label>Jenis Kelamin:</label><br>
    <input type="radio" id="laki" name="jk" value="L" required>
    <label for="laki">Laki-laki</label>
    <input type="radio" id="perempuan" name="jk" value="P">
    <label for="perempuan">Perempuan</label><br><br>

    <label for="prodi">Program Studi:</label><br>
    <select id="prodi" name="prodi" required>
        <option value="">-- Pilih Program Studi --</option>
        <option value="TI">Teknik Informatika</option>
        <option value="SI">Sistem Informasi</option>
    </select><br><br>

    <label for="alamat">Alamat Lengkap:</label><br>
    <textarea id="alamat" name="alamat" rows="4" cols="45" required></textarea><br><br>

    <button type="submit">Daftar Sekarang</button>
    <button type="reset">Reset Form</button>
</form>
Screenshot Hasil:
Langkah 2 - Form Registrasi

3. Menerapkan Validasi Form Dasar HTML
Validasi formulir dilakukan langsung di sisi peramban (client-side) menggunakan atribut bawaan HTML tanpa perlu JavaScript:

required: Memastikan input wajib diisi sebelum form dapat dikirim.
minlength: Membatasi jumlah karakter minimal yang harus dimasukkan (contoh pada nama dan password).
min dan max: Menentukan batas nilai numerik terendah dan tertinggi (contoh umur: 17 sampai 60 tahun).
type="email": Secara otomatis memeriksa pola penulisan format email (harus mengandung karakter @ dan domain).
Saat tombol submit diklik dalam kondisi kolom wajib belum terisi, browser secara otomatis menampilkan pesan kesalahan validasi.

Screenshot Hasil:
Langkah 3 - Validasi Form

4. Menambahkan Elemen Multimedia (Audio & Video)
Memasukkan media audio dan video lokal ke halaman web dengan meletakkannya di dalam folder media/:

<audio controls>: Menampilkan pemutar audio lengkap dengan tombol play, pause, volume, dan timeline.
<video controls width="480">: Menampilkan pemutar video beresolusi terukur yang mendukung kontrol pemutaran.
Tag <source> di dalamnya menentukan path file sumber beserta MIME type-nya (audio/mpeg dan video/mp4).
Potongan kode multimedia:

<audio controls>
    <source src="media/audio.mp3" type="audio/mpeg">
    Browser tidak mendukung pemutar audio.
</audio>

<video controls width="480">
    <source src="media/video.mp4" type="video/mp4">
    Browser tidak mendukung pemutar video.
</video>
Screenshot Hasil:
Langkah 4 - Multimedia

5. Menerapkan Struktur Semantic HTML
Halaman web disusun dengan elemen semantik HTML5 untuk menggantikan ketergantungan pada tag non-semantik <div>:

<header>: Memuat kepala dokumen atau judul utama halaman.
<nav>: Memuat daftar menu tautan navigasi utama.
<main>: Membungkus seluruh konten pokok halaman web.
<section>: Membagi konten ke dalam bab atau bagian bahasan tematik.
<article>: Membungkus bagian konten mandiri yang memiliki arti utuh (seperti artikel berita atau modul pemutar media).
<aside>: Memuat informasi tambahan/pelengkap yang terpisah dari konten pokok.
<footer>: Memuat kaki halaman yang berisi informasi hak cipta dan data mahasiswa.
6. Proyek Mini: Halaman Biodata Mahasiswa (biodata.html)
Sebagai proyek mini integrasi, dibuat file baru bernama biodata.html yang menggabungkan seluruh konsep yang dipelajari:

Struktur Semantic HTML yang rapi (<header>, <nav>, <main>, <section>, <aside>, <footer>).
Tabel informasi data diri mahasiswa lengkap (NIM, Nama, Kelas, Program Studi, Fakultas, Kampus).
Formulir pembaruan biodata mahasiswa dengan validasi wajib isi (required).
Elemen pemutar video dan audio profil mahasiswa.
Potongan kode biodata.html:

<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <title>Biodata Mahasiswa - Proyek Mini</title>
</head>
<body>
    <header>
        <h1>Halaman Biodata Mahasiswa</h1>
        <p>Proyek Mini Praktikum 2 - Pemrograman Web</p>
    </header>

    <nav>
        <a href="index.html">Kembali ke Beranda (index.html)</a> |
        <a href="#biodata">Data Diri</a> |
        <a href="#form">Form Pembaruan Biodata</a>
    </nav>
    <hr>

    <main>
        <section id="biodata">
            <h2>Data Diri Mahasiswa</h2>
            <table border="1" cellpadding="8" cellspacing="0">
                <tr><th>Parameter</th><th>Keterangan Lengkap</th></tr>
                <tr><td><b>NIM</b></td><td>312510054</td></tr>
                <tr><td><b>Nama Lengkap</b></td><td>Angger Cakra Wicaksono</td></tr>
                <tr><td><b>Program Studi</b></td><td>Teknik Informatika</td></tr>
            </table>
        </section>
        ...
    </main>
</body>
</html>
Screenshot Hasil Proyek Mini:

Tabel Biodata Diri:
Langkah 5 - Tabel Biodata
Formulir Biodata Mahasiswa:
Langkah 6 - Form Biodata
Multimedia Profil & Footer:
Langkah 7 - Multimedia Biodata
Jawaban Pertanyaan Evaluasi Modul
1. Apa fungsi <table>, <tr>, <th>, dan <td>?

<table>: Berfungsi sebagai pembungkus utama yang mendefinisikan seluruh area tabel.
<tr> (Table Row): Berfungsi membuat baris horizontal baru di dalam tabel.
<th> (Table Header): Berfungsi membuat sel judul kolom yang secara default tampil tebal (bold) dan berada di tengah (center).
<td> (Table Data): Berfungsi membuat sel data standar yang berisi nilai atau informasi baris bersangkutan.
2. Apa perbedaan <th> dan <td>?
Perbedaan mendasarnya terletak pada fungsi semantik dan tampilan visual bawaannya. Elemen <th> digunakan khusus untuk sel header/judul kolom sehingga teksnya otomatis tercetak tebal dan rata tengah, serta dibaca sebagai label kolom oleh pembaca layar (screen reader). Sedangkan <td> digunakan untuk sel data konten biasa dengan teks yang rata kiri dan berbobot normal.

3. Apa fungsi colspan pada tabel?
Atribut colspan (column span) berfungsi untuk menggabungkan dua atau lebih sel kolom horizontal yang bersebelahan menjadi satu sel tunggal pada baris yang sama. Contohnya digunakan pada baris <tfoot> untuk menggabungkan kolom nomor, NIM, nama, dan prodi menjadi satu tempat tulisan "Nilai Rata-rata".

4. Apa fungsi <form> dalam HTML?
Tag <form> berfungsi sebagai wadah untuk menampung berbagai elemen kontrol input (seperti input teks, radio, checkbox, select, button) yang memungkinkan pengguna memasukkan data ke halaman web, untuk kemudian diproses di sisi klien atau dikirimkan ke server melalui metode HTTP (GET atau POST).

5. Apa perbedaan radio button dan checkbox?

Radio button (type="radio"): Digunakan ketika pengguna hanya diperbolehkan memilih satu opsi tunggal dari serangkaian pilihan yang berada dalam satu kelompok nama atribut (name) yang sama (contoh: jenis kelamin Laki-laki atau Perempuan).
Checkbox (type="checkbox"): Digunakan ketika pengguna dapat memilih beberapa opsi sekaligus (bisa memilih nol, satu, atau lebih dari satu pilihan) dalam kategori yang sama (contoh: daftar keahlian/skill).
6. Mengapa <label> sebaiknya terhubung dengan id input melalui atribut for?
Menghubungkan atribut for pada label dengan atribut id pada elemen input sangat penting karena:

Aksesibilitas (Accessibility): Membantu pembaca layar (screen reader) mengidentifikasi dan membacakan label yang benar saat pengguna tunanetra memfokuskan kursor ke kolom input.
Kegunaan (Usability): Memperluas area klik. Saat pengguna mengklik teks pada label (misal label teks radio button atau checkbox), kontrol input terkait akan otomatis terpilih/aktif meskipun pengguna tidak mengklik tepat pada bulatan atau kotaknya.
7. Apa perbedaan <textarea> dengan input type text?

Input type="text": Hanya dapat menerima masukan teks satu baris saja (single-line), cocok untuk data pendek seperti nama, username, atau nomor telepon.
<textarea>: Mampu menerima masukan teks banyak baris (multi-line), mendukung perpindahan baris (enter), serta ukurannya dapat diatur menggunakan atribut rows dan cols atau di-resize oleh pengguna. Sangat sesuai untuk isian alamat, pesan, atau deskripsi panjang.
8. Apa fungsi semantic HTML seperti <header>, <nav>, <main>, <section>, <article>, <aside>, dan <footer>?
Fungsi utama semantic HTML adalah memberikan makna yang jelas mengenai peran setiap bagian dokumen, baik kepada browser, mesin pencari, maupun pengembang web:

<header>: Mendefinisikan bagian kepala halaman web atau bagian judul pembuka.
<nav>: Mengelompokkan menu tautan navigasi penting.
<main>: Membungkus konten utama yang menjadi pokok bahasan halaman (hanya boleh ada satu <main> per halaman).
<section>: Membagi konten menjadi kelompok bahasan atau seksi tematik.
<article>: Membungkus konten mandiri yang dapat berdiri sendiri secara utuh.
<aside>: Menyajikan konten pendukung atau informasi sampingan yang terpisah dari konten inti.
<footer>: Menampung bagian kaki dokumen yang memuat hak cipta, informasi kontak, atau tautan tambahan.
9. Apa fungsi required, min, max, dan minlength?
Atribut-atribut tersebut berfungsi untuk menerapkan validasi form dasar di sisi peramban:

required: Menandai bahwa suatu kolom wajib diisi pengguna sebelum formulir dapat disubmit.
min: Menentukan nilai angka numerik atau tanggal terendah yang diizinkan pada input bertipe number atau date.
max: Menentukan nilai angka numerik atau tanggal tertinggi yang diizinkan.
minlength: Menentukan jumlah batas minimal karakter teks yang harus diketikkan pengguna pada input teks atau textarea.
10. Apa perbedaan elemen <audio> dan <video>?

<audio>: Digunakan khusus untuk memutar berkas suara atau musik (format MP3, WAV, OGG) tanpa menampilkan antarmuka visual video di layar browser.
<video>: Digunakan untuk memutar berkas rekaman video (format MP4, WebM, OGG) yang menampilkan antarmuka visual gambar bergerak beserta audio, serta memiliki atribut pengaturan dimensi visual seperti width dan height.
Checklist Sebelum Dikumpulkan
Berdasarkan ketentuan modul Praktikum 2:

 Tabel berhasil ditampilkan dan memiliki header (<thead>, <tbody>, <tfoot>, colspan).
 Form memiliki label dan beberapa jenis input (text, email, password, date, number).
 Radio button dan checkbox sudah digunakan.
 Select dan textarea sudah digunakan.
 Validasi required dan validasi dasar lainnya sudah dicoba.
 Semantic HTML (header, nav, main, section, article, aside, footer) sudah digunakan.
 Audio dan video berhasil ditampilkan dari folder media/.
 Proyek mini biodata (biodata.html) menggabungkan seluruh materi utama.
 Screenshot 1.png sampai 7.png sudah tersedia di folder screenshots/.
 README.md sudah menjelaskan proses praktikum dan memuat 10 jawaban evaluasi.
 Repository sudah di-commit secara manual oleh mahasiswa.

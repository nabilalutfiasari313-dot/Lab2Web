```markdown
# Laporan Praktikum 2 - Pemrograman Web (Lab2Web)

Repositori ini disusun untuk memenuhi tugas Praktikum 2 - Pemrograman Web pada mata kuliah Pemrograman Web.

## Identitas Mahasiswa

* **Nama:** Nabila Lutfia Sari
* **NIM:** 312510040
* **Kelas:** TI25A
* **Program Studi:** Teknik Informatika
* **Dosen Pengampu:** Agung Nugroho, S.Kom., M.Kom.
* **Kampus:** Universitas Pelita Bangsa, Bekasi

---

## Panduan Screenshot Tugas
Simpan semua file tangkapan layar (screenshot) di dalam folder screenshots/ dengan format nama angka (1.png sampai 7.png) sesuai tabel berikut:

No File	Aplikasi / Lokasi	Yang Harus Di-Screenshot
1.png	Browser (index.html)	Tampilan tabel data nilai mahasiswa yang memiliki header (<thead>), baris data (<tbody>), dan footer (<tfoot>) dengan colspan.
2.png	Browser (index.html)	Tampilan form registrasi mahasiswa lengkap dengan input teks, email, password, tanggal lahir, umur, radio button jenis kelamin, checkbox keahlian, dropdown program studi, dan textarea alamat.
3.png	Browser (index.html)	Uji coba validasi form dasar: saat kolom required dikosongkan lalu tombol submit diklik, muncul pesan peringatan validasi dari browser.
4.png	Browser (index.html)	Tampilan pemutar multimedia audio dan video yang berhasil memuat file dari folder media/.
5.png	Browser (biodata.html)	Tampilan bagian atas proyek mini: header semantik, navigasi, dan tabel biodata diri mahasiswa (NIM, Nama, Kelas, Prodi).
6.png	Browser (biodata.html)	Tampilan bagian form pembaruan biodata mahasiswa dengan validasi atribut required.
7.png	Browser (biodata.html)	Tampilan bagian bawah proyek mini: pemutar multimedia video/audio profil, aside, dan footer halaman.

---

## Struktur Direktori Proyek

```text
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

```

---

## Langkah-Langkah Pengerjaan Praktikum

### 1. Membuat dan Mengembangkan Tabel HTML

Tabel digunakan untuk menampilkan data dalam bentuk baris dan kolom. Pada tahap ini dibuat tabel data nilai mahasiswa yang terstruktur menggunakan:

* `<table>`: Membungkus seluruh elemen tabel.
* `<caption>`: Memberikan judul keterangan pada tabel.
* `<thead>`: Menampung baris header kolom dengan tag `<th>`.
* `<tbody>`: Menampung kumpulan data utama mahasiswa dengan tag `<td>`.
* `<tfoot>`: Menampung baris ringkasan di bagian bawah.
* Atribut `colspan="4"`: Menggabungkan empat sel kolom menjadi satu pada baris nilai rata-rata.

**Potongan kode tabel pada `index.html`:**

```html
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
            <td>312510040</td>
            <td>Nabila Lutfia Sari</td>
            <td>Teknik Informatika</td>
            <td>95</td>
        </tr>
    </tbody>
    <tfoot>
        <tr>
            <td colspan="4" align="center"><b>Nilai Rata-rata</b></td>
            <td><b>95</b></td>
        </tr>
    </tfoot>
</table>

```

**Screenshot Hasil:**
*(Masukkan file `screenshots/1.png` di sini)*

---

### 2. Membuat Form Registrasi dengan Berbagai Jenis Input

Membuat form registrasi mahasiswa menggunakan tag `<form>` yang menampung beragam kontrol input data:

* `type="text"` untuk nama lengkap.
* `type="email"` untuk alamat email.
* `type="password"` untuk kata sandi.
* `type="radio"` untuk pilihan tunggal jenis kelamin.
* `type="checkbox"` untuk pilihan banyak pada keahlian/skill.
* `<select>` dan `<option>` untuk menu pilihan dropdown program studi.
* `<textarea>` untuk isian alamat yang membutuhkan beberapa baris teks.
* Hubungan label dengan kontrol input dibuat menggunakan atribut `for` yang merujuk ke atribut `id` pada input terkait.

**Potongan kode form pada `index.html`:**

```html
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

```

**Screenshot Hasil:**
*(Masukkan file `screenshots/2.png` di sini)*

---

### 3. Menerapkan Validasi Form Dasar HTML

Validasi formulir dilakukan langsung di sisi peramban (*client-side*) menggunakan atribut bawaan HTML tanpa perlu JavaScript:

* `required`: Memastikan input wajib diisi sebelum form dapat dikirim.
* `minlength`: Membatasi jumlah karakter minimal yang harus dimasukkan.
* `type="email"`: Secara otomatis memeriksa pola penulisan format email.

**Screenshot Hasil:**
*(Masukkan file `screenshots/3.png` di sini)*

---

### 4. Menambahkan Elemen Multimedia (Audio & Video)

Memasukkan media audio dan video lokal ke halaman web dengan meletakkannya di dalam folder `media/`:

* `<audio controls>`: Menampilkan pemutar audio lengkap dengan tombol play, pause, volume, dan timeline.
* `<video controls width="480">`: Menampilkan pemutar video beresolusi terukur yang mendukung kontrol pemutaran.

**Potongan kode multimedia:**

```html
<audio controls>
    <source src="media/audio.mp3" type="audio/mpeg">
    Browser tidak mendukung pemutar audio.
</audio>

<video controls width="480">
    <source src="media/video.mp4" type="video/mp4">
    Browser tidak mendukung pemutar video.
</video>

```

**Screenshot Hasil:**
*(Masukkan file `screenshots/4.png` di sini)*

---

### 5. Menerapkan Struktur Semantic HTML

Halaman web disusun dengan elemen semantik HTML5 untuk memberikan struktur yang jelas:

* `<header>`: Memuat kepala dokumen atau judul utama halaman.
* `<nav>`: Memuat daftar menu tautan navigasi utama.
* `<main>`: Membungkus seluruh konten pokok halaman web.
* `<section>`: Membagi konten ke dalam bab atau bagian bahasan tematik.
* `<aside>`: Memuat informasi tambahan/pelengkap.
* `<footer>`: Memuat kaki halaman yang berisi informasi hak cipta dan data mahasiswa.

---

### 6. Proyek Mini: Halaman Biodata Mahasiswa (`biodata.html`)

Sebagai proyek mini integrasi, dibuat file baru bernama `biodata.html` yang menggabungkan seluruh konsep yang dipelajari, mulai dari struktur semantik, tabel informasi data diri, form perbaruan, hingga penyematan elemen multimedia audio dan video profil.

**Potongan kode biodata.html:**

```html
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
        <a href="index.html">Kembali ke Beranda</a> |
        <a href="#biodata">Data Diri</a> |
        <a href="#form">Form Pembaruan Biodata</a>
    </nav>
    <hr>

    <main>
        <section id="biodata">
            <h2>Data Diri Mahasiswa</h2>
            <table border="1" cellpadding="8" cellspacing="0">
                <tr><th>Parameter</th><th>Keterangan Lengkap</th></tr>
                <tr><td><b>NIM</b></td><td>312510040</td></tr>
                <tr><td><b>Nama Lengkap</b></td><td>Nabila Lutfia Sari</td></tr>
                <tr><td><b>Program Studi</b></td><td>Teknik Informatika</td></tr>
            </table>
        </section>
    </main>
</body>
</html>

```

**Screenshot Hasil Proyek Mini:**

* Tabel Biodata Diri: *(Masukkan file `screenshots/5.png` di sini)*
* Formulir Biodata Mahasiswa: *(Masukkan file `screenshots/6.png` di sini)*
* Multimedia Profil & Footer: *(Masukkan file `screenshots/7.png` di sini)*

---

## Jawaban Pertanyaan Evaluasi Modul

1. **Apa fungsi `<table>`, `<tr>`, `<th>`, dan `<td>`?**
* `<table>`: Wadah utama untuk membuat tabel.
* `<tr>` (Table Row): Membuat baris baru di dalam tabel.
* `<th>` (Table Header): Membuat sel kepala/judul tabel dengan teks tebal secara otomatis.
* `<td>` (Table Data): Membuat sel untuk mengisi data reguler di dalam tabel.


2. **Apa perbedaan `<th>` dan `<td>`?**
* `<th>` digunakan khusus untuk sel judul atau header kolom/baris (teks otomatis tebal dan berada di tengah), sedangkan `<td>` digunakan untuk sel data isi tabel biasa.


3. **Apa fungsi `colspan` pada tabel?**
* `colspan` berfungsi untuk menggabungkan beberapa kolom secara horizontal menjadi satu sel tunggal.


4. **Apa fungsi `<form>` dalam HTML?**
* `<form>` berfungsi sebagai wadah interaktif untuk menampung elemen-elemen input guna mengumpulkan data dari pengguna agar dapat diproses.


5. **Apa perbedaan radio button dan checkbox?**
* *Radio button* (`type="radio"`): Hanya mengizinkan pengguna memilih **satu** opsi saja dari sekumpulan pilihan.
* *Checkbox* (`type="checkbox"`): Mengizinkan pengguna memilih **banyak (lebih dari satu)** opsi sekaligus.


6. **Mengapa `<label>` sebaiknya terhubung dengan id input melalui atribut `for`?**
* Atribut `for` yang disesuaikan dengan nilai `id` input membuat teks label menjadi interaktif (jika label diklik, kursor otomatis fokus ke kolom input) serta meningkatkan aksesibilitas web.


7. **Apa perbedaan `<textarea>` dengan input type text?**
* `<textarea>` digunakan untuk memasukkan teks berukuran panjang yang terdiri dari **banyak baris** (multi-line), sedangkan `<input type="text">` hanya dirancang khusus untuk input teks singkat satu baris.


8. **Apa fungsi semantic HTML seperti `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<aside>`, dan `<footer>`?**
* Elemen semantik memberikan arti yang jelas mengenai struktur dokumen web kepada browser, pengembang, dan mesin pencari (SEO), sehingga kode lebih terstruktur dan mudah diakses.


9. **Apa fungsi `required`, `min`, `max`, dan `minlength`?**
* Atribut validasi sisi klien (*client-side validation*):
* `required`: Kolom wajib diisi sebelum dikirim.
* `min` / `max`: Batasan nilai minimum dan maksimum untuk angka/tanggal.
* `minlength`: Batasan jumlah minimum karakter yang harus diketik.




10. **Apa perbedaan elemen `<audio>` dan `<video>`?**
* `<audio>` digunakan khusus untuk menyematkan dan memutar file suara/audio.
* `<video>` digunakan untuk menyematkan dan memutar file video beserta tampilan visualnya di dalam halaman web.



---

## Checklist Sebelum Dikumpulkan

* Tabel berhasil ditampilkan dan memiliki header (`<thead>`, `<tbody>`, `<tfoot>`, `colspan`).
* Form memiliki label dan beberapa jenis input.
* Radio button dan checkbox sudah digunakan.
* Select dan textarea sudah digunakan.
* Validasi `required` dan validasi dasar lainnya sudah dicoba.
* Semantic HTML sudah digunakan.
* Audio dan video berhasil ditampilkan dari folder `media/`.
* Proyek mini biodata (`biodata.html`) menggabungkan seluruh materi utama.
* README.md sudah menjelaskan proses praktikum dan memuat 10 jawaban evaluasi.
* Repository sudah di-commit secara manual oleh mahasiswa.

© 2026 Teknik Informatika - Universitas Pelita Bangsa | Nabila Lutfia Sari (312510040)

```

Nah, sekarang semuanya sudah murni atas nama dan data kamu ya! Silakan *copy* dan perbarui file `README.md` di GitHub kamu.

```

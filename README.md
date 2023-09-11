# Tailwind CSS

## Tentang Tailwind CSS

Ketika seorang developer ingin merealisasikan desain web, maka ia harus menggunakan CSS. Menggunakan CSS dapat dikatakan cukup sulit. Di saat sebuah website memiliki banyak komponen-komponen yang telah di-style menggunakan CSS mungkin saja seorang developer akan menjadi kesulitan jika ingin membuat nama kelas CSS untuk komponen baru di dalam file CSS yang terus-menerus menjadi lebih besar. Tailwind CSS menyediakan banyak ultility classes yang dapat digunakan secara langsung di dalam file HTML supaya dapat menyusun banyak komponen dengan cepat dan konsisten.

### Contoh menggunakan native CSS :

[isi gambar ngabers]

```html
<div class="chat-notification">
  <div class="chat-notification-logo-wrapper">
    <img class="chat-notification-logo" src="/img/logo.svg" alt="ChitChat Logo">
  </div>
  <div class="chat-notification-content">
    <h4 class="chat-notification-title">ChitChat</h4>
    <p class="chat-notification-message">You have a new message!</p>
  </div>
</div>

<style>
  .chat-notification {
    display: flex;
    max-width: 24rem;
    margin: 0 auto;
    padding: 1.5rem;
    border-radius: 0.5rem;
    background-color: #fff;
    box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1), 0 10px 10px -5px rgba(0, 0, 0, 0.04);
  }
  .chat-notification-logo-wrapper {
    flex-shrink: 0;
  }
  .chat-notification-logo {
    height: 3rem;
    width: 3rem;
  }
  .chat-notification-content {
    margin-left: 1.5rem;
    padding-top: 0.25rem;
  }
  .chat-notification-title {
    color: #1a202c;
    font-size: 1.25rem;
    line-height: 1.25;
  }
  .chat-notification-message {
    color: #718096;
    font-size: 1rem;
    line-height: 1.5;
  }
</style>
```

### Contoh menggunakan Tailwind CSS :

[isi gambar ngabers]

```html
<div class="p-6 max-w-sm mx-auto bg-white rounded-xl shadow-lg flex items-center space-x-4">
  <div class="shrink-0">
    <img class="h-12 w-12" src="/img/logo.svg" alt="ChitChat Logo">
  </div>
  <div>
    <div class="text-xl font-medium text-black">ChitChat</div>
    <p class="text-slate-500">You have a new message!</p>
  </div>
</div>
```

### Pro dan Kontra Tailwind

#### Pro

1. Kecepatan Pengembangan : Pengembangan pada Tailwind CSS dapat mempercepat proses mengaplikasikan kelas-kelas yang telah ada untuk mengatur tampilan elemen.
2. Konsistensi Desain : Tailwind CSS dapat membantu mempertahankan konsistensi desain di seluruh situs web atas aplikasi dengan menyediakan kelas-kelas desain yang telah ditentukan, sehingga mengurangi kesalahan styling.
3. Skalabilitas : Pengembang dapat dengan mudah mengelola dan memperbarui styling di seluruh situs, sehingga framework ini cocok untuk proyek-proyek besar dan kompleks.
4. Kustomisasi : Tailwind CSS tetap dapat disesuaikan dengan kebutuhan proyek dengan mudah melalui konfigurasi, walaupun memiliki kelas-kelas yang telah ditentukan.
5. Responsif : Tailwind CSS dapat memudahkan memudahkan pembuatan desin yang responsif dengan kelas-kelasnya, dengan pengaturan berdasarkan ukuran layar yang berbeda.

#### Kontra

1. Ukuran Berkas CSS yang besar : Tailwind CSS dapat menghasilkan berkas CSS yang besar karena pendekatan utilitasnya yang mengandung banyak kelas-kelas yang mungkin tidak semuanya digunakan dalam proyek.
2. Kurva Pembelajaran : Kurva pembelajaran pada Tailwind CSS harus benar-benar dipahami dan dikuasai guna berbagai kelas yang tersedia, sehingga sedikit susah bagi pengembang yang belum terbiasa.
3. Keterbatasan Desain : Tailwind CSS lebih terfokus pada pendekatan utilitas, sehingga beberapa desain dan elemen tertentu mungkin lebih sulit dicapai karena dapat membatasi kreativitas dalam desain.
4. Kustomisasi yang Terbatas : Meskipun dapat disesuaikan, tetapi ada pengecualian untuk beberapa desain yang sangat unik atau kompleks yang memungkinkan terlalu banyak kostomisasi.
5. Pertimbangan Keamanan : Inline styling yang dapat digunakan melalui kelas-kelas Tailwind CSS, namun perlu diperhatikan untuk memitigasi potensi kerentanan keamanan seperti Cross-Site Scripting (XSS) jika tidak digunakan dengan hati-hati

## Tailwind CSS vs Framework CSS Lainnya

| CSS Framework | Menyediakan Komponen UI Jadi | Kustomisasi                | Ukuran Framework | Komunitas              | Kemudahan                    |
| ------------- | ---------------------------- | -------------------------- | ---------------- | ---------------------- | ---------------------------- |
| Tailwind CSS  | Tidak                        | Sangat dapat dikustomisasi | Ringan           | Komunitas besar        | Cukup mudah untuk dipelajari |
| Bootstrap     | Ya                           | Susah dikostumisasi        | Berat            | Komunitas sangat besar | Sangat mudah dipelajari      |
| Foundation    | Ya                           | Cukup dapat dikustomisasi  | Berat            | Komunitas lebih kecil  | Lebih susah dipelajari       |
| Bulma         | Ya                           | Cukup dapat dikustomisasi  | Ringan           | Kemunitas lebih kecil  | Sangat mudah dipelajari      |

## Tutorial Tailwind dengan NPM

1. Siapkan folder project baru dengan menggunakan  perintah :

   ```
   mkdir belajar-tailwind
   ```
2. Lakukan inisialisasi dengan NPM dalam folder tersebut.

   ```
   npm init
   ```

   perintah ini akan membuat file baru bernama `package.json`
3. Install Tailwind CSS

   ```
   npm install tailwindcss
   ```
4. Lakukan file konfigurasi

   ```
   npx tailwindcss init
   ```

   dengan perintah ini akan membuat file baru `tailwind.config.js`
5. Lakukan konfigurasi path konten pada file `tailwind.config.js`

   ```
   /** @type {import('tailwindcss').Config} */
   module.exports = {
     content: ["./src/**/*.{html,js}"],
     theme: {
       extend: {},
     },
     plugins: [],
   }
   ```

   pada `content:`, di sana tempat menambahkan path `./src/**`

   Artinya saat kita melakukan build CSS, si Tailwind akan mencari class-class apa saja yang dipakai di file HTML dan JS pada path tersebut.
6. Buat folder baru dengan nama `src` di dalam project. lalu buat file CSS dengan nama `input.css` dan isi seperti ini:

   ```
   @tailwind base;
   @tailwind components;
   @tailwind utilities;
   ```
7. Buat folder `index.html` di dalam folder `src` untuk menggunakan class-class dari tailwind dan isi seperti ini:

   ```
   <!DOCTYPE html>
   <html lang="en">
   <head>
       <meta charset="UTF-8">
       <meta http-equiv="X-UA-Compatible" content="IE=edge">
       <meta name="viewport" content="width=device-width, initial-scale=1.0">
       <link rel="stylesheet" href="/dist/output.css"/>
       <title>Project Tailwind dengan NPM</title>
   </head>
   <body>
     <h1 class="text-3xl font-bold text-teal-700">Petani Kode</h1>
   </body>
   </html>
   ```
8. Jalankan perintah :

   ```
   npx tailwindcss -i src/input.css -o dist/output.css
   ```

   yang bertujuan untuk membuat file CSS (`output.css`) berdasarkan class-class yang dipakai pada path konten (`index.html`).

   Jika ingin hasil build-nya di-optimasi (minify), gunakan opsi --minify di belakannya seperti:

   ```
   npx tailwindcss -i src/input.css -o dist/output.css --minify
   ```

#### Menggunakan Live Server

Alur kerja kita di project Tailwind dengan NPM adalah seperti ini:

1. Ubah atau gunakan class di file HTML
2. Jalankan perintah untuk build CSS Tailwind
3. Lihat hasilnya di browser

Ini cukup merepotkan, karena harus dilakukan berulang-ulang.

Biar tidak begini, kita bisa pakai Live server dan membuat custom script sendiri di `package.json`.

Silahkan buka file `package.json`, lalu di bagian `"scripts"` buat menjadi seperti ini:

```
{
  "name": "belajar-tailwind",
  "version": "1.0.0",
  "description": "belajar tailwind",
  "main": "index.js",
  "scripts": {
    "dev": "tailwindcss -i src/input.css -o dist/output.css --watch",
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "author": "",
  "license": "ISC",
  "dependencies": {
    "tailwindcss": "^3.1.8"
  }
}
```

Pada script ini, kita menentukan perintah untuk build CSS tailwind dengan opsi `--watch`.

Ini artinya Tailwind akan memantau perubahan yang terjadi pada konten, lalu langsung melakukan build otomatis.

Setelah itu, install [extension Live Server Preview](https://marketplace.visualstudio.com/items?itemName=ms-vscode.live-server) di VS Code

Extension ini buat buka live preview langsung di VS Code, tanpa harus buka web browser.

Nah sekarang mari kita coba!

Buka terminal di VS Code, lalu jalankan perintah ini:

```
npm run dev
```

Ini akan menjalankan perintah yang sudah kita definisikan di `package.json`.

Setelah itu, klik kanan pada file `index.html` kemudian pilih  *show preview* .

[Tutorial Lengkapnya bisa cek disini.](https://www.petanikode.com/tailwind-dasar/)

## Ilustrasi Arsitektur Framework

## Sampel Kode

## Further Reading & List Tutorial

- https://tailwindcss.com/docs
- https://www.petanikode.com/tailwind-dasar/
- https://marketplace.visualstudio.com/items?itemName=ms-vscode.live-server
- https://marketplace.visualstudio.com/items?itemName=bradlc.vscode-tailwindcss

## Referensi

- https://tailwindcss.com/docs/utility-first
- https://blog.techwithbruce.com/the-pros-and-cons-of-tailwind-css
- https://www.linkedin.com/pulse/css-framework-showdown-bootstrap-vs-foundation-tailwind-umair-tahir/
- https://blog.logrocket.com/bulma-vs-tailwind-css-better-bootstrap-alternative/

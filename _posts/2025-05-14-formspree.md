---
layout : post
title : "Formspree"
---


Penjelasan tentang formspree

## Panduan Lengkap tentang Formspree

Formspree adalah layanan form handler yang memungkinkan Anda untuk mengirimkan data formulir (form) melalui email tanpa memerlukan backend server. Anda cukup membuat HTML form, dan Formspree akan menangani pengiriman form dan mengirimkan hasilnya ke email yang ditentukan.

## Apa itu Formspree?
Formspree adalah alat yang memungkinkan Anda mengirimkan data dari formulir HTML ke email Anda tanpa menulis backend kode server. Ini sangat berguna jika Anda tidak ingin menangani server sendiri atau menggunakan platform yang tidak menyediakan form handler.

## Kelebihan Menggunakan Formspree
- **Mudah digunakan**: Tidak perlu membuat backend server untuk menangani pengiriman form.
- **Gratis**: Formspree menyediakan paket gratis dengan fitur dasar.
- **Keamanan**: Data formulir dikirim ke email dengan aman.
- **Pengaturan Mudah**: Cukup sesuaikan HTML form Anda dengan beberapa atribut untuk mengonfigurasi pengiriman.

## Langkah-Langkah Menggunakan Formspree

### 1. Membuat Akun di Formspree
Untuk menggunakan Formspree, Anda harus membuat akun terlebih dahulu.
- Kunjungi [Formspree.io](https://formspree.io)
- Daftar dengan email Anda dan buat akun.

### 2. Membuat Formulir HTML
Formulir HTML adalah tempat pengguna akan memasukkan data. Berikut adalah contoh dasar formulir HTML yang menggunakan Formspree untuk mengirim data:

```html
<form action="https://formspree.io/f/mjkwpnrq"
 method="POST">
  <label for="name">Nama:</label>
  <input type="text" id="name" name="name" 
  required>

  <label for="email">Email:</label>
  <input type="email" id="email" name="_replyto"
   required>

  <label for="message">Pesan:</label>
  <textarea id="message" name="message" required>
    
  </textarea>

  <button type="submit">Kirim Pesan</button>
</form>
```

**Penjelasan:**

* `action`: URL yang disediakan oleh Formspree yang mengarah ke endpoint pengiriman form.
* `method`: Biasanya menggunakan metode `POST` untuk mengirim data.
* `name`: Atribut ini menentukan nama kolom data yang akan dikirimkan ke email Anda. Misalnya, `name="name"` akan mengirimkan nilai input nama pengguna.
* `_replyto`: Atribut ini adalah tempat untuk menempatkan email pengirim.

### 3. Mengonfigurasi Formspree

* Setelah Anda menyiapkan formulir, pergi ke [Formspree Dashboard](https://formspree.io/dashboard).
* Buat formulir baru atau gunakan formulir yang sudah ada.
* Salin URL formulir yang disediakan oleh Formspree dan masukkan ke dalam atribut `action` di HTML formulir Anda.
* Tentukan email penerima di dashboard Formspree untuk memastikan hasil formulir dikirim ke email yang benar.

### 4. Mengirim Formulir

Setelah formulir HTML Anda siap dan dikonfigurasi, ketika pengguna mengisi formulir dan mengirimkannya, data akan dikirimkan ke email yang telah Anda tentukan melalui Formspree. Anda akan menerima email setiap kali formulir dikirim.

### 5. Menangani Respons dan Pengaturan Lanjutan

Formspree memungkinkan Anda untuk mengonfigurasi beberapa pengaturan lanjutan, seperti:

* **Email Balasan Otomatis**: Anda dapat menambahkan pengaturan untuk mengirim email balasan otomatis kepada pengirim formulir.
* **Akses ke Data Formulir**: Anda dapat melihat data formulir yang terkirim melalui dashboard Formspree.
* **Batasan Penggunaan**: Paket gratis memiliki batasan jumlah pengiriman formulir per bulan. Paket premium memungkinkan pengiriman lebih banyak.

### 6. Menggunakan JavaScript dengan Formspree

Formspree memungkinkan integrasi dengan JavaScript untuk meningkatkan interaktivitas pengiriman form. Berikut adalah contoh menggunakan JavaScript untuk menangani pengiriman form tanpa melakukan reload halaman:

```html
<script>
  const form = document.querySelector
  ('form');
  form.addEventListener('submit', function
  (event) {
    event.preventDefault(); 
    // Mencegah reload halaman setelah 
    // pengiriman

    fetch('https://formspree.io/f/mjkwpnrq', 
    {
      method: 'POST',
      body: new FormData(form),
      headers: {
        'Accept': 'application/json'
      }
    })
    .then(response => {
      if (response.ok) {
        alert('Formulir berhasil dikirim!');
      } else {
        alert('Terjadi kesalahan, 
        coba lagi.');
      }
    })
    .catch(error => {
      alert('Terjadi kesalahan: ' + error);
    });
  });
</script>
```

Dalam contoh ini, setelah formulir dikirim, JavaScript akan menangani pengiriman data dan memberikan respons tanpa mereload halaman.

## Paket yang Tersedia

Formspree menawarkan beberapa paket:

* **Paket Gratis**: Tersedia untuk penggunaan pribadi atau situs dengan pengiriman form yang lebih sedikit.
* **Paket Premium**: Memungkinkan pengiriman formulir lebih banyak per bulan dan menyediakan fitur tambahan seperti email balasan otomatis dan pengaturan lanjutan.

### Fitur Premium:

* **Penyimpanan Pengiriman**: Menyimpan pengiriman formulir di dashboard untuk analitik.
* **Email Balasan Otomatis**: Mengirimkan email balasan otomatis kepada pengirim formulir.
* **Keamanan**: Mendukung autentikasi dua faktor dan perlindungan terhadap penyalahgunaan formulir.

## Keamanan Formspree

Formspree menggunakan mekanisme keamanan untuk mencegah penyalahgunaan formulir Anda:

* **Proteksi Spam**: Formspree memiliki fitur proteksi spam untuk menghindari pengiriman formulir otomatis dari bot.
* **HTTPS**: Semua data dikirimkan melalui koneksi yang aman dengan protokol HTTPS.

## Kesimpulan

Formspree adalah pilihan yang sangat baik bagi siapa saja yang ingin mengirim data formulir melalui email tanpa harus menulis kode backend atau mengelola server. Dengan pengaturan yang mudah dan berbagai fitur tambahan seperti email balasan otomatis dan integrasi dengan JavaScript, Formspree sangat cocok untuk situs statis atau aplikasi frontend yang membutuhkan pengiriman formulir.

## Referensi

* [Formspree Documentation](https://formspree.io/docs)
* [Formspree Pricing](https://formspree.io/pricing)



### Penjelasan:
- **Formulir HTML**: Ini adalah bagian utama di mana Anda menyiapkan form yang mengirimkan data ke Formspree.
- **Pengaturan Pengiriman**: Anda dapat menyesuaikan formulir dengan berbagai pengaturan di Formspree, seperti email penerima dan pengaturan email balasan.
- **JavaScript Integration**: Untuk pengalaman yang lebih dinamis, Anda dapat menambahkan JavaScript untuk menangani pengiriman formulir tanpa reload halaman.


---
layout : post
title : "SCSS dan SASS"
---


Penjelasan tentang SCSS dan SASS

# Panduan Lengkap SCSS dan SASS

SASS (Syntactically Awesome Stylesheets) adalah preprocessor CSS yang memberikan fitur tambahan yang memperluas kemampuan CSS tradisional. SASS memiliki dua sintaks yang berbeda: **SASS** dan **SCSS**. Meskipun keduanya memiliki fungsionalitas yang sama, mereka menggunakan pendekatan sintaks yang berbeda, sehingga bisa disesuaikan dengan preferensi pengembang.

## 1. Apa itu SCSS?

**SCSS (Sassy CSS)** adalah salah satu sintaks dari SASS yang mengadopsi struktur CSS. Ini membuat SCSS lebih mudah dipahami bagi pengembang yang sudah familiar dengan CSS, karena strukturnya hampir sama dengan CSS standar.

### Fitur Utama SCSS:

* **Variabel:** Menyimpan nilai yang dapat digunakan kembali, seperti warna dan font.
* **Nesting:** Menyusun selector CSS secara hierarkis, membuat kode lebih mudah dibaca.
* **Mixins:** Menyusun kumpulan gaya yang dapat digunakan kembali di seluruh halaman, mengurangi kode yang berulang.
* **Inheritance:** Menggunakan `@extend` untuk berbagi gaya antara selector, menyederhanakan kode.
* **Partials dan Import:** Memecah kode CSS menjadi file modular menggunakan `@import`, menjaga gaya lebih terorganisir.

### Contoh SCSS:

```scss
$primary-color: blue;
$font-size: 16px;

body {
  background-color: $primary-color;
  color: white;
  font-size: $font-size;

  .header {
    font-size: 2em;
    padding: 10px;
  }
}
```

### Output CSS:

```css
body {
  background-color: blue;
  color: white;
  font-size: 16px;
}

body .header {
  font-size: 2em;
  padding: 10px;
}
```

## 2. Apa itu SASS?

**SASS (Syntactically Awesome Stylesheets)** adalah preprocessor CSS yang menggunakan sintaks berbasis indentasi. Tidak ada tanda kurung `{}` atau titik koma `;`, yang menjadikannya lebih bersih dan lebih minimalis dibandingkan dengan CSS standar.

### Fitur Utama SASS:

* **Variabel:** Mendefinisikan nilai yang dapat digunakan kembali, seperti warna dan font.
* **Nesting:** Mengorganisir CSS dalam struktur visual yang hierarkis.
* **Partials:** Memecah stylesheet besar menjadi beberapa file dengan `@import`.
* **Mixins:** Menggunakan set aturan CSS yang dapat diterapkan ke berbagai selector.
* **Inheritance:** Menggunakan `@extend` untuk berbagi gaya antar selector.

### Contoh SASS:

```sass
$primary-color: blue
$font-size: 16px

body
  background-color: $primary-color
  color: white
  font-size: $font-size

  .header
    font-size: 2em
    padding: 10px
```

### Output CSS:

```css
body {
  background-color: blue;
  color: white;
  font-size: 16px;
}

body .header {
  font-size: 2em;
  padding: 10px;
}
```

## 3. Perbedaan antara SCSS dan SASS

Berikut adalah perbedaan utama antara **SCSS** dan **SASS**:

| Fitur              | **SCSS**                                                         | **SASS**                                                                |
| ------------------ | ---------------------------------------------------------------- | ----------------------------------------------------------------------- |
| **Sintaks**        | Sintaks seperti CSS, dengan tanda kurung `{}` dan titik koma `;` | Sintaks berbasis indentasi tanpa tanda kurung `{}` dan titik koma `;`   |
| **Ekstensi File**  | `.scss`                                                          | `.sass`                                                                 |
| **Fleksibilitas**  | Familiar bagi pengembang yang tahu CSS                           | Lebih sederhana dan bersih untuk beberapa pengembang                    |
| **Penggunaan**     | Ideal bagi pengembang yang beralih dari CSS                      | Lebih disukai bagi yang mengutamakan kode yang lebih ringkas dan bersih |

## 4. Kapan Menggunakan SCSS?

**SCSS** adalah pilihan yang baik bagi pengembang yang sudah familiar dengan CSS. Dengan sintaks yang mirip, SCSS memungkinkan pengembang beralih ke SASS dengan mudah dan memanfaatkan fitur-fitur tambahan seperti variabel, mixins, dan nesting.

### Kapan menggunakan SCSS:

* Mudah dipelajari bagi pengembang CSS.
* Cocok untuk proyek yang lebih besar.
* Kompatibel dengan CSS standar.

## 5. Kapan Menggunakan SASS?

**SASS** sangat cocok bagi pengembang yang lebih memilih sintaks yang lebih minimalis dan bersih. SASS sering digunakan untuk proyek kecil di mana kebersihan dan keterbacaan kode sangat penting.

### Kapan menggunakan SASS:

* Terbaik untuk kode yang lebih sederhana dan bersih.
* Cocok untuk proyek kecil.
* Tidak membutuhkan kompatibilitas dengan CSS standar.

## 6. Menggunakan SCSS untuk Styling Layout

Pada praktikum kali ini, kita akan mengubah layout website agar lebih rapi dan menarik menggunakan SCSS. Ikuti langkah-langkah berikut:

### 6.1. Update File `navigation.html`

Buka file `navigation.html` yang ada di folder `_includes` dan lakukan perubahan sesuai kebutuhan. Contoh kode yang diperbarui bisa terlihat seperti berikut:

```html
<nav>
  <ul>
    <li><a href="/">Home</a></li>
    <li><a href="/about">About</a></li>
    <li><a href="/contact">Contact</a></li>
  </ul>
</nav>
```

### 6.2. Update File `main.scss`

Buka file `main.scss` dan tambahkan kode SCSS untuk mendesain layout dengan lebih baik:

```scss
$primary-color: #3498db;
$font-size: 16px;

body {
  font-family: Arial, sans-serif;
  background-color: #f4f4f4;
  color: #333;
}

nav {
  background-color: $primary-color;
  ul {
    list-style-type: none;
    padding: 0;
  }

  li {
    display: inline;
    margin-right: 20px;

    a {
      color: white;
      text-decoration: none;
    }
  }
}
```

### 6.3. Update File `default.html`

Perbarui file `default.html` di folder `_layouts` dengan struktur layout yang baru:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-
  width, initial-scale=1.0">
  <title>{{ page.title }}</title>
  <link rel="stylesheet" href="{{ site.baseurl }}
  /assets/css/main.css">
</head>
</html>
```

## 7. Kesimpulan

**SCSS** dan **SASS** memberikan fungsionalitas yang sama, tetapi pemilihan antara keduanya bergantung pada preferensi sintaks masing-masing pengembang. **SCSS** lebih cocok bagi pengembang yang sudah terbiasa dengan CSS, sedangkan **SASS** lebih minimalis dan cocok bagi mereka yang mengutamakan kode yang lebih ringkas. Keduanya menawarkan fitur-fitur seperti variabel, mixins, dan nesting yang dapat meningkatkan efisiensi dalam menulis CSS.
---
layout : post
title : "Instalasi Ruby dan Jekyll"
---


Penjelasan tentang instalasi ruby dan jekyll

---

## **1. Instalasi**  
### a) **Install Ruby dan Jekyll**  
1. **Cek apakah Ruby sudah terpasang**  
   Buka terminal atau Command Prompt, lalu ketik:  
   ```bash
   ruby -v
   ```
   Jika Ruby sudah terpasang, maka akan muncul versi Ruby. Jika belum, ikuti langkah berikutnya.  

2. **Cek RubyGems**  
   Ketik perintah berikut:  
   ```bash
   gem -v
   ```

3. **Cek GCC dan Make**  
   Ketik perintah berikut:  
   ```bash
   gcc -v
   g++ -v
   make -v
   ```  
Jika belum terpasang, install terlebih dahulu dengan <strong>MinGW</strong> (untuk Windows) atau gunakan package manager seperti <code>apt</code> (untuk Linux).  



4. **Download Ruby Installer**  
   - Buka link berikut: [https://rubyinstaller.org](https://rubyinstaller.org)  
   - Pilih versi **Ruby 2.7.0** atau lebih tinggi.  
   - Ikuti instruksi instalasi hingga selesai.  

5. **Install Jekyll dan Bundler**  
   Setelah Ruby terpasang, install Jekyll dan Bundler dengan perintah:  
   ```bash
   gem install jekyll bundler
   ```

---

### b) **Install Git**  
1. **Download Git Installer**  
   - Buka link berikut: [https://git-scm.com](https://git-scm.com)  
   - Pilih installer yang sesuai dengan sistem operasi (contoh: **64-bit untuk Windows**).  

2. **Lakukan Instalasi**  
   - Ikuti instruksi instalasi hingga selesai.  
   - Setelah selesai, cek apakah Git sudah terpasang dengan perintah:  
   ```bash
   git --version
   ```

---

### c) **Install Visual Studio Code**  
1. **Download VSCode Installer**  
   - Buka link berikut: [https://code 
   .visualstudio.com](https://code.visualstudio.com)  
   - Pilih installer sesuai dengan sistem operasi (contoh: **64-bit untuk Windows**).  

2. **Lakukan Instalasi**  
   - Ikuti instruksi hingga selesai.  

---

### d) **Install Google Chrome**  
1. **Download Chrome Installer**  
   - Buka link berikut: [https://www.
   google.com/chrome](https://www.google.com/chrome)    
   - Klik tombol **Download Chrome**.  
   - Ikuti instruksi instalasi hingga selesai.  

---

## **2. Personal Web dengan Jekyll dan GitHub Pages**  
### **1. Buat Akun GitHub**  
- Buka [https://github.com](https://github.com) dan daftar akun.  

---

### **2. Buat Repository GitHub**  
- Buat repository baru dengan nama:  
   ```text
   username.github.io
   ```
   **Contoh**: Jika username GitHub kamu `faiza`, maka repository-nya adalah:  
   ```text
   faiza.github.io
   ```

---

### **3. Clone Repository ke Lokal**  
Buka terminal atau Command Prompt, lalu jalankan:  
```bash
git clone https://github.com/
username/username.github.io.git
```
**(Ganti `username` dengan username GitHub kamu)**  

---

### **4. Inisialisasi Jekyll di Folder Repository**  
Masuk ke folder repository:  
```bash
cd username.github.io
```
Inisialisasi Jekyll:  
```bash
bundle init
```
Perintah ini akan membuat file `Gemfile` di dalam folder proyek.  

---

### **5. Edit `Gemfile`**  
Buka file `Gemfile` di VSCode, lalu tambahkan kode berikut:  
```ruby
source "https://rubygems.org"

gem "jekyll"
```
Lalu jalankan perintah:  
```bash
bundle install
```

---

### **6. Buat File `index.html`**  
Buat file baru bernama `index.html` di dalam folder proyek, lalu isi dengan kode berikut:  
```html
<!DOCTYPE html>
<html>
<head>
  <title>My Jekyll Site</title>
</head>
<body>
  <h1>Welcome to My Jekyll Site!</h1>
  <p>This is a sample site created with
     Jekyll and GitHub Pages.</p>
</body>
</html>
```

---

### **7. Build dan Jalankan Jekyll**  
Jalankan perintah berikut untuk build website:  
```bash
jekyll build
```
Untuk menjalankan server Jekyll:  
```bash
jekyll serve
```
Cek di browser:  
```
http://localhost:4000
```

**Tips:** Jika ingin hasil perubahan otomatis terlihat di browser, jalankan dengan:  
```bash
jekyll serve --livereload
```

---

### **8. Edit `Gemfile.lock` untuk Platform Linux**  
Buka file `Gemfile.lock`, lalu tambahkan **platform linux** pada bagian `PLATFORMS`:  
```text
PLATFORMS
  ruby
  x86_64-linux
```

---

### **9. Push Repository ke GitHub**  
Setelah berhasil dijalankan secara lokal, upload ke GitHub dengan perintah:  
```bash
git add .
git commit -m "Initial commit"
git push origin main
```

---

### **10. Buat GitHub Actions untuk CI/CD**  
1. Di dalam repository GitHub, buat folder `.github/workflows`.  
2. Buat file baru `jekyll.yml` di dalam folder tersebut, lalu tambahkan kode berikut:  
```yaml
name: Jekyll Deploy

on:
  push:
    branches:
      - main

jobs:
  build-deploy:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout repository
        uses: actions/checkout@v2
      
      - name: Setup Ruby
        uses: ruby/setup-ruby@v1
        with:
          ruby-version: '2.7'

      - name: Install dependencies
        run: bundle install

      - name: Build site
        run: JEKYLL_ENV=production bundle exec 
        jekyll build

      - name: Deploy to GitHub Pages
        uses: peaceiris/actions-gh-pages@v3
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          publish_dir: ./_site
```

3. Commit dan push ke GitHub:  
```bash
git add .
git commit -m "Add GitHub Actions for 
Jekyll deployment"
git push origin main
```

---

### **Selesai!**  
Sekarang website kamu bisa diakses di:  
```text
https://username.github.io
```
(Ganti `username` dengan username GitHub kamu)  

---

**Troubleshooting:**
- Jika terjadi error karena **port konflik**, jalankan dengan perintah berikut:  
```bash
jekyll serve --host 0.0.0.0 --port 4001
```
- Jika build gagal, cek apakah Ruby dan Bundler sudah terpasang dengan benar.  
- Jika GitHub Pages tidak memuat, pastikan branch utama sudah diatur ke `main` di pengaturan repository.  


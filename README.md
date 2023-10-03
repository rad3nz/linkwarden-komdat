# Stash Goods
## Sekilas Tentang
Mamo adalah sebuah website yang dibuat untuk **mencatat arus pemasukan dan pengeluaran serta mengkalkulasi saldo uang yang dimiliki secara otomatis**

## Instalasi

#### Requirements :
- OS (Linux, MacOS, Windows)
- Docker
- Git
- Microsoft Azure Virtual Machine

#### Proses Instalasi
1. Login ke dalam server menggunakan ssh
   ```
   ssh rabbani@20.244.35.91
   ```
   
2. Lakukan instalasi docker menggunakan apt repository pada termninal
   berdasarkan panduan berikut:
   ```
   https://docs.docker.com/engine/install/ubuntu/
   ```
   
3. Lakukan clone pada repository Linkwarden:
   ```
   git clone https://github.com/linkwarden/linkwarden.git
   ```
   
4. Masuk ke direktori yang sudah dibuat dengan command berikut:
   ```
   cd linkwarden
   ```
   
5. Buat sebuah file dengan nama `.env`:
   ```
   touch .env
   ```
   Kemudian lakukan [konfigurasi](https://docs.docker.com/engine/install/ubuntu/) pada file tersebut
   

7. Jika sudah dikonfigurasi, jalankan dengan Docker Compose:
   ```
   sudo docker compose up -d
   ``` 


## Konfigurasi

1. Buka file `.env` dengan command:
   ```
   nano .env
   ```

2. Salin dan tempel kode di bawah:
   ```
   NEXTAUTH_SECRET=VERY_SENSITIVE_SECRET
   POSTGRES_PASSWORD=YOUR_POSTGRES_PASSWORD
   NEXTAUTH_URL=http://localhost:3000
   ```
   Ganti pada bagian `VERY_SENSITIVE_SECRET` dan `YOUR_POSTGRES_PASSWORD` dengan sebuah password dan keduanya harus berbeda.

   Pada bagian `NEXTAUTH_URL` link url dapat diganti dengan IP pada ssh dan juga port pada server.

   
   Contoh:
   ```
   http://20.244.35.91:80
   ```

4. Buka file `docker-compose.yml`:
   ```
   nano docker-compose.yml
   ```

5. Pada bagian ports ganti angka sebelah kiri dengan port pada server

   
   Contoh:
   ```
   80:3000
   ```
   

##  Maintenance (opsional)

Setting tambahan untuk maintenance secara periodik, misalnya:
- buat backup database tiap pekan
- hapus direktori sampah tiap hari
- dll


## Otomatisasi (opsional)

Skrip shell untuk otomatisasi instalasi, konfigurasi, dan maintenance.



## Cara Pemakaian
### Login Page
- Langkah pertama adalah pengguna harus masuk ke dalam sistem dengan akun yang sudah dimilikinya.
![image](https://github.com/rad3nz/mamo-komdat/assets/133312076/b44d6422-cef3-4a95-ba5b-5e58d1e9e59f)

- Jika pengguna belum memiliki akun, maka langkah pertama yang perlu dilakukan adalah mendaftar (Sign Up) untuk membuat akun baru.
![image](https://github.com/rad3nz/mamo-komdat/assets/133312076/045ae652-2c71-498c-8d3f-f7a6f60b829a)

### Dashboard
- Setelah login, user akan masuk ke halaman Dashboard. Pada bagian Dashboard, user dapat melihat total link, collections, tags, dan favorite link yang sudah diupload dari usernya itu sendiri.
- Lalu juga ada beberapa menu yang dapat dikunjungi seperti dashboard, link, dan collection.
![image](https://github.com/rad3nz/mamo-komdat/assets/133312076/59a28f9b-2372-4d9c-89e0-6c3329702d4b)

### Collection
- Pada menu Collection, user dapat melihat data atau folder yang sudah dibuat untuk menyimpan link di folder tersebut.
Untuk membuat foldernya, user harus memencet gambar atau tombol "New Collection" tersebut
![image](https://github.com/rad3nz/mamo-komdat/assets/133312076/39528a6a-c08d-4561-8fdc-4529d5e23962)

- Setelah itu, user dapat menamakan dan mengisi deskripsi folder tersebut serta mewarnai foldernya untuk membedakan folder-folder lainnya.
jika sudah, tekan tombol "Add" dan akan muncul di Collection
![image](https://github.com/rad3nz/mamo-komdat/assets/133312076/059bad45-f832-4b76-b17a-601892c9949e)
![image](https://github.com/rad3nz/mamo-komdat/assets/133312076/962bcd7b-cdb3-4394-8f1b-d83126885ea4)

- Tampilan aplikasi web
- Fungsi-fungsi utama
- Isi dengan data real/dummy (jangan kosongan) dan sertakan beberapa screenshot


## Pembahasan

Aplikasi web Stash Goods ini masih berada pada tingkat dasar dengan kelebihannya ialah development yang mudah
dan deployment yang mudah. Adapun pada deployment saat ini hanya terbatas pada page admin saja dan tidak bisa
melakukan registrasi ataupun login user. Fungsi manipulasi barang pun terbatas

Perbandingan dengan web sejenis biasa terletak pada fungsionalitas manipulasi barang, dengan tingkat kedalaman yang lebih _advanced_.


## Referensi

Cantumkan tiap sumber informasi yang anda pakai.

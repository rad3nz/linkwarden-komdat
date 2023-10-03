![image](https://github.com/rad3nz/mamo-komdat/assets/133312076/5214805f-ec44-4216-be7f-55705b59ae2e)

# Linkwarden

[Sekilas Tentang](#sekilas-tentang) | [Instalasi](#instalasi) | [Konfigurasi](#konfigurasi) | [Cara Pemakaian](#cara-pemakaian) | [Pembahasan](#pembahasan) | [Referensi](#referensi)
:---:|:---:|:---:|:---:|:---:|:---:

## Sekilas Tentang
Linkwarden adalah manajer bookmark kolaboratif sumber terbuka yang dapat di-host sendiri untuk mengumpulkan, mengorganisir, dan mengarsipkan halaman web. Tujuannya adalah untuk mengorganisir halaman web dan artikel yang berguna yang Anda temukan di seluruh web dalam satu tempat, dan karena halaman web yang berguna dapat hilang (lihat ketidakmungkinan Link Rot), Linkwarden juga menyimpan salinan dari setiap halaman web sebagai tangkapan layar dan PDF, memastikan aksesibilitas bahkan jika konten aslinya tidak lagi tersedia. Selain itu, Linkwarden dirancang dengan kolaborasi dalam pikiran, memungkinkan berbagi tautan dengan publik dan/atau memungkinkan beberapa pengguna bekerja sama dengan lancar.

## Instalasi

#### Requirements :
- OS (Linux, MacOS, Windows)
- Docker
- Git
- Microsoft Azure Virtual Machine

#### Proses Instalasi
1. Login ke dalam server menggunakan ssh dan password
   ```
   ssh komdatprojek@20.197.16.112
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
   Kemudian lakukan [konfigurasi](https://github.com/rad3nz/mamo-komdat/blob/main/README.md#konfigurasi) pada file tersebut
   

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
- Setelah login, user akan masuk ke halaman Dashboard. Pada bagian Dashboard, user dapat melihat total link, collections, tags, dan favorite link yang sudah diupload dari usernya itu sendiri. Pada bagian headernya user juga dapa melihat  profile user, tombol "+ New Link", dan juga "search link" untuk mencari tautan yang ingin dibuka.
- Lalu juga ada beberapa menu yang dapat dikunjungi link dan collection.
![image](https://github.com/rad3nz/mamo-komdat/assets/133312076/59a28f9b-2372-4d9c-89e0-6c3329702d4b)

### Collection
- Pada menu Collection, user dapat melihat data atau folder yang sudah dibuat untuk menyimpan link di folder tersebut.
Untuk membuat foldernya, user harus memencet gambar atau tombol "New Collection" tersebut
![image](https://github.com/rad3nz/mamo-komdat/assets/133312076/39528a6a-c08d-4561-8fdc-4529d5e23962)

- Setelah itu, user dapat menamakan dan mengisi deskripsi folder tersebut serta mewarnai foldernya untuk membedakan folder-folder lainnya.
jika sudah, tekan tombol "Add" dan folder yang baru dibua muncul di Collection.
![image](https://github.com/rad3nz/mamo-komdat/assets/133312076/059bad45-f832-4b76-b17a-601892c9949e)
![image](https://github.com/rad3nz/mamo-komdat/assets/133312076/962bcd7b-cdb3-4394-8f1b-d83126885ea4)

### Link
- Di dalam menu "Link," pengguna dapat menelusuri link-link yang telah diunggah ke dalam folder yang telah dibuat sebelumnya.
  Untuk mengunggah tautan, langkah pertama adalah pengguna perlu mengklik tombol "+ New Link" yang terletak di bagian header paling kanan, dekat dengan profil user.
![image](https://github.com/rad3nz/mamo-komdat/assets/133312076/5115e3fc-41d8-4dc8-9f2c-86a00f965c06)
- Kemudian user dapat memasukkan tautan ke dalam "Alamat (URL)" dan juga memilih folder tempat tautan akan disimpan. Lalu klik tombol "+ Add" untuk menambah link yang baru dibuat.
![image](https://github.com/rad3nz/mamo-komdat/assets/133312076/7dc787a5-01eb-414a-8e47-820cae56b4c3)
- Jika user ingin lebih spesifik atau mendetail, user dapat menekan tombol "opsi lebih lanjut" di mana user dapat mengisi Nama tautan, Tag, dan Deskripsi.
![image](https://github.com/rad3nz/mamo-komdat/assets/133312076/42257160-c1e1-4b79-9a6e-962b5e24cc95)
- Saat tautan tersebut diberikan tag, nanti tampilannya akan seperti ini.
![image](https://github.com/rad3nz/mamo-komdat/assets/133312076/73c55817-d310-449a-a8ec-10939c45e840)

### Share & Collaborate
- Fitur ini terdapat 2 cara untuk berbagi tautan dengan publik dan/atau memungkinkan beberapa pengguna bekerja bersama dengan lancar. Untuk melakukannya, pertama-tama pilih folder yang ingin Anda bagikan kepada publik. Kemudian, di halaman tersebut, ada tombol "Manage Team".
![image](https://github.com/rad3nz/mamo-komdat/assets/133312076/3b9fb02b-7b51-4404-86bd-fba95e60db4a)
- Klik tombol tersebut, lalu akan muncul tampilan di mana user dapat membuat tautannya menjadi publik dengan cara mencentang/klik kotak kecil di bagian "Make Public," yang kemudian akan menampilkan public link yang dapat dicopy lalu dibagikan ke public. Selain itu, ada opsi lain di mana pengguna dapat memasukkan alamat email teman atau orang yang ingin mereka bagikan pada bagian "Member Management". Terakhir pencet tombol "Save".
![image](https://github.com/rad3nz/mamo-komdat/assets/133312076/143df8e5-e96b-4726-aaff-fc3754130d05)



## Pembahasan

Linkwarden adalah situs bookmark collection yang kaya akan fitur. Adapun kelebihan website ini adalah
- 📱 UI dan navigasi web yang mudah dipahami
- 📸 Auto Capture Screenshot dan PDF untuk link yang sudah ditambahkan
- 👥 Fitur kolaborasi dengan user lain
- 🌓 Light Mode dan **Dark Mode**
- 🌐 Collection dapat di-set menjadi **public** dan dilihat oleh umum

Untuk kekurangan yang ada dalam website ini, menurut saya hanya terbatas pada deployment website kami
dan tidak bisa dijadikan patokan untuk kualitas dan potensi riilnya yaitu:
- Saat ingin menambah kolaborator tidak bisa memverifikasi apakah user ada atau tidak saat mengisi field username
- Hasil Screenshot dan PDF untuk sebuah Link tidak ada


## Referensi

Cantumkan tiap sumber informasi yang anda pakai.

- Instalasi Docker:   https://docs.docker.com/engine/install/ubuntu/
- Instalasi WebApp:   https://docs.linkwarden.app/

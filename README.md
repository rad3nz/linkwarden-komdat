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
   berdasarkan panduan berikut : https://docs.docker.com/engine/install/ubuntu/
3. Lakukn clone pada repository Linkwarden
   ```
   git clone https://github.com/linkwarden/linkwarden.git
   ```
4. Masuk ke direktori yang sudah dibuat dengan command berikut:
   ```
   cd linkwarden
   ```
5. Buat sebuah file dengan nama `.env`
   ```
   touch .env
   ```
6. 


## Konfigurasi (opsional)

Setting server tambahan yang diperlukan untuk meningkatkan fungsi dan kinerja aplikasi, misalnya:
- batas upload file
- batas memori
- dll

Plugin untuk fungsi tambahan
- login dengan Google/Facebook
- editor Markdown
- dll


##  Maintenance (opsional)

Setting tambahan untuk maintenance secara periodik, misalnya:
- buat backup database tiap pekan
- hapus direktori sampah tiap hari
- dll


## Otomatisasi (opsional)

Skrip shell untuk otomatisasi instalasi, konfigurasi, dan maintenance.


## Cara Pemakaian
### Login Page
- Masukkan Username, Untuk memulai sesi login, masukkan username ke dalam kolom yang tersedia.
- Masukkan Password, Setelah memasukkan username, ketikkan password dengan hati-hati di kolom berikutnya.
![image](https://github.com/rad3nz/mamo-komdat/assets/133312076/8b3ee5e3-07f2-4c2d-ac8d-0b3eb56f5537)
### Dashboard
- Di dashboard atau halaman utama, akan menemukan nama situs web yang terletak di bagian header, yaitu "Stash Goods." Selain itu, di bagian header juga terdapat pesan yang memungkinkan kita untuk mengakses informasi-informasi penting dari situs web ini, serta profil kita. Selain itu, terdapat beberapa fitur-fitur lainnya yang memungkinkan untuk mengakses halaman-halaman lainnya, seperti:
    - Data Barang: kita dapat mengakses informasi tentang barang-barang yang tersedia di situs ini.
    - Entry Penjualan: Fitur ini untuk mencatat penjualan barang secara praktis.
    - Ganti Foto: Dapat mengganti foto profil Anda sesuai keinginan.
    - Ganti Password: Jika ingin mengubah kata sandi akun , kita dapat melakukannya melalui fitur ini.
    - Logout: Terakhir, jika ingin keluar dari akun, kita dapat melakukan logout melalui tombol ini.
![image](https://github.com/rad3nz/mamo-komdat/assets/133312076/ba44bf95-287c-482a-9fb1-e61803b7bbfe)

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

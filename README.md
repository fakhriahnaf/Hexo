<h1 align="center"><img src="https://oded.blog/images/2017/07/hexo-logo.png"></h1>

[Sekilas Tentang](#sekilas-tentang) | [Instalasi](#instalasi) | [Konfigurasi](#konfigurasi) | [Maintenance](#maintenance) | [Cara Pemakaian](#cara-pemakaian) | [Pembahasan](#pembahasan) | [Referensi](#referensi) | 
:---:|:---:|:---:|:---:|:---:|:---:|:---:|:---:

# Sekilas Tentang
Hexo adalah sebuah SSG (static generator) atau program mirip CMS yang digunakan untuk membuat websites statis. Hexo sendiri menggunakan nodejs sebagai platformnya. Nodejs tersebut bertindak sebagai sebuah server/backend layaknya Apache/Nginx/.Net, dll. Keuntungan dari menggunakan website statis seperti Hexo adalah selain hanya membutuhkan resource yang kecil, website statis yang digenerate via tool seperti Hexo juga menghasilkan output yang kecil, apalagi gambar dihosting menggunakan Image Hosting seperti Blogger, Google Photos dan CDN Hosting lainnya.

## Fitur
- Sangat cepat untuk dibuat
- Mendukung GitHub Flavoured Markdown dan sebagian besar plugin Octopress
- One-command deploy ke GitHub Pages, Heroku, dan lain-lain
- Sistem plugin yang kuat


# Instalasi

##### Prasyarat, apa saja yang harus diinstal sebelumnya.

- Sebelum menginstall hexo pertama - tama praktikan melakukan instalasi ubuntu server 14.0.* di virtual box dengan konfigurasi pada tab network seperti berikut :
- Terinstall ssh di sisi client remote.
- Lalu, praktikan menginstall nodejs versi 6.x dan npm melaui padaserver melalui remote client menggunakan ssh. 

##### Langkah instalasi dalam CLI :

- Pertama - tama praktikan melakukan login ke server menggunakan ssh :
```
$ ssh student@localhost -p 2222
```
- Lalu memasukkan password : student.
- Setelah itu praktikan meng-install nodejs dengan mendownload file .deb  versi 6.x dengan metode cURL :
```
$ curl -sL https://deb.nodesource.com/setup_6.x | sudo -E bash -
```
- setelah selesai mendownload file praktikan menginstallnya :
```
$ sudo apt-get install nodejs
```
- setelah node js terinstall, lalu praktikan meng install npm (node package manager ) :
```
$ sudo apt-get install npm
```
- Setelah menginstall npm dan nodeJS, lalu prak tikan meng install cli hexo :
```
$ npm install -g hexo-cli
```
- Selelah CLI Hexo ter install lalu praktikan membuat projek folder hexo pada server dengan mengetikkan command seperti berikut : 
```
$ hexo init blog
```
- Setelah hexo ter install maka kita masuk ke folder projek hexo kita melalui server :
```
$ cd blog
```
- Lalu install hexo secara local di folder projek dengan npm :
```
$ npm install hexo --save
```
- Lalu start server hexo kita :
```
$ hexo server
```
- Kemudian hexo kita akan di running di server
![](https://i.imgur.com/sb8y9YV.png)
- lalu kita akses di sisi client melalui http://localhost:8888/, yang dimana port 8888 telah disesuaikan httpnya ke port 4000 pada server.

##### Konfigurasi (opsional)

Setting tambahan yang diperlukan untuk meningkatkan fungsi dan kinerja aplikasi, misalnya:
- Batas upload file
Hexo menyediakan space hosting gratis berukuran antara 5mb-10mb.
- Plugin untuk fungsi tambahan
Plugin tema


# Maintenance
## Menambahkan password
Jika Anda menggunakan plugin [hexo-admin](https://github.com/jaredly/hexo-admin) di live server Anda, Anda perlu perlindungan kata sandi. Untuk mengaktifkannya, Anda cukup menambahkan beberapa variabel konfigurasi ke hexo `_config.yml` Anda:
``` bash
admin:
  username: myfavoritename
  password_hash: be121740bf988b2225a313fa1f107ca1
  secret: a secret something
```
Password_hash adalah sebuah bcrypt hash dari kata sandi Anda. Secret digunakan untuk membuat cookie aman, lebih baik jika dibuat panjang dan rumit.

Sebuah utility di Pengaturan admin Hexo dapat melakukan hash pada kata sandi Anda dan membuat `admin` section untuk Anda. Mulai Hexo dan pergi ke `Settings > Setup authentification` dan isi informasi Anda. Salin YAML yang dihasilkan ke `_config.yml` Anda.

Setelah itu, mulai server hexo Anda dan pergi ke `/admin/`, Anda akan diminta untuk memasukkan kata sandi.

## Melakukan kustomisasi post metadata
Untuk menambah dan mengedit post metadata Anda dengan antarmuka admin, tambahkan variabel metadata dan variabel khusus Anda ke hexo `_config.yml` Anda:
``` bash
metadata:
  author_id: defaultAuthorId
  language:
```
Anda dapat memberikan nilai default yang akan digunakan untuk menginisialisasi metadata dari postingan baru. Nilai dapat berupa primitif atau array.

# Cara Pemakaian
- Tampilan aplikasi web
![](https://i.imgur.com/ChGeQdj.png)
- Fungsi - fungsi utama
	- Membuat post baru:
		- Membuat post baru di Hexo menggunakan cli seperti berikut dari sisi client :
		`$ hexo new "My New Post"`
		- Lalu akan keluar seperti berikut :
		`Created: ~/blog/source/_posts/My-New-Post.md`
		- Untuk mengeditnya praktikan menggunakan nano :
		`nano My-New-Post.md`
		![](https://i.imgur.com/oqnfAou.png)
		- Setelah di edit lalu praktikan menyimpannya.
		- Setelah itu praktikan mendeploynya : 
		`$ hexo deploy`
		- Maka akan muncul post baru
# Pembahasan

# Referensi
Ada aplikasi sejenis yang juga menggunakan SSG yaitu Hugo. Hugo sendiri untuk men-deploy website yang sudah jadi ke hosting pribadi harus manual menggunakan FTP. Lain halnya dengan Hexo, aplikasi SSG yang dibuat menggunakan nodejs ini memiliki plugin yang bisa deploy website dengan banyak cara salah satunya dengan FTP. Sama seperti halnya jika push file melalui metode git, deploy file website menggunakan plugin yang disediakan Hexo membuat blogging jadi lebih mudah.

Menggunakan Hexo (atau statis website lainnya) memberikan keuntungan dalam hal SEO karena dengan menggunakan website statis, kita bisa memanfaatkan hosting gratis yang space kecil (antara 5mb-10mb). Website statis yang dihasilkan oleh Hugo dan Hexo juga bisa digunakan pada server yang tidak mendukung PHP server seperti Apache, Nginx, Litespeed, dll.




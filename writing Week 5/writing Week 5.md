# **Writing & Presentation Week 5**

## Web Server & RESTFUL API
### WEB SERVER
- Web Server adalah suatu perangkat lunak (software) dalam server yang berfungsi untuk menerima permintaan (request) dari client atau browser berupa halaman website melalui protokol HTTP/ HTTPS, lalu merespon permintaan tersebut dalam bentuk halaman website berupa dokumen HTML atau PHP.
- Web server terdiri dari 2 komponen penting:
    - Hardware
    - Software
- Server HTTP adalah perangkat lunak yang memahami URL (alamat web) dan HTTP (protokol yang digunakan browser Anda untuk melihat halaman web).

### **Static Web Server VS Dynamic Web Server**
- Static Web Server, atau stack, terdiri dari komputer (perangkat keras) dengan server HTTP (perangkat lunak). disebut "static" karena server mengirimkan file yang dihosting apa adanya ke browser.

    <br>
- Dynamic Web Server terdiri dari server web static ditambah perangkat lunak tambahan, paling sering server aplikasi dan database. disebut "dynamic" karena server aplikasi memperbarui file yang dihosting sebelum mengirim konten ke browser Anda melalui server HTTP

### **Server Side Programming**
- Server web menunggu pesan permintaan klien, memprosesnya saat tiba, dan membalas browser web dengan pesan respons HTTP. Respons berisi baris status yang menunjukkan apakah permintaan berhasil atau tidak (mis. "HTTP/1.1 200 OK" untuk berhasil).

    <div align="justify">Isi respons yang berhasil atas permintaan akan berisi sumber daya yang diminta (misalnya halaman HTML baru, atau gambar, dll...), yang kemudian dapat ditampilkan oleh browser web.
    
    <br>
- Static Sites
    <div align="justify">Menunjukkan arsitektur web server dasar untuk situs static (situs static adalah situs yang mengembalikan konten hard-coded yang sama dari server setiap kali sumber daya tertentu diminta).
    
    <br>
- Dynamic Site
    <div align="justify">Dynamic Website adalah situs di mana beberapa konten respons dihasilkan secara dinamis, hanya bila diperlukan.


### **Yang dapat Anda lakukan di server-side**
- Efficient storage and delivery of information
- Customised user experience
- Controlled access to content
- Store session/state information
- Notifications and communication
- Data analysis

### **REST**
- REST, atau Representational State Transfer, adalah gaya arsitektur untuk menyediakan standar antara sistem komputer di web, sehingga memudahkan sistem untuk berkomunikasi satu sama lain.
- Sistem yang sesuai dengan REST, sering disebut sistem RESTful, dicirikan oleh bagaimana mereka tidak memiliki kewarganegaraan dan memisahkan masalah klien dan server


### **Komunikasi antara Klien dan Server**
- **Membuat permintaan**
    <div align="justify">REST mengharuskan klien membuat permintaan ke server untuk mengambil atau mengubah data di server. Permintaan umumnya terdiri dari:

    - kata kerja HTTP, yang mendefinisikan jenis operasi apa yang harus dilakukan
    - header, yang memungkinkan klien untuk menyampaikan informasi tentang permintaan
    - jalan menuju sumber daya
    - badan pesan opsional yang berisi data
- **HTTP VERBS**
    <div align="justify">Ada 4 kata kerja HTTP dasar yang kami gunakan dalam permintaan :

    - GET — mengambil sumber daya tertentu (berdasarkan id) atau kumpulan sumber daya
    - POST — buat sumber daya baru
    - PUT — perbarui sumber daya tertentu (berdasarkan id)
    - DELETE — menghapus sumber daya tertentu dengan id

### **Headers and Accept Parameters**
- Di header permintaan, klien mengirimkan jenis konten yang dapat diterimanya dari server.
- Ini disebut bidang Terima, dan ini memastikan bahwa server tidak mengirim data yang tidak dapat dipahami atau diproses oleh klien. Opsi untuk tipe konten adalah Tipe MIME.

### **Paths**
- Permintaan harus berisi jalur ke sumber daya tempat operasi harus dilakukan. Dalam RESTful API, jalur harus dirancang untuk membantu klien mengetahui apa yang sedang terjadi.
### **Sending Responses**
- Content Types
    <div align="justify">Misalnya, ketika klien mengakses sumber daya dengan id 23 di sumber artikel dengan Permintaan GET ini:

    DAPATKAN /artikel/23 HTTP/1.1
    Terima: teks/html, aplikasi/xhtml

    Server mungkin mengirim kembali konten dengan header respons:

    HTTP/1.1 200 (Oke)
    Tipe-Konten: teks/html
- Response Codes
    <div align="justify">Tanggapan dari server berisi kode status untuk memperingatkan klien tentang informasi tentang keberhasilan operasi.

    <div align="justify">Untuk setiap kata kerja HTTP, ada kode status yang diharapkan yang harus dikembalikan server setelah berhasil:

    - GET — kembalikan 200 (OK)
    - POST — kembalikan 201 (DIBUAT)
    - PUT — kembalikan 200 (OK)
    - DELETE — return 204 (NO CONTENT) Jika operasi gagal, kembalikan kode status paling spesifik yang mungkin terkait dengan masalah yang ditemui.

<hr>

## **Node JS**<hr>

1. Node js merupakan runtime javascript yang digunakan oleh back-end developer yang dibangun di JS engine yang bernama V8, lalu V8 tersebut dari web browser Chrome.
2. Runtime = menjalankan / meng eksekusi kode yang dibuat.
3. Ditemukan oleh Ryan Dahl (2009)
4. Build in module Node JS
   - Console
   - Process
   - OS
   - File System
   - Events
   - Util
5. Menginstal package/library `npm init` atau `npm i [nama package]`
6. Membuat web Server <br>
   ```javascript
       let a = require(`http`);
       a.createserver((req, res) => {
       res.write(`hallo`);
       res.end(); // untuk menghentikan respon agar tidak terjadi stuck
       });
        .listen(/*port*/, () => {
        console.log("data berhasil");
       });
   ```
7. `createserver` sebagai ngembaliin instance dari server.
8. `.listen` ngejalanin server dan mulai connect/aktif.

## **Express Js Routing dan Middleware**<hr>

1. Express merupakan framework untuk back-end atau web server yang dibangun di node js melalui jalur API.
2. Framework node = `npm isntall express`
3. Framework untuk development `npm install nodemon`
4. Middleware merupaka sebuah function yang bisa digunakan untuk memodifikasi Object Request & Object Response.
5. Nodemon digunakan untuk development sebagai running program di node js.
6. Menggunakan express js : <br>

   - Buka vscode, new terminal `npm init`
   - instal expreess js `npm instal express`
   - buat file idx.js,

     ```javascript
     const express = require("express");
     const idx = express();
     const PORT = 7000;

     //  running port
     idx.listen(PORT, () => {
       console.log("running port " + PORT);
     });
     ```

   - Setting script di file package.json

     ```javascript
         {
           "name": "minggu_5",
           "version": "1.0.0",
           "description": "",
           "main": "index.js",
               "scripts": {
               "test": "echo \"Error: no test specified\" && exit 1",
               "start": "node idx.js",
               "dev": "nodemon idx.js"
           },
           "author": "Guntur",
           "license": "ISC",
           "dependencies": {
             "express": "^4.18.2"
           },
            // setelah di instal npm nodemon
           "devDependencies": {
             "nodemon": "^2.0.20"
           }
         }

     ```

   - instal nodemon untuk development `npm i -D nodemon` lanjut dengan `npm run dev` untuk menjalankan nodemon.


## **Design Database with MySQL**
### **Menentukan Entity**
- Berdasarkan requirement yang ada kita bisa mulai untuk mengidentifikasi entity dalam database.
- Beberapa kandidat yang paling sering menjadi sebuah entity : peoples, things, events, locations
- Mari kita lihat kembali requirement yang ada, dan kita mulai list entity yang ada.
- Berikut adalah kandidat yang bisa dijadikan enitity dalam database :
    - User
    - Singer
    - Track
    - Album
    - Playlist
 ### **Menentukan Atribbutes dari Entity**
- Menentukan attributes apa saja yang akan datanya kita simpan di dalam sebuah entity.
- Attributes yang di perlukan didalam entity kemungkinan sudah ada di dalam requirements document, atau mungkin juga diperlukan penafsiran kita sendiri sebagai database developer.
### **Menentukan Relasi Antar Entity**
- Didalam requrement mungkin sudah dijelaskan relasi dari beberapa entity.
- Namun terkadang didalam requirement juga tidak dijelaskan mengenai relasi, dan kita sebagai database developer menafsirkan relasi antar entity
### **Membuat SQL Table dari Entity**
- Setelah kita punya ERD, maka kita akan lanjut dengan create table berdasarkan dengan data yang kita punya.
- Pada kali ini kita akan menggunakan terminal untuk menjalankan query SQL
. Membuat table <br>
   - Mahasiswa
     ```sql
     create table mahasiswa(
         -> Nim int,
         -> nama varchar,
         -> Jurusan varchar,
         -> PRIMARY KEY(Nim);
     ```
   - Matakuliah
     ```sql
     create table matakuliah(
         -> Id int,
         -> Matkul varchar,
         -> sks int,
         -> PRIMARY KEY(Id);
     ```
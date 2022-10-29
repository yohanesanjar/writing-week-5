# Yohanes Anjar Dewantara - BE 15
# writing-week6

# Web Server dan RESTful API

## Web Server
### Komponen Web Server
- Hardware
  > Di sisi hardware, server web adalah komputer yang menyimpan perangkat lunak server web dan file komponen situs web. (misalnya, dokumen HTML, gambar, CSS stylesheet, dan file JavaScript) Server web terhubung ke Internet dan mendukung pertukaran data fisik dengan perangkat lain yang terhubung ke web.
- Software
  > Di sisi software, server web mencakup beberapa bagian yang mengontrol bagaimana pengguna web mengakses file yang dihosting. Minimal, ini adalah server HTTP. Server HTTP adalah perangkat lunak yang memahami URL (alamat web) dan HTTP (protokol yang digunakan browser Anda untuk melihat halaman web). Server HTTP dapat diakses melalui nama domain situs web yang disimpannya, dan mengirimkan konten situs web yang dihosting ini ke perangkat pengguna akhir.
### Static Web Server VS Dynamic Web Server
- Static Web Server
  > Static Web Server, terdiri dari komputer (perangkat keras) dengan server HTTP (perangkat lunak). Kami menyebutnya "statis" karena server mengirimkan file yang dihosting apa adanya ke browser Anda.
- Dynamic Web Server
  > Sebuah server web dinamis terdiri dari server web statis ditambah perangkat lunak tambahan, paling sering server aplikasi dan database. Kami menyebutnya "dinamis" karena server aplikasi memperbarui file yang dihosting sebelum mengirim konten ke browser Anda melalui server HTTP
### Server Side Programming
>Web Server menunggu pesan permintaan klien, memprosesnya saat tiba, dan membalas browser web dengan pesan respons HTTP. Respons berisi baris status yang menunjukkan apakah permintaan berhasil atau tidak (misal "HTTP/1.1 200 OK" untuk berhasil). Isi respons yang berhasil atas permintaan akan berisi sumber daya yang diminta (misalnya halaman HTML baru, atau gambar, dll...), yang kemudian dapat ditampilkan oleh web browser.
### Static Sites
> Static sites menggunakan rendering sisi server untuk menyajikan file HTML, CSS, dan JavaScript yang telah dibuat sebelumnya ke browser web, berbeda dengan situs dinamis tradisional yang bekerja dengan merender halaman web pada saat permintaan.
### Dynamic Sites
> Dynamic sites adalah situs di mana beberapa konten respons dihasilkan secara dinamis, hanya bila diperlukan. Di situs web dinamis, halaman HTML biasanya dibuat dengan memasukkan data dari database ke dalam placeholder di template HTML (ini adalah cara yang jauh lebih efisien untuk menyimpan konten dalam jumlah besar daripada menggunakan situs web statis).
### Perbedaan Static Sites dan Dynamic Sites
- Memiliki tujuan dan perhatian yang berbeda.
- Umumnya tidak menggunakan bahasa pemrograman yang sama (pengecualiannya adalah JavaScript, yang dapat digunakan di sisi server dan klien).
- Berjalan di dalam sistem operasi yang berbeda.
### Yang dapat dilakukan di server-side
- Penyimpanan dan pengiriman informasi yang efisien
- Mengkostumisasi UX
- Akses terkontrol ke konten
- Store session/state information
- Notifikasi dan komunikasi
- Data analysis

## RESTful API
### Pengertian REST
- REST, atau REpresentational State Transfer, adalah gaya arsitektur untuk menyediakan standar antara sistem komputer di web, sehingga memudahkan sistem untuk berkomunikasi satu sama lain.
- Sistem yang sesuai dengan REST, sering disebut sistem RESTful, dicirikan oleh bagaimana mereka tidak memiliki kewarganegaraan dan memisahkan masalah klien dan server
### Komunikasi antara Klien dan Server
- Membuat Requests
  - REST mengharuskan klien membuat permintaan ke server untuk mengambil atau mengubah data di server. Permintaan umumnya terdiri dari:
    - kata kerja HTTP, yang mendefinisikan jenis operasi apa yang harus dilakukan
    - Header, yang memungkinkan klien untuk menyampaikan informasi tentang permintaan jalan menuju sumber daya
    - jalan menuju sumber daya
    - badan pesan opsional yang berisi data
- Kata Kerja HTTP
  - Ada 4 kata kerja HTTP dasar yang digunakan dalam permintaan untuk berinteraksi dengan sumber daya dalam sistem REST
    1. GET — mengambil resource tertentu (berdasarkan id) atau kumpulan sumber daya
    2. POST — membuat resource baru
    3. PUT — memperbarui resource tertentu (berdasarkan id)
    4. DELETE — menghapus resource tertentu dengan id
### Parameter Headers dan Accept
- Di header permintaan, klien mengirimkan jenis konten yang dapat diterimanya dari server. Ini disebut bidang Terima, dan ini memastikan bahwa server tidak mengirim data yang tidak dapat dipahami atau diproses oleh klien.
- Tipe lain dan subtipe yang umum digunakan :
  - image — image/png, image/jpeg, image/gif
  - audio — audio/wav, audio/mpeg
  - video — video/mp4, video/ogg
  - application — application/json, application/pdf, application/xml, application/octet-stream
### Paths
- Permintaan harus berisi jalur ke sumber daya tempat operasi harus dilakukan. Dalam RESTful API, jalur harus dirancang untuk membantu klien mengetahui apa yang sedang terjadi.
- Path seperti skilvulstore.com/customers/223/orders/12 jelas dalam apa yang ditunjuknya, bahkan jika Anda belum pernah melihat path khusus ini sebelumnya, karena path ini bersifat hierarkis dan deskriptif.
### Sending Responses
- Tipe Content
  - Misalnya, ketika klien mengakses resource dengan id 23 di sumber artikel dengan Permintaan GET ini:
    ```
    GET /articles/23 HTTP/1.1
    Accept: text/html, application/xhtml
    ```
    Server akan mengirim kembali konten dengan header respons :
    ```
    HTTP/1.1 200 (OK)
    Content-Type: text/html
    ```
### Response Codes
- Untuk setiap kata kerja HTTP, ada kode status yang diharapkan yang harus dikembalikan server setelah berhasil :
  1. GET — return 200 (OK)
  2. POST — return 201 (CREATED)
  3. PUT — return 200 (OK)
  4. DELETE — return 204 (NO CONTENT) jika operasi gagal, kembalikan kode status paling spesifik yang mungkin terkait dengan masalah yang ditemui.

![image](https://user-images.githubusercontent.com/100120189/198830026-d6280164-ebb4-49fe-9716-19660397b21e.png)

## Intro Node.Js
### Tools
- Visual Studio Code (code editor)
- Browser latest version (Chrome, mozilla, opera, dll)
- Command Line Iinterface (mac / linux : terminal, windows : cmd)
- Node JS - https://nodejs.org/en
### Pengertian
> Node.js adalah open-source, lintas platform, back-end Javascript yang berjalan pada V8 engine dan mengeksekusi kode JavaScript di luar browser web. Node.js memungkinkan pengembang menggunakan JavaScript untuk menulis command line tools dan untuk skrip sisi server—menjalankan skrip sisi server untuk menghasilkan konten halaman web dinamis sebelum halaman dikirim ke browser web pengguna.
### Node JS Architecture
- **Single Thread**
  - Thread dalam ilmu komputer adalah eksekusi menjalankan beberapa tugas atau program secara bersamaan. Setiap unit yang mampu mengeksekusi kode disebut thread. Javascript menggunakan konsep single thread, yang berarti hanya memiliki satu tumpukan panggilan yang digunakan untuk menjalankan program.
- **Even Loop**
  - Dengan menggunakan konsep arsitektur javascript, walaupun menggunakan single thread tetapi kita dapat melihat javascript seperti menggunakan multi thread
  - Terdapat event queue yang berguna sebagai penampung ketika terdapat perintah baru yang akan dieksekusi.
  - Event loop akan memfasilitasi kondisi ini, event loop akan memeriksa terus menerus, ketika antrian kosong di call stack maka akan menambah antrian baru dari event queue sampai semua perintah selesai di eksekusi.
- **Server side scripting**
  - Sejatinya javascript merupakan bahasa pemrograman yang digunakan di front end side. Sehingga kita hanya bisa mengerjakan javascript dengan menggunakan browser untuk menampilkan hasil eksekusinya. Tetapi dengan menggunakan NodeJS kita dapat menjalankan javascript di server side menggunakan terminal command line menggunakan perintah “node”.
### Javascript For Node JS
- **Arrow Expression**
  > Arrow expression merupakan fitur terbaru dari javascript, yaitu mempermudah membuat sintaks function menggunakan “=>”
- **Asynchronous**
  > Asynchronous merupakan konsep yang paling penting dari javascript. Pada dasarnya, javascript mengeksekusi code secara single thread dan berurutan baris per baris yang disebut dengan synchronous. Sedangkan asynchronous memungkinkan mengeksekusi code tanpa berurutan dengan cara “skip” code dan melanjutkan eksekusi code selanjutnya. Konsep ini menungkinkan code kita tidak terjadi blocking dan lebih efisien.
- **JSON**
  > JSON atau Javascript Object Notation merupakan format yang digunakan untuk menyimpan dan mengirim data menggunakan konsep object di javascript. JSON dapat digunakan di hampir semua bahasa pemrograman sehingga sangat cocok untuk dipelajari
### Build In Module Node JS
- **Console**
  - Console merupakan module bawaan dari javascript yang ada di node JS untuk digunakan sebagai debug atau menampilkan code secara interface
  - Contoh :
    ```
    console.log("ini adalah console")
    ```
- **Process**
  - Process adalah modules yang digunakan untuk menampilkan dan mengontrol prosess Node JS yang sedang dijalankan.
  - Contoh :
    ```
    const process = require('process')
    const env = process.env
    
    env.foo = 'bar'
    console.log(env.foo) // bar
    ```
- **OS**
  - OS module merupakan module yang digunakan untuk menyediakan informasi terkait sistem operasi komputer yang digunakan user.
  - Contoh :
    ```
    let os = require('os')
    console.log("Platform: " + os.platform())
    console.log("Architecture: " + os.arch())
    
    //Platform: Darwin
    //Architecture: x64
    ```
- **Util**
  - Module Util merupakan alat bantu / utilities untuk mendukung kebutuhan internal API di Node JS
  - Contoh :
    ```
    const util = require('util')
    const debuglog = util.debuglog('foo')
    
    debuglog('hello from foo [%d]', 123)
    //FOO 3245 : hello from foo [123]
    ```
- **Events**
  - Contoh :
    ```
    const EvenEmitter = require('events')
    class myEmitter extends evenEmitter {}
    
    const myEmitter = new myEmitter()
    myEmitter.on('event', () => {
      console.log('an event occured!')
    })
    myEmitter.emit('event')
    ```
- **Errors**
  - Errors merupakan modules yang dapat digunakan untuk mendefinisikan error di Node JS sehingga lebih informatif. Kita juga dapat menghandle error menggunakan try catch
  - Contoh :
    ```
    try {
      const m = 1
      const n = m +
    } catch (err) {
      //handle error
    }
    ```
- **Buffer**
  - Buffer merupakan modules yang digunakan untuk mengakses, mengelola dan mengubah tipe data raw atau tipe data bytes.
  - Contoh :
    ```
    import { Buffer } from 'buffer'
    const buf = Buffer.from('hello world','utf8')
    console.log(buf.toString('hex'))
    console.log(buf.toString('base64'))
    ```
- **FS**
  - Fs atau “file system” merupakan module yang dapat membantu berinteraksi dengan file yang ada diluar code. FS paling sering digunakan untuk membaca file dengan ekstensi .txt, .csv, dan .json
  - Contoh :
    ```
    import { readFileSyny } from 'fs'
    readFileSync('<directory>')
    ```
- **Timers**
  - Timers merupakan modules yang digunakan untuk melakukan scheduling atau mengatur waktu pemanggilan fungsi yang dapat diatur di waktu tertentu
  - Contoh :
    ```
    import{
      setTimeout,
    } from 'timers/promises'
    const res = await setTimeout(100, 'result')
    console.log(res)
    //Prints 'result'
    ```
### Membuat Web Server Dengan Node JS
- **Node JS Web Server**
  - Node.js memiliki built-in modul yang disebut HTTP, built-in modul ini memungkinkan Node JS mentransfer data melalui Hyper Text Transfer Protocol (HTTP).
  - Modul HTTP dapat membuat server HTTP yang mendengarkan port server dan memberikan respons kembali ke klien.
  - Untuk menggunakan modul HTTP, gunakan require()
  - Gunakan method createServer() untuk membuat server HTTP
  - Callback function yang digunakan pada method http.createServer(), akan dijalankan ketika seseorang mencoba mengakses komputer pada port 8080.
  - Contoh :
    ```
    const http = require('http')
    
    http.createServer(function(req, res) => {
      res.write('Hello World')
      res.end()
    }).listen(8080)
    ```
- **Menambahkan HTTP Header**
  - Kita bisa menggunakan method res.writeHead() untuk menambahkan header HTTP.
  - Argumen pertama dari method res.writeHead() adalah status code, 200 berarti semuanya OK
  - Argumen kedua adalah objek yang berisi header respons.
  - Contoh : 
    ```
    const http = require('http')
    
    http.createServer(function(req, res) => {
      res.writeHead(200, {'Content-Type': 'text/html'})
      res.write('Hello World')
      res.end()
    }).listen(8080)
    ```
  - Respons yang dikembalikan dari HTTP web server bisa dalam berbagai format.
  - Contohnya, Kita bisa mengembalikan response dalam format JSON dan HTML, namun kita juga dapat mengembalikan format teks lain seperti XML dan CSV.
  - Selain itu web server dapat mengembalikan data non-teks seperti PDF, file zip, audio, dan video.
  - Format ini harus ditambahkan kedalam HTTP Header.
- **Membaca Query String**
  - Callback function pada method http.createServer() memiliki argumen req yang mewakili request dari klien, sebagai objek (objek http.IncomingMessage).
  - Objek ini memiliki sebuah properti yang disebut "url" yang menyimpan informasi url yang sedang mengakses.
  - Contoh :
    ```
    const http = require('http')
    
    http.createServer(function(req, res) => {
      res.writeHead(200, {'Content-Type': 'text/html'})
      res.write(req.url)
      res.end()
    }).listen(8080)
    ```
- **Split Query String**
  - Ada build-in module yang bisa kita gunakan untuk split query string menjadi beberapa bagian yang dapat dibaca.
  - Build-in modulenya adalah URL Module.
  - Contoh :
    ```
    const http : require('http')
    const url : require('url')
    
    http.createServer(function(req, res) => {
      res.writeHead(200, {'Content-Type': 'text/html'})
      const query = url.parse(req.url, true).query
      let txt = q.year + " " + q.month 
      res.end(txt)
    }).listen(8080)
    ```

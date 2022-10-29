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

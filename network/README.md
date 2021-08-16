# Network

Amazon Virtual Private Cloud (Amazon VPC) memungkinkan untuk menyediakan bagian logis dari AWS Cloud yang terisolasi, di mana Anda dapat meluncurkan sumber daya AWS di jaringan virtual sesuai kebutuhan.

Sumber daya tersebut dapat menjadi public-facing yang berarti memiliki akses ke internet ataupun private alias tanpa akses internet.

Pengelompokan sumber daya menjadi publik dan privat ini disebut dengan subnet yang juga merupakan rentang alamat IP di VPC.

Anda bisa saja memiliki sumber daya yang internet-facing (terhubung ke internet) sehingga dapat dijangkau oleh umum, seperti website publik.

Namun, dalam skenario lain, Anda mungkin ingin memiliki sumber daya yang hanya Anda saja yang dapat menjangkaunya. Ini mungkin pas untuk layanan internal, seperti aplikasi HRD atau database.

## Internet Gateway

Untuk mengizinkan traffic dari internet publik mengalir masuk dan keluar dari VPC, Anda harus melampirkan apa yang disebut dengan Internet Gateway (IGW). Di bawah ini adalah contoh arsitektur yang menggunakan Internet Gateway.

![](https://d17ivq9b7rppb3.cloudfront.net/original/academy/20210310160547b068b89607a727456c38340e2290933d.png)

## Virtual Private Gateway

Anda bisa memasang gateway privat yang hanya mengizinkan masuk suatu permintaan jika ia berasal dari jaringan yang disetujui, bukan internet publik.

Gateway privat ini disebut juga dengan virtual private gateway. Ia memudahkan Anda untuk membuat koneksi VPN (virtual private network) terenkripsi antara jaringan privat--seperti data center on-premise atau jaringan perusahaan internal--ke VPC Anda.

Jadi, dapat disederhanakan bahwa virtual private gateway adalah komponen yang memungkinkan traffic internet yang terlindungi masuk ke dalam VPC.

![](https://d17ivq9b7rppb3.cloudfront.net/original/academy/20210310160717f55c748910c59b07d4dd579c4b2101da.png)

Koneksi VPN bersifat pribadi dan dienkripsi, tetapi faktanya ia masih menggunakan koneksi internet reguler dengan bandwidth (jumlah maksimum data yang dapat dikirim) yang terbagi kepada banyak pengguna internet lainnya.

## AWS Direct Connect

Jika Anda menginginkan koneksi privat, koneksi terdedikasi, jumlah latensi yang rendah, dan tingkat keamanan yang tinggi, maka Anda bisa mewujudkannya di AWS dengan menggunakan AWS Direct Connect.

![](https://d17ivq9b7rppb3.cloudfront.net/original/academy/20210310160759b1b2ea1ee5556519543d26c7d22ed4c8.png)

AWS Direct Connect memungkinkan Anda untuk membuat koneksi fiber yang privat nan terdedikasi sepenuhnya antara data center Anda dan VPC. Untuk membangun koneksi tersebut, Anda perlu berpartner dengan mitra Direct Connect yang tersedia di wilayah Anda.

Dengan demikian, layanan ini dapat membantu Anda memenuhi kebutuhan regulasi dan kepatuhan yang tinggi serta menghindari potensi masalah pada bandwidth.

## Subnet

Subnet adalah sebuah bagian dari VPC di mana Anda dapat mengelompokkan sumber daya berdasarkan keamanan atau kebutuhan operasional. Subnet bisa menjadi publik maupun privat.

Di VPC subnet dapat berkomunikasi satu sama lain. Misalnya, Anda dapat memiliki aplikasi pada Amazon EC2 instance di subnet publik yang berkomunikasi dengan database di subnet pribadi.

## Network Access Control List (Network ACL)

Satu-satunya alasan teknis untuk menggunakan subnet di VPC adalah untuk mengontrol akses ke gateway. Subnet publik memiliki akses ke Internet Gateway, sementara Subnet privat tidak. Tapi walaupun begitu, subnet juga bisa mengontrol perizinan traffic.

Ketika pelanggan meminta data dari aplikasi yang berjalan di AWS Cloud, maka permintaan ini dikirim sebagai paket. Paket adalah sebuah unit data yang dikirim melalui internet atau jaringan.

![](https://d17ivq9b7rppb3.cloudfront.net/original/academy/202103101612444d839af795a92a8aef280b8f628d6a4e.png)

Paket masuk ke VPC melalui Internet Gateway. Sebelum paket dapat masuk atau keluar dari subnet, ia akan diperiksa terkait perizinannya. Pemeriksaan ini dilakukan untuk melihat apakah paket memiliki izin untuk masuk ke subnet berdasarkan siapa pengirimnya dan bagaimana ia mencoba berkomunikasi dengan sumber daya yang berada di subnet.

Komponen VPC yang memeriksa izin paket untuk subnet adalah network access control list alias network ACL. Network ACL adalah firewall virtual yang mengontrol traffic masuk dan keluar di tingkat subnet. Tentu ini berbeda dengan Internet Gateway yang cakupannya di tingkat VPC.

Jika paket memiliki potensi yang dapat membahayakan sumber daya di dalam subnet--seperti upaya untuk menguasai sistem melalui permintaan administratif--maka ia akan diblokir sebelum dapat menyentuh target.

Selain memeriksa traffic yang masuk, network ACL pun akan mengecek setiap traffic yang keluar dari subnet.

Setiap akun AWS menyertakan network ACL secara default (bawaan). Saat mengonfigurasi VPC, Anda dapat menggunakan default network ACL (mengizinkan semua traffic masuk dan keluar) atau custom network ACL (menolak semua traffic masuk dan keluar hingga Anda secara eksplisit mengizinkannya).

Selain itu, network ACL memiliki aturan penolakan secara eksplisit. Aturan ini berguna untuk memastikan jika sebuah paket tidak cocok dengan salah satu aturan lain di daftar, paket tersebut akan ditolak.

>NOTE: Network ACL hanya dapat mengevaluasi paket jika melintasi batas subnet--baik masuk atau keluar namun tidak tahu-menahu apakah paket tersebut dapat mencapai EC2 instance tertentu atau tidak.

## Security Group

Security group adalah firewall virtual yang mengontrol traffic masuk dan keluar untuk Amazon EC2 instance. Terlihat berbeda ya dengan network ACL yang cakupannya di tingkat subnet.

![](https://d17ivq9b7rppb3.cloudfront.net/original/academy/20210310161531e35fa09c172d32de5182337c5e1ed0c6.png)

Saat EC2 instance diluncurkan, ia secara otomatis dilengkapi dengan security group. Jika Anda memiliki beberapa Amazon EC2 instance di dalam subnet yang sama, Anda dapat mengaitkannya dengan security group yang sama maupun berbeda untuk setiap instance.

Dengan security group default, semua port dan alamat IP yang mengirimkan paket akan diblokir. Tentu ini sangat aman, tapi mungkin membuat instance tidak berguna. Maka dari itu, tentu Anda bisa mengonfigurasinya dengan menambah aturan sendiri yang mengizinkan atau menolak traffic sesuai kebutuhan.

Perbedaan utama antara security group dan network ACL adalah:

* Security group bersifat stateful, yang berarti ia memiliki semacam memori untuk mengingat siapa yang diizinkan masuk atau keluar.
* Network ACL bersifat stateless, artinya ia tidak mengingat apa pun. Layanan ini akan memeriksa setiap paket yang melintasi perbatasannya terlepas dari keadaan apa pun.

## Domain Name System (DNS)

DNS menerjemahkan sebuah nama domain ke dalam alamat IP (Internet Protocol) yang dapat dibaca komputer.

![](https://d17ivq9b7rppb3.cloudfront.net/original/academy/20210310164623c3c9bd41216e260b0c0511dae839cde6.png)

## Amazon Route 53

Amazon Route 53 adalah layanan domain name system (DNS) atau sistem nama domain di AWS yang highly available (sangat tersedia) dan scalable (dapat diskalakan). Layanan ini dapat memberikan Anda cara yang andal untuk merutekan pelanggan ke aplikasi internet yang berjalan di AWS.

Amazon Route 53 bertugas untuk menghubungkan permintaan pelanggan ke infrastruktur yang berjalan di AWS (seperti Amazon EC2 instance dan load balancers) atau ia bisa pula mengarahkan pelanggan ke infrastruktur yang berada di luar AWS.

Jika kita melangkah lebih jauh, Amazon Route 53 itu dapat pula mengarahkan traffic ke endpoints (titik akhir) yang berbeda menggunakan beberapa routing policies (kebijakan perutean) yang berbeda, seperti:

* Latency-based routing (Perutean berbasis latensi)
* Geolocation DNS
* Geoproximity routing
* Weighted round robin

Contoh dari Geolocation DNS, kita mengarahkan traffic berdasarkan lokasi pelanggan. Lalu lintas yang datang dari Indonesia akan dialihkan ke Region Singapura atau jika berasal dari Jepang akan dialihkan ke Region Tokyo.

Selain mengarahkan traffic, Route 53 dapat digunakan untuk mendaftarkan nama domain baru atau menggunakan nama domain yang Anda miliki. Sehingga, ini memudahkan Anda untuk mengelola semua nama domain dalam satu lokasi.

## Amazon CloudFront

Amazon CloudFront adalah layanan yang dapat membantu Anda untuk mengirimkan konten (data, aplikasi, maupun API) ke pelanggan di seluruh dunia dengan aman dan latensi rendah. Konten yang dimaksud ini bisa berbagai hal, seperti data, video, aplikasi, dan API.

Edge locations menyajikan konten sedekat mungkin dengan pelanggan, salah satu bagiannya adalah content delivery network (CDN) atau jaringan pengiriman konten. Sebagai pengingat, CDN adalah jaringan yang membantu Anda untuk memberikan konten kepada pelanggan berdasarkan lokasi geografis mereka.

CloudFront sangat terintegrasi dengan layanan lainnya seperti AWS Web Application Firewall (WAF), AWS Certificate Manager, Amazon Route 53, Amazon S3, dan lainnya.
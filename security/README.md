# Intro to CLoud Securiity

Pembagian kontrol terhadap lingkungan AWS platform mengenal konsep shared responsibility model alias model tanggung jawab bersama.

![](https://d17ivq9b7rppb3.cloudfront.net/original/academy/202102231425447e744dc8556f8d1f81ce86009a055bcb.jpeg)

Ada dua hal utama yang harus Anda perhatikan di shared responsibility model ini, yaitu:

* AWS mengontrol security of the cloud (keamanan dari cloud).
* Pelanggan mengontrol security in the cloud (keamanan di cloud).

AWS bertanggung jawab untuk mengontrol data center, keamanan setiap layanan, dan lain sebagainya.

Lalu, bagian pelanggan adalah mengamankan beban kerja yang mereka jalankan di cloud. Ini merupakan bagian tanggung jawab yang AWS bagikan dengan pelanggan guna memastikan keamanan di cloud. 

## Shared Responsibility Model

![](https://d17ivq9b7rppb3.cloudfront.net/original/academy/20210310170138f31fac18d7a3f5d310aa97bf55a9bfba.png)

Bagian yang menjadi tanggung jawab AWS:

* Physical
  Bagian ini terdiri dari berbagai komponen keamanan fisik, seperti gedung, sumber daya listrik, instalasi jaringan, sistem pendingin, penjagaan keamanan, dan lain sebagainya. Ini semua adalah tanggung jawab AWS.

* Network & Hypervisor
  Pada dasarnya, AWS telah mempersiapkan teknologi tersebut dan membuatnya menjadi lebih cepat, lebih baik, lebih kuat, dan tahan kerusakan.
  AWS memiliki banyak auditor pihak ketiga yang memperhatikan dan mengawasi bagaimana infrastruktur AWS dibangun. Dan sehubungan dengan aspek tersebut, AWS dapat memberi Anda dokumentasi sesuai kebutuhan untuk struktur security compliance (kepatuhan keamanan). Ini juga adalah tanggung jawab AWS.

Bagian yang menjadi tanggung jawab pelanggan:

* Operating System
  Dengan Amazon EC2, Anda bisa memilih sistem operasi yang ingin dijalankan. AWS tidak memiliki akses sama sekali ke sistem Anda. Hanya Anda yang memiliki akses untuk masuk ke sistem operasi yang Anda jalankan.
  Lebih lanjut, Anda juga bertanggung jawab untuk melakukan patching (memperbaiki masalah dengan memperbarui program) terhadap sistem operasi tersebut. Jika ditemukan beberapa kerentanan baru di versi Windows, Anda yang perlu mencari solusinya dengan menerapkan patch terbaru.
  Ini adalah hal yang sangat bagus untuk keamanan. Tak akan ada yang dapat men-deploy (menerapkan) sesuatu sehingga mengganggu atau merusak sistem Anda.

* Application
  Di atas sistem operasi, Anda dapat menjalankan aplikasi apa pun yang diinginkan. Anda bertanggung jawab 100% untuk mengelolanya.

* Data
  Data adalah bagian terpenting dan sepenuhnya menjadi ranah Anda untuk mengontrolnya. Anda bisa membuat data dapat diakses oleh semua orang, beberapa orang, satu orang dengan kondisi tertentu, atau bahkan benar-benar menguncinya sehingga tidak ada yang dapat mengakses data tersebut. Plus, Anda juga dapat melakukan enkripsi pada data tersebut.

## Perizinan dan Hak Akses Pengguna

Saat pertama kali membuat akun, Anda memulai dengan identitas sebagai AWS account root user atau bisa disederhanakan menjadi root user.

Root user adalah pemilik akun AWS. Ia memiliki permission untuk mengakses dan mengontrol seluruh sumber daya apa pun dalam akun tersebut, seperti menjalankan database, membuat EC2 instance, layanan blockchain, dan lain-lain.

AWS menyarankan Anda untuk mengaktifkan multi-factor authentication (MFA) guna memastikan agar akun tersebut aman.

### AWS Identity and Access Management (AWS IAM)

AWS Identity and Access Management (AWS IAM) dapat membantu Anda untuk mengelola akses ke layanan dan sumber daya AWS dengan aman.

IAM memberi Anda fleksibilitas untuk mengonfigurasi akses berdasarkan kebutuhan operasional dan keamanan yang spesifik.

* IAM Users
  Di AWS Identity and Access Management (AWS IAM) Anda dapat membuat IAM users. Ia mewakili orang (personal) yang berinteraksi dengan layanan dan sumber daya AWS.

  IAM users secara default belum memiliki permission sama sekali. Ia tidak bisa masuk ke akun AWS, meluncurkan EC2 instance, atau bahkan membuat S3 bucket. Intinya, secara default semua tindakan yang dilakukan oleh IAM users akan ditolak.

  Jika ingin membuat IAM users bisa melakukan sesuatu, maka Anda harus memberikan permission secara eksplisit.

* IAM Policies
  IAM policies adalah dokumen JSON yang mengizinkan atau menolak aktivitas tertentu terhadap layanan dan sumber daya AWS.

  JSON (JavaScript Object Notation) adalah format dokumen pertukaran data yang mudah dimengerti, baik oleh manusia maupun mesin.

  Anda dapat menggunakan IAM policies untuk mengatur akses user ke sumber daya AWS. Misalnya, untuk mengizinkan user untuk mengakses beberapa atau spesifik salah satu Amazon S3 bucket dalam akun AWS Anda.

  ![](https://d17ivq9b7rppb3.cloudfront.net/original/academy/20210310170500aedeeea78d832946a6c2cdbb4ee2b131.png)

* IAM Groups
  Salah satu cara yang dapat mempermudah pengelolaan user dan permission adalah dengan mengelompokkannya ke dalam IAM groups.

  IAM groups adalah grup/kelompok yang berisi kumpulan dari user. Menariknya, Anda bisa melampirkan policy ke group sehingga semua user yang berada di group tersebut akan memiliki permission yang sama.

* IAM Roles
  IAM roles memiliki permission yang dapat mengizinkan tindakan tertentu yang dibutuhkan secara temporer atau sementara. Role ini juga sebenarnya mirip dengan user, bedanya, ia tak memiliki credential (username dan password).

  IAM roles dapat Anda gunakan untuk memberikan akses sementara ke beberapa hal, seperti sumber daya AWS, user, eksternal user, aplikasi, bahkan layanan AWS lainnya.

  Ketika sebuah identitas menggunakan IAM roles, identitas tersebut menanggalkan semua permission sebelumnya yang dimiliki dan mengambil permission dari role tersebut.

  Tak hanya itu, Anda dapat memfederasikan/menggabungkan eksternal user ke akun Anda. Maksudnya, daripada terus membuat IAM users untuk setiap orang di organisasi, Anda dapat menggunakan regular corporate credential (kredensial perusahaan reguler) untuk login ke AWS dengan memetakan identitas perusahaan ke IAM roles.

## Serangan Denial-of-Service

Serangan denial-of-service (DoS) adalah upaya yang dilakukan secara sengaja untuk membuat website atau aplikasi menjadi tidak bekerja dengan optimal bagi pengguna.

Salah satu contohnya adalah ketika penyerang membanjiri aplikasi Anda dengan traffic jaringan yang masif sehingga membuatnya kewalahan dan tak lagi dapat merespons permintaan pengguna.

## Serangan Distributed Denial-of-Service

Distributed denial-of-service alias DDoS adalah salah satu serangan yang dapat menimpa infrastruktur atau aplikasi Anda.

Berbeda dengan DoS yang hanya berasal dari satu  sumber, serangan DDoS ini menggunakan beberapa sumber untuk melakukan serangan.

Serangan ini bisa bisa berasal dari sekelompok orang atau bahkan individu. Cara kerjanya, penyerang menggunakan beberapa komputer yang terinfeksi (juga dikenal sebagai "bot") untuk mengirimkan traffic yang masif ke situs aplikasi Anda.

Untuk serangan UDP flood, solusi untuk mencegah serangan ini adalah dengan menggunakan security group. Ia hanya dapat mengizinkan traffic permintaan yang tepat.

Untuk serangan Slowloris, solusinya sederhana, yakni menggunakan Elastic Load Balancer (ELB) yang dapat mengarahkan traffic lalu lintas untuk Amazon EC2 instance.

Jadi, walaupun penyerang memiliki koneksi yang sangat lambat, pelanggan Anda yang sah tak perlu menunggunya hingga selesai, mereka tetap bisa mengakses server.

Serangan ini juga tak akan mengenai instance Anda karena sebelum diteruskan ke server, ELB akan menangani setiap permintaan hingga selesai terlebih dahulu, tak peduli ia memiliki koneksi yang cepat atau bahkan lambat sekali pun.

ELB itu sangat kuat dan kapasitasnya dapat diskalakan. Ia juga berjalan di tingkat Region. Artinya, untuk bisa membanjiri ELB, Anda harus membanjiri keseluruhan AWS Regions. Bukannya mustahil, tetapi secara teoritis akan terlalu mahal bagi siapa pun yang melakukannya.

## AWS Shield

* AWS Shield Standard
  AWS Shield Standard secara otomatis melindungi sumber daya AWS Anda dari jenis serangan DDoS yang paling umum tanpa biaya.

  Dengan menggunakan berbagai teknik analisis, AWS Shield Standard dapat mendeteksi dan memitigasi traffic berbahaya secara real time saat memasuki aplikasi Anda.

* AWS Shield Advanced
  AWS Shield Advanced adalah layanan berbayar yang menyediakan kemampuan untuk mendiagnostik, mendeteksi, dan memitigasi serangan DDoS yang canggih.

  AWS Shield Advanced terintegrasi dengan layanan lain seperti Amazon CloudFront, Amazon Route 53, dan Elastic Load Balancing.

  Selain itu, Anda juga dapat mengintegrasikan AWS Shield dengan AWS WAF. AWS WAF merupakan web application firewall untuk melindungi aplikasi web atau API Anda dari eksploitasi web umum yang dapat memengaruhi ketersediaan, mengganggu keamanan, atau memakai sumber daya secara berlebihan.
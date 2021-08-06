# Introduction to Amazon Web Services

Hampir semua model komputasi modern adalah berbentuk client-server.

Dalam dunia komputasi, client dapat berupa web browser atau aplikasi yang dapat membuat permintaan ke server. Sebuah server dapat berupa layanan seperti Amazon Elastic Compute Cloud (Amazon EC2).

Contoh interaksinya adalah client membuat permintaan untuk mengakses sebuah artikel berita, skor dalam game online, atau video lucu lalu server mengevaluasi detail permintaan tersebut dan memenuhinya dengan mengembalikan informasi ke client.

Pada dasarnya client membuat suatu permintaan--tentu dengan telah memiliki izin akses--kemudian server menanggapi permintaan tersebut.

Server virtual di AWS diberi nama Amazon Elastic Compute Cloud (EC2) atau dapat kita sebut sebagai instance.

Mari kita lihat proses transaksi yang terjadi antara server dan client ini dari sudut pandang arsitektural:

1. Client membuat permintaan ke server.
2. Server memvalidasi bahwa permintaan tersebut sah.
3. Jika ya, maka server akan memproses permintaan.
4. Setelah selesai, server tersebut akan kembali kepada client dengan membawa hasil dari permintaan client.

Di dunia nyata, aplikasi bisa lebih rumit dari sekadar satu transaksi dengan satu server, bahkan bisa menjadi sangat kompleks ketika diterapkan ke dalam solusi bisnis yang mapan.

AWS memiliki prinsip pay for what you use, prinsip ini bertujuan untuk mengurangi kompleksitas penggunaan server. Ketika kita membutuhkan banyak server kita bisa menambah sesuai kebutuhan dan mengurangi kapasitas server ketika tidak lagi dibutuhkan.

Hal ini berbeda dengan penggunaan data center on-premise (lokal). Anda tidak bisa hanya sekadar menjentikkan jari lalu voila! Kapasitas Anda berlipat ganda dengan sendirinya. Nope. Banyak proses administratif yang perlu Anda lakukan dan berujung pada mahalnya biaya yang perlu Anda keluarkan.

Dengan Amazon Web Service (AWS), Anda tidak perlu membayar uang muka untuk apa pun dan tidak perlu khawatir tentang kendala kapasitas.

>NOTE: Berdasarkan website Cisco--salah satu perusahaan telekomunikasi global--data center adalah fasilitas yang digunakan perusahaan untuk menempatkan aplikasi dan data penting mereka. Komponen utama dari data center adalah router, switch, firewall, sistem penyimpanan, dan juga server.

## Komputasi Cloud

Menurut [newyorker.com](https://www.newyorker.com/books/page-turner/how-the-metaphor-of-the-cloud-changed-our-attitude-toward-the-internet), simbol awan dipakai karena merepresentasikan keberadaan data kita ada di suatu tempat di luar sana, mengambang, melayang, nirkabel, tersedia di mana saja dan kapan saja ketika kita membutuhkannya. Istilah awan juga menarik karena merupakan kebalikan dari dunia material yang riil seperti colokan, kabel, hard disk, dsb.

Cloud computing (komputasi cloud) adalah penggunaan sesuai kebutuhan (on-demand) sumber daya IT melalui internet dengan harga sesuai pemakaian (pay-as-you-go).

## Model Penerapan untuk Komputasi Cloud

Saat memilih strategi untuk menerapkan cloud, Anda harus mempertimbangkan beberapa faktor, seperti komponen aplikasi cloud yang diperlukan, layanan manajemen sumber daya yang dibutuhkan, dan setiap persyaratan infrastruktur IT.

Tiga model penerapan komputasi cloud adalah cloud-based, on-premises (lokal), dan hybrid.

### Cloud-based Deployment

Dalam model penerapan cloud-based, Anda dapat merancang, membangun, dan menjalankan aplikasi baru di cloud. Anda pun dapat memigrasikan aplikasi yang telah ada ke cloud.

Anda dapat membangun aplikasi tersebut pada low-level infrastructure (infrastruktur tingkat rendah) yang mana memerlukan staf IT Anda untuk mengelolanya. Atau dengan alternatif lain, yaitu menggunakan higher-level services (layanan dengan tingkat lebih tinggi) sehingga mengurangi kebutuhan pengelolaan, arsitektur, dan scaling (penyesuaian kapasitas) pada infrastruktur Anda.

Misalnya, Anda dapat membuat aplikasi yang terdiri dari server virtual, database, dan komponen jaringan yang sepenuhnya berbasis di cloud.

### On-premises Deployment

On-premises juga dikenal sebagai private cloud (cloud privat). Dalam model ini, sumber daya di-deploy (diterapkan) menggunakan layanan manajemen aplikasi dan teknologi virtualisasi pada data center pribadi sehingga penggunaan dan pemanfaatannya dapat meningkat.

### Hybrid Deployment

Dalam penerapan hybrid, sumber daya berbasis cloud terhubung ke data center on-premises (lokal). Anda bisa gunakan pendekatan ini untuk beberapa situasi, seperti aplikasi lama yang memang lebih baik dikelola di on-premises atau mungkin karena peraturan pemerintah yang mengharuskan Anda menyimpan data tertentu di data center lokal.

## Manfaat dari Komputasi Cloud

### Ubah pengeluaran di muka menjadi pengeluaran variabel

Pengeluaran di muka (upfront expense) mengacu pada data center, server fisik, dan sumber daya lain yang perlu Anda investasikan sebelum Anda menggunakannya. Sedangkan pengeluaran variabel (variable expense) berarti Anda hanya membayar untuk sumber daya komputasi yang Anda konsumsi.

Dengan mengambil pendekatan komputasi cloud yang menawarkan keuntungan biaya variabel, perusahaan dapat mengimplementasikan solusi inovatif sekaligus menghemat biaya.

### Hentikan biaya pengelolaan dan pemeliharaan data center

Komputasi di data center sering kali mengharuskan Anda untuk mengeluarkan lebih banyak biaya dan waktu untuk mengelola infrastruktur dan server.

Nah, dengan komputasi cloud, Anda tak perlu lagi khawatir akan tugas-tugas ini. Dengan begitu, Anda dapat lebih fokus pada aplikasi dan pelanggan Anda.

### Berhenti menebak kapasitas

Dengan komputasi cloud, Anda tak perlu memprediksi berapa banyak kapasitas infrastruktur yang Anda perlukan sebelum men-deploy aplikasi.

Misalnya, Anda dapat meluncurkan Amazon EC2 instance dan cukup membayar untuk waktu komputasi yang digunakan. Daripada harus membayar sumber daya yang tak terpakai atau berurusan dengan kapasitas yang terbatas, dengan komputasi cloud, Anda dapat menggunakan kapasitas sesuai keinginan.

Bahkan Anda juga dapat melakukan proses scale in (mengurangi) atau scale out (memperbanyak) kapasitas sesuai permintaan.

### Manfaatkan skala ekonomi yang masif

Dengan menggunakan komputasi cloud, Anda dapat mewujudkan biaya variabel yang lebih rendah daripada yang dapat Anda peroleh dari data center on-premise.

Penggunaan dari ratusan ribu pelangganlah yang memungkinkan AWS dapat mencapai skala ekonomi (economies of scale) yang lebih tinggi. Kemudian skala ekonomi ini diterjemahkan ke dalam harga pay-as-you-go yang lebih murah.

### Tingkatkan kecepatan dan ketangkasan

Fleksibilitas dari penggunaan komputasi cloud memudahkan Anda untuk mengembangkan dan men-deploy aplikasi.

Dengan komputasi cloud, Anda memiliki lebih banyak waktu untuk bereksperimen dan berinovasi. Tentu ini tak bisa Anda lakukan jika menggunakan data center on-premise. Misal untuk mendapatkan sumber daya baru, mungkin Anda memerlukan waktu berminggu-minggu. Sedangkan dengan AWS, sumber daya baru akan langsung siap diakses dalam hitungan menit.

### Mendunia dalam hitungan menit

AWS Cloud memungkinkan Anda dapat meluncurkan aplikasi ke pelanggan di seluruh dunia dengan cepat sekaligus memberikan latensi yang rendah. Ini berarti meskipun Anda berada di belahan dunia yang berbeda dengan pelanggan, mereka tetap dapat mengakses aplikasi dengan waktu tunda (delay) yang minimal.

## Pengenalan ke Amazon Elastic Compute Cloud (Amazon EC2)

Di AWS server berbentuk virtual. Dan layanan yang dapat Anda gunakan untuk mendapatkan akses ke server virtual tersebut disebut dengan Amazon EC2.

Amazon EC2 memberikan kapasitas komputasi yang aman dan dapat Anda ubah-ubah ukurannya di cloud.

AWS terus mengoperasikan kapasitas komputasi dalam jumlah besar sehingga Anda dapat menggunakannya kapan pun dan berapa pun sesuai dengan porsi kapasitas yang Anda butuhkan. Anda hanya perlu membuat permintaan untuk EC2 instance sesuai keinginan dan saat itu juga mereka pun siap dalam hitungan menit. Di AWS, server virtual disebut sebagai instance.

Amazon EC2 berjalan di atas host (mesin fisik) yang dikelola oleh AWS menggunakan teknologi virtualisasi. Saat menjalankan instance, Anda tidak menggunakan keseluruhan mesin host untuk sendiri melainkan Anda akan berbagi mesin host dengan beberapa instance lainnya. Ini dikenal dengan nama virtual machines alias mesin virtual.

Hypervisor-lah yang bertanggung jawab untuk membagi sumber daya fisik yang mendasarinya di antara mesin virtual tersebut. Ini sepenuhnya dikelola oleh AWS. Ide berbagi perangkat keras yang mendasarinya ini disebut multitenancy.

Hypervisor juga bertanggung jawab untuk mengisolasi mesin virtual satu sama lain saat mereka berbagi sumber daya dari host. Ini berarti EC2 instance tetap aman meskipun mereka berbagi sumber daya. Satu instance tidak akan mengetahui keberadaan instance lainnya walau mereka ada di host yang sama. Mereka tetap aman dan terpisah satu sama lain.

Amazon EC2 memberikan Anda banyak fleksibilitas dan kontrol. Tak hanya dapat menjalankan server baru atau menghentikannya sesuka hati, Anda juga memiliki kuasa atas konfigurasinya.

Misal pada saat Anda membuat EC2 instance. Anda dapat memilih OS (operating system/sistem operasi) yang Anda inginkan, baik itu Windows atau Linux. Anda juga dapat membuat ribuan instance EC2 sekaligus dengan perpaduan sistem operasi dan konfigurasi sehingga dapat mendukung berbagai aplikasi bisnis Anda.

Ketika aplikasi yang Anda jalankan mulai membutuhkan kapasitas yang lebih besar, Anda dapat menambahkan lebih banyak memori dan CPU. Itulah yang dinamakan vertical scaling atau mengatur skala instance secara vertikal.

## Tipe Instance Amazon EC2

### General purpose instances (Instance tujuan umum)

Tipe ini memberikan keseimbangan yang baik dari segi sumber daya komputasi, memori, dan jaringan. Selain itu, opsi ini juga dapat digunakan untuk berbagai beban kerja yang beragam seperti server aplikasi web atau repositori kode.

### Compute optimized instances (Instance teroptimasi untuk komputasi)

Tipe yang satu ini ideal untuk tugas komputasi yang intensif dan berpusat pada prosesor dengan performa tinggi, seperti server game, HPC (high-performance computing/komputasi dengan performa tinggi), atau bahkan pemodelan ilmiah.

Anda juga bisa menggunakan tipe compute optimized instances untuk beban kerja batch processing yang membutuhkan banyak proses transaksi di satu grup.

### Memory optimized instances (Instance teroptimasi untuk memori)

Opsi ini didesain untuk memberikan performa tinggi untuk beban kerja yang memproses kumpulan data besar di dalam memori, seperti relasional dan nonrelasional database atau HPC (high-performance computing).

### Accelerated computing instances (Instance terakselerasi untuk komputasi)

Tipe ini menggunakan perangkat keras akselerator untuk menjalankan beberapa fungsi secara lebih efisien dibandingkan dengan perangkat lunak yang berjalan pada CPU. Contohnya adalah penghitungan bilangan floating-point, pemrosesan grafik, dan data pattern matching (pencocokan pola data).

### Storage optimized instance (Instance teroptimasi untuk penyimpanan)

Opsi ini didesain untuk beban kerja yang membutuhkan akses read (baca) dan write (tulis) yang tinggi dan berurutan untuk kumpulan data yang besar di penyimpanan lokal.

## Mengarahkan Traffic dengan Elastic Load Balancing

Katakanlah Anda memiliki beberapa EC2 instance yang menjalankan program serupa. Anda perlu mengarahkan setiap permintaan yang masuk untuk menuju ke EC2 instance tertentu. Anda juga harus memastikan bahwa distribusi beban kerja merata di seluruh EC2 instance sehingga tak ada satu instance pun yang menganggur.

Proses ini disebut dengan load balancing (menyeimbangkan beban).

Sedangkan aplikasi yang dapat menerima permintaan lalu mengarahkannya ke instance untuk diproses disebut dengan load balancer (penyeimbang beban).

Load balancer bertindak sebagai satu titik kontak untuk semua traffic web yang masuk ke Auto Scaling group Anda. Ini berarti saat Anda menambah atau menghapus Amazon EC2 instance sebagai respons terhadap jumlah traffic yang masuk, permintaan ini diarahkan ke load balancer terlebih dahulu. Barulah kemudian permintaan tersebut disebar ke berbagai sumber daya yang akan menanganinya.

### Elastic Load Balancing

AWS memiliki layanan load balancer yang berkinerja tinggi, hemat biaya, highly available (sangat tersedia), dan dapat diskalakan secara otomatis.

Elastic Load Balancing (ELB), yaitu layanan AWS yang secara otomatis mendistribusikan traffic aplikasi yang masuk ke berbagai sumber daya, seperti Amazon EC2 instance.

Elastic Load Balancing dirancang untuk mengatasi undifferentiated heavy lifting dari load balancing.

Elastic Load Balancing adalah regional construct (konstruksi regional). Ini berarti ELB berjalan di tingkat Region, bukan pada individu EC2 instance sehingga membuatnya highly available secara otomatis.

ELB dapat diskalakan secara otomatis sehingga mampu menangani kepadatan traffic tanpa berdampak pada biaya per jamnya. Elastic Load Balancing dapat bekerja sama dengan Amazon EC2 Auto Scaling untuk membantu memastikan aplikasi yang berjalan di Amazon EC2 dapat memberikan kinerja dan ketersediaan tinggi.

## Messaging dan Queueing

Aplikasi saling mengirim pesan untuk berkomunikasi. Ketika aplikasi berkomunikasi secara langsung maka itu disebut dengan tightly coupled architecture.

Ciri khas dari arsitektur yang tightly coupled adalah jika ada satu komponen yang gagal atau berubah, maka kegagalan ini memicu masalah untuk komponen lain atau bahkan keseluruhan sistem.

Misalnya kita punya aplikasi A yang mengirimkan pesan langsung ke aplikasi B. Jika aplikasi B mengalami kegagalan dan tak dapat menerima pesan tersebut, maka aplikasi A pun akan terkena eror juga.

Desain aplikasi seperti ini dapat dianggap sebagai pendekatan monolithic application alias aplikasi monolitik, yaitu saat berbagai komponen digabungkan menjadi satu kesatuan.

Nah, untuk mengatasi masalah ini kita harus membuat arsitektur yang lebih andal dengan loosely coupled architecture. Karakter dari arsitektur ini adalah jika satu komponen gagal, maka komponen tersebut akan diisolasi sehingga tak akan menyebabkan kegagalan beruntun ke seluruh sistem.

Pesan dikirim ke antrean oleh aplikasi A dan diproses oleh aplikasi B. Jika aplikasi B gagal, aplikasi A tidak mengalami gangguan apa pun. Pesan yang dikirim masih dapat dikirim ke antrean (message queue) dan akan tetap berada di sana sampai akhirnya diproses.

Desain aplikasi semacam ini merupakan pendekatan dari microservice (layanan mikro), yaitu saat komponen dibuat menjadi loosely coupled sehingga dapat dikembangkan, di-deploy (diterapkan), dan dikelola secara independen. Setiap komponen mempunyai tugasnya masing-masing dan juga dapat berkomunikasi satu sama lain.

### Amazon Simple Queue Service (Amazon SQS)

Amazon Simple Queue Service (Amazon SQS) memungkinkan Anda untuk mengirim, menyimpan, dan menerima pesan antar komponen perangkat lunak dengan volume berapa pun tanpa perlu khawatir akan kehilangan pesan tersebut atau membutuhkan layanan lain untuk menyediakan pesan. Data yang terkandung di dalam pesan disebut payload dan itu dilindungi hingga terkirim.

Amazon SQS queue adalah tempat di mana pesan ditaruh sampai diproses. Cara kerjanya adalah aplikasi A akan mengirim sebuah pesan ke dalam queue lalu aplikasi B akan mengambilnya, memprosesnya, dan kemudian menghapusnya dari antrean.

AWS mengelola infrastruktur yang mendasarinya sehingga layanan ini dapat otomatis diskalakan, andal, serta mudah dikonfigurasi dan digunakan.

Jika Anda sulit memahaminya, bayangkan saja sebuah pesan sebagai sebuah pesanan kopi dan SQS queue adalah buffer, sebagaimana yang terdapat di skenario kedai kopi kita.

### Amazon Simple Notification Service (Amazon SNS)

Amazon Simple Notification Service (Amazon SNS) juga digunakan untuk mengirimkan pesan ke layanan. Bedanya, ia juga dapat mengirimkan pemberitahuan ke pelanggan.

Proses tersebut dilakukan dengan cara yang berbeda, yaitu menggunakan model publish/subscribe alias pub/sub. Itu artinya Anda dapat membuat suatu saluran untuk menyampaikan pesan yang disebut dengan SNS topic. Jika ingin mempublikasikan pesan (publish), Anda bisa mengatur pelanggan (subscribers) yang akan menerima topik tersebut.

Dalam praktiknya, Anda dapat mengirim satu pesan ke SNS topic yang kemudian akan menyebar ke semua subscribers dalam sekali jalan. Subscribers dapat berupa endpoint (titik akhir) layanan lain, seperti SQS queue, fungsi AWS Lambda--akan kita bahas nanti, dan juga server web.

Selain itu, Amazon SNS dapat digunakan untuk menyebarkan notifikasi kepada pelanggan menggunakan push notification (pesan yang muncul di perangkat seluler), SMS, dan email.

Nah, begitu juga dengan skenario kedai kopi. Kita dapat mengirimkan pemberitahuan kepada pelanggan ketika pesanan mereka sudah siap untuk diambil, bisa berupa SMS atau push notification.
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


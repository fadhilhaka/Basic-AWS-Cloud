# Storage and Database

## Instance Store dan Amazon Elastic Block Store (Amazon EBS)

Ketika aplikasi berjalan di EC2 instance, mereka kerap kali membutuhkan akses ke block-level storage (penyimpanan tingkat blok).

Jika Anda kurang kenal dengan istilah block-level storage, maka anggaplah ia sebagai tempat menyimpan file. File adalah serangkaian byte (bita) yang disimpan di dalam blok pada disk.

Pada saat file pada disk tersebut diperbarui, ia tak akan menimpa seluruh rangkaian blok, melainkan memperbarui bagian yang berubah saja. Dengan sistem seperti ini, penyimpanan untuk aplikasi (database, perangkat lunak perusahaan, atau sistem file) jadi lebih efisien.

### Instance Store

Instance store (tempat penyimpanan instance) adalah penyimpanan block-level storage sementara untuk Amazon EC2 instance. Saat Anda meluncurkan EC2 instance--tergantung tipe EC2 instance yang Anda pilih--biasanya sudah tersedia penyimpanan lokal alias instance store volume di dalamnya.

Volume ini secara fisik terpasang ke host (mesin fisik), yaitu tempat di mana EC2 instance Anda berjalan. Anda dapat melakukan proses write (menulis) data padanya seperti hard drive pada umumnya.

Namun, jika Anda menghentikan atau mengakhiri EC2 instance tersebut, maka semua data di sana akan terhapus.

EC2 instance adalah mesin virtual. Oleh karena itu, host yang mendasarinya dapat berubah pada saat instance berhenti dan memulai.

### Amazon Elastic Block Store (Amazon EBS)

Amazon Elastic Block Store (Amazon EBS) adalah layanan yang menyediakan block-level storage (penyimpanan tingkat blok) yang dapat Anda gunakan bersama dengan Amazon EC2 instance.

Amazon EBS memungkinkan Anda untuk membuat hard drive virtual (EBS volume) yang kemudian bisa di-attach (dipasang) ke EC2 instance. EBS volume ini merupakan penyimpanan yang terpisah dari instance store volume. Ia pun tak terikat langsung ke host yang menjalankan EC2 instance Anda.

Karena EBS volume digunakan untuk kebutuhan data yang persisten, maka penting untuk Anda melakukan backup (pencadangan) data. Anda dapat menjalankan incremental backup (pencadangan secara inkremental) dari EBS volume dengan membuat Amazon EBS snapshot.

Amazon EBS snapshot disimpan secara bertahap/inkremental. Itu berarti pada saat pertama kali proses pencadangan dilakukan, ia akan menyalin semua data yang ada di EBS volume. Namun, untuk pencadangan berikutnya, ia hanya menyimpan blok data yang berubah dari snapshot terakhir.

## Amazon Simple Storage Service (Amazon S3)

Dengan Amazon S3, data disimpan sebagai objek. Objek tersebut akan disimpan di dalam bucket. Sederhananya, anggaplah file yang ada di hard drive Anda sebagai objek dan direktori file adalah bucket.

Amazon S3 juga merupakan object-level storage (penyimpanan tingkat objek). Setiap objek terdiri dari data, metadata, dan kunci.

Data yang dimaksud itu bisa bermacam-macam, seperti gambar, video, dokumen teks, atau jenis file lainnya. Lalu, metadata adalah informasi yang berisi tentang apa itu data, cara penggunaannya, ukuran objeknya, dan sebagainya. Nah, key (kunci) pada suatu objek adalah identifier/pengenal yang unik.

Ukuran maksimum dari setiap objek yang dapat Anda unggah adalah 5 terabyte. S3 juga memiliki fitur versioning dengan membuat object version (versi objek).

## Amazon Elastic File System (Amazon EFS)

Amazon EFS adalah sistem file terkelola yang bisa diskalakan dan dapat digunakan oleh layanan AWS Cloud dan sumber daya di data center on-premise.

Dengan EFS, Anda dapat memiliki beberapa instance yang mengakses data secara bersamaan. Ia akan melakukan scaling up dan scaling down sesuai kebutuhan secara otomatis.

Amazon EBS volume dilampirkan ke EC2 instance dan merupakan Availability Zone-level resource atau sumber daya tingkat Availability Zone. Itu artinya, EBS akan menyimpan data hanya di satu Availability Zone (AZ).

Dengan Amazon EBS, Anda dapat menyimpan file, menjalankan database, atau menyimpan aplikasi di dalamnya. Ia adalah hard drive (cakram keras). Namun, jika Anda membuat EBS volume sebesar 2 terabyte lalu mengisinya hingga penuh, ia tidak akan serta-merta melakukan proses scaling dengan sendirinya.

Amazon EFS memungkinkan beberapa instance untuk melakukan proses read (membaca) dan write (menulis) data darinya pada saat bersamaan.

Amazon EFS memakai sistem file untuk Linux dan merupakan Regional resource (sumber daya regional). Itu berarti data akan disimpan di beberapa AZ. Dengan demikian, setiap EC2 instance yang berada di Region yang sama dapat menyimpan data ke sistem file Amazon EFS.

## Amazon Relational Database Service (Amazon RDS)

Relational database management system (RDBMS) artinya, data yang kita simpan dapat memiliki relasi dengan bagian data lainnya.

Dalam dunia database, Anda akan sering mendengar kata query atau kueri. Itu adalah sekumpulan instruksi khusus untuk mengekstraksi data.

Database relasional menggunakan structured query language (SQL) alias bahasa kueri terstruktur untuk menyimpan dan membuat kueri data. Pendekatan semacam ini memungkinkan data disimpan dengan cara yang mudah dimengerti, konsisten, dan dapat diskalakan.

AWS memungkinkan Anda untuk melakukan Lift-and-Shift, yaitu proses memigrasikan beban kerja dari on-premise ke AWS dengan sedikit atau bahkan tanpa modifikasi.

Contohnya, Anda bisa memindahkan database on-premise lalu menjalankannya di Amazon EC2. Dengan begitu, Anda mempunyai kendali atas variabel yang sama dengan keadaan di on-premise, seperti OS, memori, CPU, kapasitas penyimpanan, dsb.

Salah satu cara yang dapat Anda lakukan untuk mewujudkan proses migrasi ini adalah dengan menggunakan layanan Database Migration Service.

## Amazon DynamoDB

Amazon DynamoDB merupakan database nonrelasional (NoSQL) dan menggunakan jenis pendekatan pasangan key-value (kunci-nilai).

Dengan Amazon DynamoDB, Anda dapat membuat tabel, yakni tempat menyimpan dan membuat kueri data. Data diatur menjadi item/key dan item memiliki atribut/value.

Anda dapat menambah dan menghapus atribut dari item di dalam tabel kapan pun. Setiap item tidak harus memiliki atribut yang sama. Sehingga, ini akan sangat baik untuk kumpulan data yang memiliki beberapa variasi antara satu item dengan item lainnya.

Karena kueri pada database nonrelasional itu cenderung lebih sederhana, ini membuat Anda bisa fokus pada kumpulan item dari satu tabel, bukan kueri dari rentang beberapa tabel.

Amazon DynamoDB ini adalah layanan yang terkelola sepenuhnya dan merupakan database serverless (tanpa server). Itu artinya Anda tak perlu mengelola instance atau infrastruktur dasarnya. Bahkan, Anda tidak perlu khawatir akan proses scaling (penyesuaian kapasitas) yang terjadi pada sistem.

Selain itu, Amazon DynamoDB juga menyimpan data di beberapa perangkat di seluruh availability zone. Sehingga, ini menjadikannya database yang highly available (sangat tersedia). Layanan ini memiliki kinerja yang sangat tinggi. Ia punya response time (waktu respons) kilat, yakni milidetik, yang akan sangat bermanfaat untuk aplikasi dengan potensi jutaan pengguna.

## Amazon Redshift

Ketika data menjadi semakin kompleks untuk ditangani oleh database relasional tradisional, maka data warehouse (gudang data) adalah solusinya. Data warehouse dirancang secara spesifik untuk jenis big data seperti analitik historis, bukan analisis operasional.

Analitik historis itu seperti pertanyaan, “Tunjukkan angka penjualan satu jam terakhir di semua toko.” Intinya, data sudah siap pada saat diproses. Data tidak akan berubah lagi karena data ini adalah data historis yang sudah terjadi sebelumnya.

Bandingkan pertanyaan itu dengan, "Berapa kantong kopi yang masih ada di inventaris kita sekarang?" Yang mana data tersebut bisa berubah bahkan pada saat kita bertanya. Selama pertanyaan Anda melihat ke belakang alias lampau, maka data warehouse adalah solusi yang tepat untuk lini business intelligence tersebut.

Amazon Redshift adalah layanan data warehousing yang dapat Anda gunakan untuk analitik big data. Layanan ini menawarkan kemampuan untuk mengumpulkan data dari banyak sumber dan membantu Anda memahami hubungan dan tren di seluruh data. Selain itu, ia juga dapat diskalakan secara masif.

## AWS Database Migration Service

AWS Database Migration Service (AWS DMS) dapat memigrasikan database yang Anda miliki--baik relasional, nonrelasional (NoSQL), atau tipe penyimpanan data lain--ke AWS dengan mudah dan aman.


# Migration

## AWS Cloud Adoption Framework (AWS CAF)

AWS telah menciptakan [AWS Cloud Adoption Framework (AWS CAF)](https://docs.aws.amazon.com/whitepapers/latest/aws-migration-whitepaper/the-aws-cloud-adoption-framework-aws-caf.html), fungsinya untuk memberikan Anda panduan agar proses migrasi ke AWS menjadi lebih cepat dan lancar.

Framework atau kerangka kerja tersebut membagi panduan menjadi 6 area yang disebut dengan perspektif. Masing-masing perspektif meliputi tanggung jawab dari kelompok yang berbeda.

Secara umum, ia mencakup perspektif Business, People, dan Governance berfokus pada kemampuan bisnis. Lalu, perspektif Platform, Security, dan Operations berfokus pada kemampuan teknis.

## Strategi Migrasi

Setiap aplikasi yang berarsitektur tightly coupled akan memiliki 6 kemungkinan opsi terkait strategi migrasi, AWS menyebutnya dengan 6 R.

* Rehosting
  Rehosting juga dikenal sebagai lift and shift (angkat dan pindahkan). Opsi ini mudah dilakukan karena Anda tak perlu membuat perubahan apa pun. Cukup pindahkan aplikasi yang Anda miliki ke AWS.

* Replatforming
  Strategi migrasi yang satu ini disebut juga dengan lift, tinker, and shift (angkat, perbaiki, dan pindahkan). Pada dasarnya, opsi ini masih berupa lift and shift namun Anda dapat melakukan beberapa pengoptimalan cloud. Dalam strategi ini, Anda tak akan mengubah arsitektur inti (core architecture) apa pun pada proses migrasi aplikasi.

* Retiring
  AWS menemukan bahwa sebanyak 10% hingga 20% dari portofolio IT perusahaan menyertakan aplikasi yang tak lagi digunakan dan bisa dimatikan. Penghematan semacam ini dapat memberikan beberapa keuntungan, seperti meningkatkan business case (kasus bisnis), memfokuskan tim terhadap aplikasi yang digunakan, dan mengurangi jumlah aplikasi yang harus dikelola.

* Retaining
  Saat hendak melakukan migrasi ke AWS, mungkin Anda memiliki beberapa aplikasi yang akan segera deprecated (dihentikan). Tetapi, aplikasi tersebut masih perlu digunakan selama beberapa waktu, daripada memindahkan aplikasi tersebut ke AWS, sebaiknya Anda hanya memigrasikan aplikasi yang sekiranya masuk akal dan berguna untuk bisnis.

* Repurchasing
  Strategi migrasi ini umum terjadi pada perusahaan yang ingin meninggalkan vendor perangkat lunak lama dan memulai yang baru.

* Refactoring/re-architecting
  Pada opsi inilah Anda menulis kode yang baru. Hal ini didorong oleh kebutuhan bisnis yang kuat untuk menambahkan fitur, skala, atau kinerja yang mungkin sulit diraih pada data center on-premise.

## AWS Snow Family

Beberapa pelanggan memerlukan suatu cara yang dapat mengirimkan data ke AWS dengan cara yang efisien dan cepat.

Metode yang biasanya dilakukan adalah melakukan transfer data yang diperlukan melalui internet atau AWS Direct Connect. Namun, dengan keterbatasan bandwidth (jumlah maksimum data yang dapat dikirim), secara umum proses tersebut dapat memakan waktu berhari-hari, berminggu-minggu, atau bahkan berbulan-bulan.

Misalnya, untuk memindahkan 1 PB (petabyte) data, koneksi jaringan yang memiliki kecepatan 1 Gbps (gigabit per second) secara teori membutuhkan waktu sekitar 100 hari. Di dunia nyata, itu bisa memakan waktu lebih lama dan bahkan menguras biaya yang besar.

AWS memperkenalkan perangkat AWS Snow Family. Layanan ini adalah kumpulan perangkat fisik yang dapat membantu Anda untuk memindahkan data sampai dengan ukuran exabyte ke dalam dan keluar AWS.

AWS Snow Family terdiri dari AWS Snowcone, AWS Snowball, dan AWS Snowmobile.
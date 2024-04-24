# Tutorial 8 Subscriber
Nama  : Prasetyo Adi Wijonarko
Kelas : A
NPM   : 2206830246

## Refleksi 1
1. what is amqp? <br>
AMQP (Advanced Message Queuing Protocol) adalah sebuah protokol standar dalam lapisan aplikasi untuk middleware berorientasi pesan, digunakan untuk membangun sistem pengiriman pesan yang efisien. Dengan AMQP, berbagai jenis aplikasi dapat saling berkomunikasi dengan melakukan pertukaran pesan antara sistem yang terpisah, seperti subscriber dan publisher, sehingga memungkinkan implementasi sistem antar layanan yang efisien.
2. what it means? `guest:guest@localhost:5672` , what is the first quest, and what is the second guest, and what is `localhost:5672` is for? <br>
`guest:guest@localhost:5672` adalah sebuah string koneksi yang digunakan untuk menghubungkan ke server AMQP, seperti RabbitMQ. Bagian 'guest' pertama adalah username untuk autentikasi ke server AMQP, sementara 'guest' kedua adalah password yang sesuai. `@localhost:5672` menunjukkan alamat host dan port yang digunakan oleh RabbitMQ, dengan 'localhost' mengacu pada komputer lokal di mana RabbitMQ berjalan, dan 5672 sebagai port default untuk komunikasi menggunakan protokol AMQP. Dengan string ini, aplikasi dapat berkomunikasi dan bertukar pesan dengan server AMQP yang terhubung. AMQP (Advanced Message Queuing Protocol) adalah protokol jaringan yang memfasilitasi pengiriman dan penerimaan pesan antara sistem yang terpisah, memungkinkan pertukaran data antar layanan dengan efisien.
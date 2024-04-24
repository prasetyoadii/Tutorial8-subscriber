# Tutorial 8 Subscriber
Nama  : Prasetyo Adi Wijonarko <BR>
Kelas : A <BR>
NPM   : 2206830246 <br>

## Refleksi 1
1. what is amqp? <br>
AMQP (Advanced Message Queuing Protocol) adalah sebuah protokol standar dalam lapisan aplikasi untuk middleware berorientasi pesan, digunakan untuk membangun sistem pengiriman pesan yang efisien. Dengan AMQP, berbagai jenis aplikasi dapat saling berkomunikasi dengan melakukan pertukaran pesan antara sistem yang terpisah, seperti subscriber dan publisher, sehingga memungkinkan implementasi sistem antar layanan yang efisien.
2. what it means? `guest:guest@localhost:5672` , what is the first quest, and what is the second guest, and what is `localhost:5672` is for? <br>
`guest:guest@localhost:5672` adalah sebuah string koneksi yang digunakan untuk menghubungkan ke server AMQP, seperti RabbitMQ. Bagian 'guest' pertama adalah username untuk autentikasi ke server AMQP, sementara 'guest' kedua adalah password yang sesuai. `@localhost:5672` menunjukkan alamat host dan port yang digunakan oleh RabbitMQ, dengan 'localhost' mengacu pada komputer lokal di mana RabbitMQ berjalan, dan 5672 sebagai port default untuk komunikasi menggunakan protokol AMQP. Dengan string ini, aplikasi dapat berkomunikasi dan bertukar pesan dengan server AMQP yang terhubung. AMQP (Advanced Message Queuing Protocol) adalah protokol jaringan yang memfasilitasi pengiriman dan penerimaan pesan antara sistem yang terpisah, memungkinkan pertukaran data antar layanan dengan efisien.
3. Simulation slow subcsriber <br>
![alt text](/image/Simulation%20slow%20subcsriber.jpg) <br>
Berdasarkan screenshot tersebut, terlihat bahwa jumlah queue atau queued message mencapai sekitar 20. Hal ini disebabkan oleh perubahan pada subscriber yang menyebabkan penundaan dalam penerimaan pesan, sehingga subscriber menjadi lebih lambat dalam mengambil pesan daripada kecepatan pengiriman pesan oleh publisher. Ketidakseimbangan ini menyebabkan penumpukan pesan dalam antrian (queue) karena subscriber tidak dapat mengimbangi laju pengiriman pesan oleh publisher. Akibatnya, saat perintah cargo run dijalankan beberapa kali secara cepat pada publisher, subscriber akan mengalami beban yang berlebihan karena harus mengambil dan memproses banyak pesan sekaligus, mengakibatkan peningkatan jumlah queue hingga mencapai 20 pesan dalam antrian.
4. Running at least three subscribers
![alt text](/image/running3subs-1.jpg)
![alt text](/image/running3subs-2.jpg)
Berdasarkan kedua screenshot tersebut, Penambahan subscriber membantu mengurangi beban tiap subscriber, sehingga message queue dapat berkurang dan spikenya lebih cepat menurun. Dengan beberapa subscriber yang berjalan, message dapat diproses secara paralel, di mana 3 subscriber yang aktif bekerja bersama-sama untuk memproses message. Distribusi beban kerja yang merata dan respons yang lebih cepat terhadap message yang masuk terjadi karena tugas dipisahkan di antara beberapa subscriber. Jumlah subscriber yang berjalan membantu menyeimbangkan kecepatan pengiriman dan penerimaan message antara publisher dan subscriber, yang pada akhirnya dapat mengurangi message queue.
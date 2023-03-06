set key value <!-- untuk menambahkan data ke redis -->
get key <!-- untuk mengambil data -->
exists key <!-- untuk mengecek apakah key yang dituliskan ada -->
del key <!-- untuk menghapus data di redis -->
append key value <!-- untuk menambah value kedalam key yang sudah ada -->
keys pattern <!-- untuk mengambil semua key atau beberapa key --> <!-- pattern disini menggunakan regex dari redisnya -->

keys *<nama keys> <!-- maka ini akan mencari keys dengan akhiran nama keys yang di inginkan -->
keys <nama keys>* <!-- kebalikanya dari yang atas -->


getrange <nama keys> <start di karakter keberapa> <berakhir di karakter keberapa> <!-- untuk mengambil data berdasarkan jumlah karakter yang di inginkan dari depan -->

setrange <nama keys> <start dari karakter keberapa> <value yang baru> <!-- untuk mengganti beberapa karakter di value -->

mget <nama keys> <nama keys> <!-- untuk mengambil data dengan cara banyak -->

mset <nama keys> <value> <nama keys> <value> <!-- untuk set data dengan banyak -->

expire <nama keys> <second> <!-- menambahkan waktu menggunakan detik ke keys yang sudah ada di redis -->

setex <nama keys> <second> <value> <!-- set data baru ke redis dengan tambahan expire time -->

ttl <nama keys> <!-- untuk mengetahui berapa lama lagi data itu akan expire -->

incr key <!-- untuk melakukan increment data valuenya berupa string integer naik 1 -->
decr key <!-- kebalikanya dari yang atas -->

incrby key increment  <!-- kenaikan valuenya sesuai yang kita mau -->
decrby key decrement <!-- kebalikanya dari yang atas -->

flushdb <!-- menghapus semua data di dalem redis yang ada di db yang kita select -->
flushall <!-- menghapus semua data yang ada di dalam redis dan tidak peduli db manapun -->

cat <nama file> | redis-cli -h localhost --pipe <!-- untuk migrasi db ke redis -->

<!-- Transaction -->

multi <!-- digunakan untuk memulai transaction -->
exec <!-- untuk mengeksekusi semua perintah yang ada -->
discard <!-- untuk membatalkan semua perintah yang sudah kita lakukan -->

monitor <!-- untuk memonitor semua data yang masuk ke redis -->
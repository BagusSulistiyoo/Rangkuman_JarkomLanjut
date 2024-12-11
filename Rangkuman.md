# Rangkuman_JarkomLanjut
Bagus Sulistiyo
20210801138
Teknik informatika
Rangkuman jarkom lanjut pert awal sampai dengan akhir!

Pengenalan WAN dan router
1.	WAN (Wide Area Network)  jaringan komputer yang mencakup area geografis yang luas, seperti antar kota, negara, atau bahkan benua. 
2.	Router adalah perangkat jaringan yang mengarahkan lalu lintas data antar jaringan yang berbeda, seperti dari LAN ke WAN. Router memastikan data dikirim melalui jalur yang paling efisien.
Menghubungkan jaringan lokal (LAN) ke jaringan luas (WAN).
Menentukan jalur terbaik untuk data menggunakan protokol routing seperti OSPF atau BGP.
Menyediakan fitur keamanan seperti firewall dan VPN untuk melindungi jaringan.

Konfigurasi awal router

1.	Subnet adalah subdivisi atau bagian kecil dari jaringan komputer yang lebih besar.
Subnet membantu memisahkan jaringan menjadi bagian yang lebih kecil untuk mengurangi lalu lintas, meningkatkan keamanan, dan mempermudah pengelolaan.
2.	Ip class
Kelas	*Rentang IP	*Subnet Mask Default	*Jumlah Host	*Penggunaan

A	1.0.0.0 - 126.255.255.255	255.0.0.0	~16 juta	Jaringan sangat besar

B	128.0.0.0 - 191.255.255.255	255.255.0.0	~65 ribu	Jaringan menengah-besar

C	192.0.0.0 - 223.255.255.255	255.255.255.0	254	Jaringan kecil

D	224.0.0.0 - 239.255.255.255	Tidak ada	Tidak relevan	Multicast

E	240.0.0.0 - 255.255.255.255	Tidak ada	Tidak relevan	Cadangan / Eksperimen

Dimulai dari klasifikasi kelas ip 

Kelas A (0.0.0.0 - 127.255.255.255)
Kelas B (128.0.0.0 - 191.255.255.255)
Kelas C (192.0.0.0 - 223.255.255.255)
Mencoba subneting pada ip (192.168.1.0/24), disini /24 artinya ada 32 - 24 = 8 bit yang tersedia untuk bagian host, Jumlah alamat dalam /24 adalah 256 (total alamat)−2 (dikurangi 2 untuk alamat network dan broadcast) =254host.

•256 host itu di dapat dari 2 pangkat 8 yang berarti 2×2×2×2×2×2×2×2=256
•Menagapa 2 pangkat 8 karena Dalam alamat IP, setiap bit bisa bernilai 0 atau 1.

Jika ada 8 bit, maka kita bisa membuat kombinasi 0 dan 1 sebanyak 2 pangkat 8, contoh : 
00000000
00000001
00000010
Pada jaringan /24, ada 8 bit yang tersedia untuk host (bagian terakhir dari alamat IP), contoh : 192.168.0.1/24
Subnet mask digunakan untuk menentukan bagian network dan host dalam alamat IP.
Dalam subnet mask:
-	1 menunjukkan bit yang digunakan untuk network.
-	0 menunjukkan bit yang digunakan untuk host.



Subnet Mask: 255.255.255.0
-	Dalam biner, subnet mask terlihat seperti: 11111111.11111111.11111111.0000000011111111.11111111.11111111.0000000011111111.11111111.11111111.00000000
-	Ada 24 bit 1 di awal dan 8 bit 0 di akhir:
-	24 bit pertama untuk bagian network.
-	8 bit terakhir untuk bagian host.
Subnet mask 255.255.255.0 berarti :
- 255 dalam desimal berarti 11111111 dalam biner, yang menunjukkan bit jaringan. 
- 0 dalam desimal berarti 00000000 dalam biner, yang menunjukkan bit host.

Pengenalan Routing

1.	Routing adalah proses pengiriman paket data dari satu perangkat ke perangkat lain melalui jaringan komputer. Proses ini melibatkan pemilihan jalur terbaik untuk data, sehingga dapat mencapai tujuan dengan efisien.
2.	Routing Statis adalah jenis routing di mana jalur atau rute untuk pengiriman paket data ditentukan secara manual oleh administrator jaringan.
Routing Dinamis adalah metode pengaturan rute atau jalur data dalam jaringan yang dilakukan secara otomatis oleh router menggunakan protokol routing dinamis. DHCP
DHCP (Dynamic Host Configuration Protocol) adalah sebuah protokol yang digunakan untuk memberikan konfigurasi jaringan secara otomatis kepada perangkat yang terhubung ke jaringan.
	
Untuk mengatur DHCP di MikroTik Router, berikut adalah langkah-langkah yang perlu dilakukan:
1. Menyiapkan IP Address untuk MikroTik
Pastikan MikroTik memiliki IP address yang sesuai dengan jaringan yang akan dikonfigurasi. Misalnya, kita akan mengonfigurasi 192.168.1.0/24 sebagai jaringan lokal.

2. Menambahkan IP Address di MikroTik
- Masuk ke WinBox atau WebFig.
- Pilih menu IP → Addresses.
- Klik + untuk menambahkan alamat IP baru.
- Masukkan IP yang diinginkan, misalnya *192.168.1.1/24, dan pilih interface (misalnya ether1).
- Klik Apply dan *OK*.

3. Mengonfigurasi DHCP Server
- Pilih menu IP → DHCP Server.
- Klik DHCP Setup.
- Pilih interface yang ingin digunakan untuk DHCP (misalnya ether2 untuk jaringan lokal).
- Klik Next dan MikroTik akan mulai menyiapkan DHCP server.


Routing information protocol

RIP merupakan yang cara kerjanya menghitung jumlah hop sebagai routing metric dan menggunakan algoritma distance vector. Pada routing RIP juga memiliki jumlah maksimum hop yang terhitung yaitu 15 hop. Setiap routernya saling menukar informasi ketika sudah 30 detik melalui port UDP 520.



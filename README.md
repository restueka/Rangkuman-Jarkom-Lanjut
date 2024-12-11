# Rangkuman-Jarkom-Lanjut
Nama : Restu Eka Putri
NIM    : 20210801042

Pengenalan WAN dan Router 
•	WAN atau Wide Area Network adalah jenis jaringan komputer yang mencakup area geografis yang luas, seperti kota, negara, atau bahkan benua. WAN menghubungkan beberapa jaringan lokal (LAN) dan memungkinkan komunikasi antara perangkat yang berada di lokasi yang jauh dari satu sama lain. 
•	Router adalah perangkat jaringan yang berfungsi untuk menghubungkan beberapa jaringan komputer dan mengarahkan lalu lintas data antara jaringan tersebut. Router memainkan peran penting dalam komunikasi data, baik di dalam jaringan lokal (LAN) maupun di antara jaringan yang lebih luas, seperti Wide Area Network (WAN) atau Internet.
Setting IP 
Mengatur alamat IP (IP Address) pada perangkat jaringan adalah langkah penting untuk memastikan bahwa perangkat dapat berkomunikasi dengan perangkat lain di jaringan. Berikut cara-caranya :
•	Matikan Firewall seperti Windows Defender atau Antivirus lainnya
•	Sambungkan Laptop dengan MikroTik menggunakan kabel LAN
•	Buka WinBox → Neighbors → Cari yang MikroTik → Connect

Pengenalan Routing dan Routing Statis
Router bertugas untuk menentukan jalur terbaik bagi paket data berdasarkan informasi yang terdapat dalam tabel routing. Routing sangat penting dalam jaringan komputer, terutama dalam konteks Wide Area Network (WAN) dan Internet.
Komponen Utama Routing :
•	Router : Perangkat yang mengarahkan lalu lintas data antara jaringan.
•	Tabel Routing : Struktur data yang menyimpan informasi tentang jalur yang tersedia untuk mencapai alamat IP tertentu.
•	Protokol Routing : Aturan yang digunakan oleh router untuk berbagi informasi routing dan memperbarui tabel routing. Contoh protokol routing termasuk RIP (Routing Information Protocol), OSPF (Open Shortest Path First), dan BGP (Border Gateway Protocol).
Jenis Routing :
•	Routing Statis : Pengaturan rute secara manual oleh administrator jaringan.
Routing Dinamis : Pengaturan rute secara otomatis menggunakan protokol routing untuk menyesuaikan dengan perubahan dalam jaringan. 
Routing Statis adalah metode pengaturan rute di mana administrator jaringan secara manual menentukan jalur yang akan diambil oleh paket data. Ini biasanya digunakan dalam jaringan kecil atau ketika jalur tetap dan tidak sering berubah.
Karakteristik Routing Statis :
•	Konfigurasi Manual : Administrator harus secara manual mengkonfigurasi setiap rute di router.
•	Stabilitas : Rute yang ditetapkan tidak berubah kecuali administrator melakukan perubahan.
•	Sederhana : Mudah dipahami dan diimplementasikan, terutama dalam jaringan kecil.
Static (Manual)
•	Dalam WinBox → IP → Addresses
•	Tambahkan IP Address baru → Contohnya 192.168.10.1/24 → Sesuaikan interface dengan ether dari sambungan kabel LAN → Apply → Ok
•	Buka Control Panel untuk mengatur IP Laptop
Control Panel → Network and Internet → Network and Sharing Center → Ethernet → Properties
•	Ubah IPv4 dengan double click → Use the following IP Address → Isi dengan 192.168.10.2 (2 karena 1 sudah digunakan MikroTik) → Tab untuk kolom yang lain → Ok
•	Lakukan Ping terhadap IP Laptop dalam Terminal WinBox
DHCP (Otomatis)
•	Dalam WinBox → IP → Addresses
•	Tambahkan IP Address baru → Contohnya 192.168.10.1/24 → Sesuaikan interface dengan ether dari sambungan kabel LAN → Apply → Ok
•	Buka Control Panel untuk mengatur IP Laptop
Control Panel → Network and Internet → Network and Sharing Center → Ethernet → Properties
•	Ubah IPv4 dengan double click → Obtain an IP Address automatically → Ok
•	Dalam WinBox → IP → DHCP Server
•	Tambahkan DHCP dengan DHCP Setup → Sesuaikan interface dengan ether yang digunakan → Klik Next sampai selesai
•	Buka bagian Leases dalam DHCP Server → Lihat IP dalam bagian Active Addresses
•	Lakukan Ping terhadap IP Address yang ada dalam Leases di Terminal WinBox
Subnet
Subnetting adalah proses membagi jaringan IP menjadi beberapa subnet yang lebih kecil. Dalam konteks ini, ada tiga kelas utama dari alamat IP yang dikenal sebagai Kelas A, Kelas B, dan Kelas C. Masing-masing kelas memiliki rentang alamat dan jumlah host yang berbeda. Berikut adalah penjelasan singkat tentang masing-masing kelas :
•	Class A 
Rentang Alamat : 1.0.0.0 hingga 126.255.255.255
Subnet Mask Default : 255.0.0.0 (atau /8)
Jumlah Subnet : Sangat sedikit, tetapi dapat mendukung banyak host (sekitar 16 juta host per subnet).
Penggunaan : Kelas A biasanya digunakan oleh organisasi besar dan penyedia layanan internet.
•	Class B
Rentang Alamat : 128.0.0.0 hingga 191.255.255.255
Subnet Mask Default : 255.255.0.0 (atau /16)
Jumlah Subnet : Lebih banyak daripada Kelas A, dengan dukungan untuk sekitar 65.000 host per subnet.
Penggunaan : Kelas B sering digunakan oleh perusahaan menengah dan besar. 
•	Class C
Rentang Alamat : 192.0.0.0 hingga 223.255.255.255
Subnet Mask Default : 255.255.255.0 (atau /24)
Jumlah Subnet : Sangat banyak, tetapi hanya mendukung hingga 254 host per subnet.
Penggunaan : Kelas C biasanya digunakan untuk jaringan kecil, seperti jaringan rumah atau kantor kecil.
Lalu melakukan subnetting yaitu pembagian jaringan misal pada ip (192.168.1.0/24), disini /24 artinya ada 32 - 24 = 8 bit yang tersedia untuk bagian host, Jumlah alamat dalam /24 adalah 256 (total alamat)−2 (dikurangi 2 untuk alamat network dan broadcast) =254host.
•	256 host itu di dapat dari 2 pangkat 8 yang berarti 2×2×2×2×2×2×2×2=256
•	Menagapa 2 pangkat 8 karena Dalam alamat IP, setiap bit bisa bernilai 0 atau 1.
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
-	Dalam biner, subnet mask ini terlihat seperti: 11111111.11111111.11111111.0000000011111111.11111111.11111111.0000000011111111.11111111.11111111.00000000
-	Ada 24 bit 1 di awal dan 8 bit 0 di akhir:
-	24 bit pertama untuk bagian network.
-	8 bit terakhir untuk bagian host.
Subnet mask 255.255.255.0 berarti :
- 255 dalam desimal berarti 11111111 dalam biner, yang menunjukkan bit jaringan.
CIDR	Subnet mask	Wildcard mask	# of IP addresses	# of usable IP addresses
/23	255.255.254.0	0.0.1.255	512	510
/24	255.255.255.0	0.0.0.255	256	254
/25	255.255.255.128	0.0.0.127	128	126
/26	255.255.255.192	0.0.0.63	64	62
/27	255.255.255.224	0.0.0.31	32	30
/28	255.255.255.240	0.0.0.15	16	14
/29	255.255.255.248	0.0.0.7	8	6
/30	255.255.255.252	0.0.0.3	4	2
/31	255.255.255.254	0.0.0.1
	2	2*
/32	255.255.255.255	0.0.0.0	1	1

Bridge
•	Dalam WinBox → Bridge
•	Tambahkan Bridge baru → Apply → Ok
•	Tambahkan Bridge Port → Sesuaikan interface dengan ether yang digunakan → Sesuaikan Bridge dengan Bridge yang sudah dibuat → Apply → Ok
•	Tambahkan IP Address → Ubah interface dengan Bridge yang sudah dibuat → Apply → Ok
•	Tambahkan DHCP dengan DHCP Setup → Sesuaikan interface dengan Bridge yang sudah dibuat → Klik Next → Pada bagian DNS Servers ubah menjadi 8.8.8.8 → Klik Next sampai selesai
•	Buka Command Prompt → ipconfig → Lihat IPv4 Address → Lakukan Ping terhadap sesama Laptop (Laptop A melakukan Ping terhadap IP Laptop B dan sebaliknya)
•	Buka XAMPP dan nyalakan → Salin IP Address Laptop satu sama lain untuk melihat web XAMPP jika sudah tersambung

Untuk mengkonfigurasi bridge dalam jaringan, Anda dapat menggunakan berbagai perangkat dan alat. Berikut adalah beberapa opsi yang umum digunakan :
1. Perangkat Jaringan
a. Router
Router dengan Fitur Bridge : Beberapa router memiliki opsi untuk berfungsi sebagai bridge, memungkinkan Anda untuk menghubungkan dua jaringan yang berbeda.
b. Bridge Hardware
Bridge Device : Ada perangkat khusus yang dirancang untuk berfungsi sebagai bridge, yang dapat menghubungkan dua segmen jaringan secara langsung.
2. Sistem Operasi
a. Windows
Network Connections: Di Windows, Anda dapat mengkonfigurasi bridge melalui antarmuka grafis di "Network Connections". Anda dapat memilih dua atau lebih koneksi jaringan, klik kanan, dan pilih "Bridge Connections".
3. Perangkat Lunak Jaringan
a. Virtualisasi
Software Virtualization: Jika Anda menggunakan perangkat lunak virtualisasi seperti VMware atau VirtualBox, Anda dapat mengkonfigurasi bridge virtual untuk menghubungkan mesin virtual ke jaringan fisik.
A.	Static Routing
1.	Sambungkan Laptop dengan MikroTik seperti berikut:
•	Hubungkan MikroTik A → Laptop A → ether1
•	Hubungkan MikroTik B → Laptop B → ether1
•	Hubungkan kedua MikroTik → ether3
2.	Dalam WinBox → IP → Addresses → Tambahkan IP Address seperti berikut:
•	Laptop A → 192.168.1.1/24
•	Laptop B → 192.168.10.1/24
Tambahkan IP Address untuk MikroTik seperti berikut:
•	Laptop A → 192.168.100.1/24
•	Laptop B → 192.168.100.2/24
3.	Tambahkan DHCP dengan DHCP Setup → Buat 2 DHCP dan sesuaikan dengan interface yang digunakan IP Address ether1 dan IP MikroTik ether3 → Klik Next → Pada bagian DNS Servers ubah menjadi 8.8.8.8 → Klik Next sampai selesai
4.	Buka Control Panel → Network and Internet → Network and Sharing Center → Ethernet → Disable → Change adapter settings → Double click Ethernet untuk Enable kembali
5.	Dalam WinBox → IP → Routes → Tambahkan Routes seperti berikut:
•	Laptop A → Isi Destination dengan 192.168.10.0/24 dan Gateway dengan 192.168.100.2
•	Laptop B → Isi Destination dengan 192.168.1.0/24 dan Gateway dengan 192.168.100.1
6.	Buka Command Prompt → ipconfig → Lihat IPv4 Address → Lakukan Ping terhadap sesama Laptop (Laptop A melakukan Ping terhadap IP Mikrotik B dan Laptop B dan sebaliknya)
7.	Lakukan “tracert -d (IP tujuan)” untuk mengecek jalur apa saja yang dilewati untuk mencapai IP tujuan → Contohnya Laptop A melakukan “tracert -d 192.168.10.1/24” dan Laptop B melakukan “tracert -d 192.168.1.1/24”

Routing Information Protocol (RIP)
RIP adalah protokol routing berbasis distance-vector yang digunakan untuk mengatur dan mengelola rute dalam jaringan berbasis IP.
Distance Vector : Menggunakan jumlah hop sebagai metrik untuk menentukan jarak ke tujuan.
Metrik : Maksimum 15 hop, lebih dari 15 dianggap tidak dapat dijangkau.
Update Periodik : Mengirim pembaruan routing setiap 30 detik secara default.
Sederhana : Mudah diimplementasikan, tetapi kurang efisien dibandingkan protokol routing yang lebih canggih.
Versi RIP :
RIP Version 1 (RIPv1) : Tidak mendukung subnetting, menggunakan alamat kelas penuh.
RIP Version 2 (RIPv2) : Mendukung subnetting, autentikasi, dan pengiriman informasi routing multicast.
Cara Kerja :
Inisialisasi : Router mengirim informasi routing ke tetangga saat dihidupkan.
Penghitungan Hop : Menghitung jumlah hop ke setiap tujuan dan menyimpan dalam tabel routing.
Pembaruan : Mengirim pembaruan tabel routing secara berkala.
Pemilihan Rute : Memilih rute dengan jumlah hop terendah untuk pengiriman paket.
Kelebihan :
•	Mudah dikonfigurasi.
•	Kompatibel dengan banyak perangkat.
Kekurangan :
•	Terbatas untuk jaringan kecil (maksimum 15 hop).
•	Konvergensi lambat.
•	Penggunaan bandwidth yang tidak efisien.














  

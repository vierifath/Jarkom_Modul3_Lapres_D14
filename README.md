# Jarkom_Modul3_Lapres_D14
 
### KELOMPOK        : D14
ANGGOTA         :

* Muhammad Haris W.     (05111840000029)
* Vieri Fath Ayuba      (05111840000153)

## Jawaban Soal Praktikum Jarkom Modul 3

### Soal No. 1
#### 1. Membuat topologi :

- Lakukan konfigurasi topologi.sh sebagai berikut :

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/topo.JPG" >


- Setelah itu mengatur nano /etc/network/interfaces pada setiap uml

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/1A.JPG" >
<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/1B.JPG" >
<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/1C.JPG" >
<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/1D.JPG" >

- Serta memberikan perintah apt-get update juga pada setiap UML untuk melakukan update.




### Soal No. 2
#### 2. SURABAYA ditunjuk sebagai perantara (DHCP Relay) antara DHCP Server dan client

- Install dhcp-relay pada surabaya : 

      apt-get install isc-dhcp-relay 
      
- Konfigurasi interface dhcp-relay pada surabaya : 

      nano /etc/default/isc-dhcp-relay .
      
- Menambahkan SERVERS="10.151.79.124" dalam DHCP relay forward

- menambahkan INTERFACES="eth1 eth2 eth3" dalam interface DHCP relay request

- Lalu Restart : 

      service isc-dhcp-relay restart

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/2A.JPG" >






### Soal No. 3
#### 3. Client pada subnet 1 mendapatkan range IP dari 192.168.0.10 sampai 192.168.0.100 dan 192.168.0.110 sampai 192.168.0.200

- Pertama buka nano isc-dhcp-server dalam tuban

      etc/default/isc-dhcp-server

- menambahkan INTERFACEv4="eth0"

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/3A.JPG" >

- nano etc/dhcp/dhcp.conf dalam tuban

- Konfigurasi Tuban sebagai berikut :

- service isc-dhcp-server restart

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/3B.JPG" >

- Melakukan konfigurasi Gresik dengan melakukan

      ifconfig
      
<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/3C.JPG" >

- Melakukan konfigurasi Sidoarjo dengan melakukan

      ifconfig
      
<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/3D.JPG" >





### Soal No. 4
#### 4. Client pada subnet 3 mendapatkan range IP dari 192.168.1.50 sampai 192.168.1.70.

- Buka dhcp nano etc/dhcp/dhcp.conf dalam tuban

      nano etc/dhcp/dhcp.conf

- Ubah range IP
- Konfigurasi pada dhcp.conf pada Tuban sebagai berikut :

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/4A.JPG" >


- Lakukan konfigurasi pada Banyuwangi dan Madiun dengan melakukan ifconfig

      ifconfig
      


<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/4B.JPG" >
<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/4C.JPG" >





### Soal No. 5
#### 5. Client pada subnet 3 mendapatkan range IP dari 192.168.1.50 sampai 192.168.1.70.

- Lakukan konfigurasi pada dhcp.conf dalam tuban dengan mengetikkan

      nano etc/dhcp/dhcp.conf 
      
- Mengubah domain-name-servers sebagai berikut :

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/5A.JPG" >




### Soal No. 6
#### 6. Client di subnet 1 mendapatkan peminjaman alamat IP selama 5 menit, sedangkan client pada subnet 3 mendapatkan peminjaman IP selama 10 menit.

- Lakukan konfigurasi pada dhcp.conf dalam tuban dengan mengetikkan

      nano etc/dhcp/dhcp.conf 
      
- Ubah default-lease-time dan max-lease-time pada subnet 1 dan 3
- Pada subnet 1 diaru default-lease-time 300 (5menit)
- Pada subnet 3 ditulis default-lease-time 600 (10menit)
- Konfigurasinya sebagai berikut :

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/6A.JPG" >




### Soal No. 7
#### 7. Akses ke proxy hanya bisa dilakukan oleh Anri sendiri sebagai user TA.

- Pastikan pada UML Mojokerto sudah terinstall squid dan apache2-utils. Lalu ketikkan:
- Buat user dan password baru dengan mengetikkan:
htpasswd -c /etc/squid/passwd userta_c04








      
      

































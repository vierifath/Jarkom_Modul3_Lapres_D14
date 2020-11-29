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

- nano etc/default/isc-dhcp-server dalam tuban

- menambahkan INTERFACEv4="eth0"

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/3A.JPG" >

- nano etc/dhcp/dhcp.conf dalam tuban

- service isc-dhcp-server restart

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/3B.JPG" >


<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/3C.JPG" >
<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/3D.JPG" >






      
      

































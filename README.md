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

       htpasswd -c /etc/squid/passwd userta_d14

- Format user dan password sebagai berikut

```
User : userta_c04
Password : inipassw0rdta_c04 
```

- Cek username dan password dengan mengetikkan : 
     
      nano etc/squid/passwd

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/7A.JPG" >

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/7C.JPG" >

- Edit konfigurasi squid pada /etc/squid/squid.conf menjadi:


<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/7B.JPG" >

- Lakukan restart squid

       Restart squid: service squid restart
       
- Ubah pengaturan proxy browser. Gunakan IP MOJOKERTO sebagai host dan isikan port 8080.

- Testing : Buka browser, maka akan muncul authencation required seperti sebagai berikut :

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/7C.JPG" >



### Soal No. 8
#### 8. Anri sudah menjadwal pengerjaan TA-nya setiap hari Selasa-Rabu pukul 13.00-18.00.

- Edit konfigurasi squid pada /etc/squid/squid.conf, tambahkan :

       acl ONE time TW 13:00-18:00
       
 <img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/8A.JPG" >
 
 
- Konfigurasi MOJOKERTO sebagai berikut :

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/7B.JPG" >


- Lakukan restart squid

       Restart squid: service squid restart
       
- Testing : buka browser. Akan muncul halaman error jika mengakses di luar waktu yang ditentukan


### Soal No. 9
#### 9. Jadwal bimbingan dengan Bu Meguri adalah setiap hari Selasa-Kamis pukul 21.00 - 09.00 keesokan harinya (sampai Jumat jam 09.00).

- Edit konfigurasi squid pada /etc/squid/squid.conf, tambahkan :

```
acl TWO time TWH 21:00-23:59
acl THREE time WHF 00:00-09:00

```

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/8A.JPG" >

-  Selain dapat mengakses internet pada waktu yang telah ditentukan, Anri juga bisa mengakses internet saat ada jadwal bimbingan dengan Bu Meguri, yaitu hari Selasa-Kamis pukul 21.00 - 09.00 keesokan harinya.


- Konfigurasi MOJOKERTO sebagai berikut :

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/7B.JPG" >

- Lakukan restart squid

       Restart squid: service squid restart

- Testing : buka browser. Akan muncul halaman error jika mengakses di luar waktu yang ditentukan

### Soal No. 10
#### 10. Agar Anri bisa fokus mengerjakan TA, setiap dia mengakses google.com, maka akan di redirect menuju monta.if.its.ac.id agar Anri selalu ingat untuk mengerjakan TA🙂.


- Edit konfigurasi squid pada /etc/squid/squid.conf sebagai berikut

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/8A.JPG" >

#### Pada nomer 10, kami belum menemukan solusi untuk redirect google.com ke monta.if.its.ac.id. 
#### Namun, dengan konfigurasi yang sama kami dapat redirect dari facebook.com ke monta.if.its.ac.id
#### Kami sudah melakukan konfigurasi dengan berbagai cara namun masih belum bisa ke redirect ke monta.if.its.ac.id ( hanya google.com ke block saja )





### Soal No. 11
#### 11. Untuk menandakan bahwa Proxy Server ini adalah Proxy yang dibuat oleh Anri, Bu Meguri meminta Anri untuk mengubah error page default squid.

- Unduh file error dengan mengetikkan wget 10.151.36.202/ERR_ACCESS_DENIED

- Copy file tersebut ke /usr/share/squid/errors/English/

- Lakukan restart squid

       Restart squid: service squid restart
       
- Kemudian buka browser. Akan muncul halaman error yang terbaru jika mengakses di luar waktu yang ditentukan.

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/11A.JPG" >


### Soal No. 12
#### 12. Karena Bu Meguri dan Anri adalah tipe orang pelupa, maka untuk memudahkan mereka, Anri memiliki ide ketika menggunakan proxy cukup dengan mengetikkan domain janganlupa-ta.d14.pw dan memasukkan port 8080.


- Buka konfigurasi named.conf.local 
               
       nano /etc/bind/named.conf.local.

- Lakukan konfigurasi domain janganlupa-ta.d14.pw, sesuai dengan konfigurasi berikut:

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/12A.JPG" >


- Buat folder jarkom di dalam /etc/bind : mkdir /etc/bind/jarkom

- Buka file janganlupa-ta.d14.pw serta edit dengan gambar sebagai berikut :

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/12B.JPG" >

- Restart bind9 : 

      service bind9 restart
      
- Lakukan setting proxy pada browser. Gunakan domain : janganlupa-ta.d14.pw sebagai host dan isikan port 8080.

- Testing : Buka browser, maka akan muncul authencation required seperti sebagai berikut :

<img src="https://github.com/vierifath/Jarkom_Modul3_Lapres_D14/blob/main/img/12C.JPG" >




























      
      

































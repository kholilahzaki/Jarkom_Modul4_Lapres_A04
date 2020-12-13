# Jarkom_Modul4_Lapres_A04
Lapres Jarkom Modul 4 A04

Kelompok A04:
-
#### I Gusti Agung Chintya Prema Dewi   (05111840000130)
#### Kholilah Zaki Lismia               (05111840000159)

## Penyelesaian
Kelompok A04 menggunakan VLSM pada CPT dan CIDR pada UML.

### VLSM
---------------------------------
### Subnetting
  1. Melakukan subnetting pada topologi yang diberikan. Sehingga terbentuklah 13 subnet di dalam topologi seperti pada gambar berikut.
  ![topologi soal](https://user-images.githubusercontent.com/61299072/102007739-3d52f880-3d5e-11eb-926c-832b1c7372c2.PNG)

  2. Menentukan jumlah alamat IP yang dibutuhkan oleh tiap subnet dan lmelakukan labelling netmask berdasarkan jumlah IP yang dibutuhkan.
      | Subnet      | Jumlah IP   | Netmask |
      | ----------- |         ---:| ------- |
      | A1          | 721         | /22     |
      | A2          | 252         | /24     |
      | A3          | 13          | /28     |
      | A4          | 502         | /23     |
      | A5          | 521         | /22     |
      | A6          | 2           | /30     |
      | A7          | 2           | /30     |
      | A8          | 2           | /30     |
      | A9          | 701         | /22     |
      | A10         | 2           | /30     |
      | A11         | 2021        | /21     |
      | A12         | 101         | /25     |
      | A13         | 1001        | /22     |
      | Total       | 5841        | /19     |
      
      Berdasarkan total IP dan netmask yang dibutuhkan, maka dapat menggunakan netmask /19 untuk memberikan pengalamatan IP pada subnet.
  3.  Subnet besar yang dibentuk memiliki NID 192.168.0.0 dengan netmask /19. Selanjutnya menghitung pembagian IP berdasarkan NID dan netmask tersebut menggunakan pohon seperti gambar berikut.
      ![vlsm_tree](img/vlsm_tree.png)

### CPT

   1. Membuat topologi pada CPT
        ![vlsm_cpt](img/vlsm_cpt.png)
   2. Mengatur IP untuk masing masing interface yang ada disetiap device sesuai dengan pembagian subnet pada pohon VLSM.
        ![ip_router](img/ip_router.png)
   3. Melakukan Routing pada setiap router
        ![routing](img/routing.png)
        
      
### CIDR
-----------------------------

### Subnetting

1. Tentukan subnet yang ada dalam topologi dan lakukan labelling netmask terhadap masing-masing subnet seperti berikut
<p align="center"><img width="auto" src="https://user-images.githubusercontent.com/61299072/102007415-8bb2c800-3d5b-11eb-8ba9-6bee5b581d67.PNG"></p><br>

<p align="center"><img width="auto" src="https://user-images.githubusercontent.com/61299072/102007417-8d7c8b80-3d5b-11eb-9036-d68f640cd2f4.PNG"></p><br>

<p align="center"><img width="auto" src="https://user-images.githubusercontent.com/61299072/102007421-8fdee580-3d5b-11eb-9734-edece057f045.PNG"></p><br>

<p align="center"><img width="auto" src="https://user-images.githubusercontent.com/61299072/102007422-91101280-3d5b-11eb-9c6a-8d60af84b78f.PNG"></p><br>

<p align="center"><img width="auto" src="https://user-images.githubusercontent.com/61299072/102007423-92413f80-3d5b-11eb-9bc7-9f8f7356f572.PNG"></p><br>

<p align="center"><img width="auto" src="https://user-images.githubusercontent.com/61299072/102007424-92d9d600-3d5b-11eb-9ade-662b1b28db68.PNG"></p><br>

<p align="center"><img width="auto" src="https://user-images.githubusercontent.com/61299072/102007426-940b0300-3d5b-11eb-998c-df66b0f7ffba.PNG"></p><br>

2. Dari proses tersebut didapatkan subnet besar dengan NID 192.168.0.0 dengan netmask /16.
3. Hitung pembagian IP dengan pohon berdasarkan penggabungan subnet yang telah dilakukan.
![bisa](https://user-images.githubusercontent.com/61299072/102007794-9458cd80-3d5e-11eb-8cdf-903cb4fad86f.PNG)

4. Lalu lakukan routing dengan pembagian sebagai berikut
![hasil routing](https://user-images.githubusercontent.com/61299072/102007835-d97cff80-3d5e-11eb-808d-5f3e7c7be8ce.PNG)

### Praktik pada UML
1. Buatlah topologi seperti berikut
```
#Switch
uml_switch -unix switch0 > /dev/null < /dev/null &
uml_switch -unix switch1 > /dev/null < /dev/null &
uml_switch -unix switch2 > /dev/null < /dev/null &
uml_switch -unix switch3 > /dev/null < /dev/null &
uml_switch -unix switch4 > /dev/null < /dev/null &
uml_switch -unix switch5 > /dev/null < /dev/null &
uml_switch -unix switch6 > /dev/null < /dev/null &
uml_switch -unix switch7 > /dev/null < /dev/null &
uml_switch -unix switch8 > /dev/null < /dev/null &
uml_switch -unix switch9 > /dev/null < /dev/null &
uml_switch -unix switch10 > /dev/null < /dev/null &
uml_switch -unix switch11 > /dev/null < /dev/null &
uml_switch -unix switch12 > /dev/null < /dev/null &
uml_switch -unix switch13 > /dev/null < /dev/null &
uml_switch -unix switch14 > /dev/null < /dev/null &

# Router
xterm -T SURABAYA -e linux ubd0=SURABAYA,jarkom umid=SURABAYA eth0=tuntap,,,10.151.73.21 eth1=daemon,,,switch1 eth2=daemon,,,switch2 eth3=daemon,,,switch7 eth4=daemon,,,switch0 mem=64M &
xterm -T PASURUAN -e linux ubd0=PASURUAN,jarkom umid=PASURUAN eth0=daemon,,,switch2 eth1=daemon,,,switch3 eth2=daemon,,,switch8 mem=64M &
xterm -T PROBOLINGGO -e linux ubd0=PROBOLINGGO,jarkom umid=PROBOLINGGO eth0=daemon,,,switch3 eth1=daemon,,,switch4 eth2=daemon,,,switch9 mem=64M &
xterm -T BATU -e linux ubd0=BATU,jarkom umid=BATU eth0=daemon,,,switch7 eth1=daemon,,,switch11 eth2=daemon,,,switch10 eth3=daemon,,,switch6 mem=64M &
xterm -T MADIUN -e linux ubd0=MADIUN,jarkom umid=MADIUN eth0=daemon,,,switch6 eth1=daemon,,,switch5 mem=64M &
xterm -T KEDIRI -e linux ubd0=KEDIRI,jarkom umid=KEDIRI eth0=daemon,,,switch11 eth1=daemon,,,switch14 eth2=daemon,,,switch12 mem=64M &
xterm -T BLITAR -e linux ubd0=BLITAR,jarkom umid=BLITAR eth0=daemon,,,switch14 eth1=daemon,,,switch13 mem=64M &

# Server
xterm -T MOJOKERTO -e linux ubd0=MOJOKERTO,jarkom umid=MOJOKERTO eth0=daemon,,,switch0 mem=64M &
xterm -T MALANG -e linux ubd0=MALANG,jarkom umid=MALANG eth0=daemon,,,switch12 mem=64M &

# Klien
xterm -T SAMPANG -e linux ubd0=SAMPANG,jarkom umid=SAMPANG eth0=daemon,,,switch1 mem=64M &
xterm -T BONDOWOSO -e linux ubd0=BONDOWOSO,jarkom umid=BONDOWOSO eth0=daemon,,,switch4 mem=64M &
xterm -T JEMBER -e linux ubd0=JEMBER,jarkom umid=JEMBER eth0=daemon,,,switch9 mem=64M &
xterm -T BANYUWANGI -e linux ubd0=BANYUWANGI,jarkom umid=BANYUWANGI eth0=daemon,,,switch9 mem=64M &
xterm -T SIDOARJO -e linux ubd0=SIDOARJO,jarkom umid=SIDOARJO eth0=daemon,,,switch8 mem=64M &
xterm -T JOMBANG -e linux ubd0=JOMBANG,jarkom umid=JOMBANG eth0=daemon,,,switch6 mem=64M &
xterm -T BOJONEGORO -e linux ubd0=BOJONEGORO,jarkom umid=BOJONEGORO eth0=daemon,,,switch5 mem=64M &
xterm -T NGANJUK -e linux ubd0=NGANJUK,jarkom umid=NGANJUK eth0=daemon,,,switch10 mem=64M &
xterm -T LUMAJANG -e linux ubd0=LUMAJANG,jarkom umid=LUMAJANG eth0=daemon,,,switch14 mem=64M &
xterm -T TULUNGAGUNG -e linux ubd0=TULUNGAGUNG,jarkom umid=TULUNGAGUNG eth0=daemon,,,switch13 mem=64M &
```

2. Pada UML, setting interface pada setiap UML dengan menjalankan perintah `nano /etc/network/interfaces` kemudian restart network dengan perintah `service networking restart`. Untuk UML yang merupakan router, juga harus di-uncomment pada perintah net.ipv4.ip_forward=1 pada file sysctl.conf, dapat dibuka dengan mengetikkan `nano /etc/sysctl.conf` dan untuk restart gunakan `sysctl -p`. Jangan lupa di setiap UML yang merupakan router buatlah file iptables.sh yang berisi `iptables –t nat –A POSTROUTING –o eth0 –j MASQUERADE –s 192.168.0.0/16` dan jalankan iptables setelah konfigurasi interface selesai dengan perintah `bash iptables.sh`. Berikut setting file /etc/network/interfaces untuk setiap UML:

**SURABAYA**
<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102008006-07167880-3d60-11eb-88ae-c752435c3216.PNG"></p><br>

<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102008008-07af0f00-3d60-11eb-911e-cf169958e153.PNG"></p><br>

**PASURUAN**
<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102008001-054cb500-3d60-11eb-85db-60af7ae39135.PNG"></p><br>

**PROBOLINGGO**
<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102008002-054cb500-3d60-11eb-99f6-1f9f0a0cad73.PNG"></p><br>

**BATU**
<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102007983-fcf47a00-3d5f-11eb-83b1-52e1e8eaed62.PNG"></p><br>

<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102007984-fd8d1080-3d5f-11eb-886c-51a690c2a44d.PNG"></p><br>

**MADIUN**
<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102007995-02ea5b00-3d60-11eb-9eac-aa68b2082e3b.PNG"></p><br>

**KEDIRI**
<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102007991-01b92e00-3d60-11eb-9b81-7074fe5ef52c.PNG"></p><br>

**BLITAR**
<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102007985-fe25a700-3d5f-11eb-9509-29264056d89c.PNG"></p><br>

**MOJOKERTO**
<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102007999-041b8800-3d60-11eb-951a-d79fb173e3c5.PNG"></p><br>

**MALANG**
<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102007996-0382f180-3d60-11eb-85b3-95f03f104dc3.PNG"></p><br>

**SAMPANG**
<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102008004-05e54b80-3d60-11eb-8e67-50cabdacfa01.PNG"></p><br>

**BONDOWOSO**
<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102007988-ffef6a80-3d5f-11eb-9de1-d2fd7f322189.PNG"></p><br>

**JEMBER**
<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102007989-00880100-3d60-11eb-9f39-e217cfb20fbf.PNG"></p><br>

**BANYUWANGI**
<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102008008-07af0f00-3d60-11eb-911e-cf169958e153.PNG"></p><br>

**SIDOARJO**
<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102008005-067de200-3d60-11eb-8f8a-963fccea0cb7.PNG"></p><br>

**JOMBANG**
<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102007990-01209780-3d60-11eb-9a18-8716e70cff33.PNG"></p><br>

**BOJONEGORO**
<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102007987-febe3d80-3d5f-11eb-9f7e-017d4f498599.PNG"></p><br>

**NGANJUK**
<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102008000-04b41e80-3d60-11eb-9159-82467315da67.PNG"></p><br>

**LUMAJANG**
<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102007994-0251c480-3d60-11eb-82f0-2228d4c6d54a.PNG"></p><br>

**TULUNGAGUNG**
<p align="center"><img width="600" src="https://user-images.githubusercontent.com/61299072/102008011-0847a580-3d60-11eb-8a17-81b4ede0e9f8.PNG"></p><br>

3. Untuk routing, masukkan konfigurasi sebagai berikut pada `route.sh` agar saat UML di restart konfigurasi untuk routing tidak hilang
- Surabaya
```
route add -net 192.168.128.0 netmask 255.255.192.0 gw 192.168.192.2
route add -net 192.168.0.0 netmask 255.255.224.0 gw 192.168.32.2
route add -net 10.151.73.44 netmask 255.255.255.252 gw 192.168.32.2
```

- Batu
```
route add -net 192.168.0.0 netmask 255.255.248.0 gw 192.168.8.2
route add -net 192.168.18.0 netmask 255.255.255.240 gw 192.168.16.2
route add -net 10.151.73.44 netmask 255.255.255.252 gw 192.168.8.2
```

- Kediri
```
route add -net 192.168.0.0 netmask 255.255.252.0 gw 192.168.4.2
```

- Pasuruan
```
route add -net 192.168.128.0 netmask 255.255.240.0 gw 192.168.144.2
```

Untuk menjalankan route.sh, bisa dengan menggunakan perintah `source route.sh`.

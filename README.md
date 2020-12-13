# Jarkom_Modul4_Lapres_A04
Lapres Jarkom Modul 4 A04

## VLSM
### Subnetting
  1. Melakukan subnetting pada topologi yang diberikan. Sehingga terbentuklah 13 subnet di dalam topologi seperti pada gambar berikut.
     *gambar*
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
      *gambar*

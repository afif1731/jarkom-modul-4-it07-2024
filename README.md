# Laporan Resmi Praktikum Jarkom Modul 2 - Kelompok IT07

| Nama              | NRP        |
| ----------------- | ---------- |
| Muhammad Afif     | 5027221032 |
| Alma Amira Dewani | 5027221054 |

## Soal

1. Soal shift dikerjakan pada `Cisco Packet Tracer` dan `GNS3` menggunakan metode perhitungan CLASSLESS yang **berbeda**.
2. Keterangan: Bila di **CPT menggunakan VLSM**, maka di **GNS3 menggunakan CIDR** atau **sebaliknya**.
3. Jika tidak ada pemberitahuan revisi soal dari asisten, berarti semua soal **BERSIFAT BENAR** dan **DAPAT DIKERJAKAN**.
4. Untuk di GNS3 `CLOUD` merupakan `NAT1` jangan sampai salah agar bisa terkoneksi internet.
5. Pembagian IP menggunakan Prefix IP yang telah ditentukan pada modul pengenalan
6. Pembagian IP dan routing harus **SE-EFISIEN MUNGKIN**.
7. Seluruh node yang ada pada topologi harus dapat **TERKONEKSI** satu sama lain dan dapat melakukan **PING** ke node lainnya yang ada di topologi
8. Gambar topologi yang lebih jelas dapat diakses pada link berikut

### Topologi CPT

![modul](./img/topo_modul4.png)

### Topologi GNS

![modu2](./img/gns-topologi.png)

## Penyelesaian

Pembagian:

- Pada `GNS3` menggunakan `VLSM`
- Pada `CPT` menggunakan `CIDR`

### Prefix IP IT07

```bash
10.67
```

### Pelabelan Subnet

![label_subnet](./img/topologi_w_label.png)

## Rute

Berikut merupakan hasil rute yang kami gunakan
![rute](./img/rute.png)

## GNS3 - VLSM

### Tree

Berikut merupakan hasil pemecahan subnet besar yang akan dibentuk menjadi jaringan yang lebih ke
![tree vlsm](./img/tree-vlsm.png)

### Pembagian IP

Berikut adalah hasil dari pembagian IP yang telah kami peroleh dari tree sebelumnya
![ip vlsm](./img/ip-vlsm.png)

### Konfigurasi Network

- JAWA

```
auto lo
iface lo inet loopback

auto eth0
iface eth0 inet dhcp

#A7
auto eth1
iface eth1 inet static
address 10.67.21.185
netmask 255.255.255.252

#A15
auto eth2
iface eth2 inet static
address 10.67.21.201
netmask 255.255.255.252

#A21
auto eth3
iface eth3 inet static
address 10.67.21.205
netmask 255.255.255.252
```

- Berawang-Tempu (53 host)

```
#A1
auto eth0
iface eth0 inet static
address 10.67.20.130
netmask 255.255.255.128
gateway 10.67.20.129
```

- Enang-Enang (27 host)

```
#A1
auto eth0
iface eth0 inet static
address 10.67.20.131
netmask 255.255.255.128
gateway 10.67.20.129
```

- Starland (44 host)

```
#A1
auto eth0
iface eth0 inet static
address 10.67.20.132
netmask 255.255.255.128
gateway 10.67.20.129
```

- Sabang (6 host)

```
#A2
auto eth0
iface eth0 inet static
address 10.67.21.130
netmask 255.255.255.224
gateway 10.67.21.129
```

- Lambaro (8 host)

```
#A2
auto eth0
iface eth0 inet static
address 10.67.21.131
netmask 255.255.255.224
gateway 10.67.21.129
```

- ACEH

```
auto lo
iface lo inet loopback

#A3
auto eth0
iface eth0 inet static
address 10.67.21.178
netmask 255.255.255.252
gateway 10.67.21.177

#A1
auto eth1
iface eth1 inet static
address 10.67.20.129
netmask 255.255.255.128

#A2
auto eth2
iface eth2 inet static
address 10.67.21.129
netmask 255.255.255.224
```

- SUMATERA UTARA

```
auto lo
iface lo inet loopback

#A4
auto eth0
iface eth0 inet static
address 10.67.21.98
netmask 255.255.255.224
gateway 10.67.21.97

#A3
auto eth1
iface eth1 inet static
address 10.67.21.177
netmask 255.255.255.252
```

- Samosir (14 host)

```
#A4
auto eth0
iface eth0 inet static
address 10.67.21.99
netmask 255.255.255.224
gateway 10.67.21.97
```

- Sibandang (11 host)

```
#A4
auto eth0
iface eth0 inet static
address 10.67.21.100
netmask 255.255.255.224
gateway 10.67.21.97
```

- Sebuku (186 host)

```
#A5
auto eth0
iface eth0 inet static
address 10.67.19.2
netmask 255.255.255.0
gateway 10.67.19.1
```

- Sebesi

```
#A5
auto eth0
iface eth0 inet static
address 10.67.19.3
netmask 255.255.255.0
gateway 10.67.19.1
```

- LAMPUNG

```
auto lo
iface lo inet loopback

#A6
auto eth0
iface eth0 inet static
address 10.67.21.182
netmask 255.255.255.252
gateway 10.67.21.181

#A5
auto eth1
iface eth1 inet static
address 10.67.19.1
netmask 255.255.255.0

```

- SUMATERA

```
auto lo
iface lo inet loopback

#A7
auto eth0
iface eth0 inet static
address 10.67.21.186
netmask 255.255.255.252
gateway 10.67.21.185

#A4
auto eth1
iface eth1 inet static
address 10.67.21.97
netmask 255.255.255.224

#A6
auto eth2
iface eth2 inet static
address 10.67.21.181
netmask 255.255.255.252
```

- Bajuin (511 host)

```
#A8
auto eth0
iface eth0 inet static
address 10.67.0.2
netmask 255.255.248.0
gateway 10.67.0.1
```

- Takisung (513 host)

```
#A8
auto eth0
iface eth0 inet static
address 10.67.0.3
netmask 255.255.248.0
gateway 10.67.0.1
```

- Batakan (1020 host)

```
#A8
auto eth0
iface eth0 inet static
address 10.67.0.4
netmask 255.255.248.0
gateway 10.67.0.1
```

- Angsana (15 host)

```
#A9
auto eth0
iface eth0 inet static
address 10.67.21.66
netmask 255.255.255.224
gateway 10.67.21.65
```

- KALIMANTAN-SELATAN

```
auto lo
iface lo inet loopback

#A10
auto eth0
iface eth0 inet static
address 10.67.21.190
netmask 255.255.255.252
gateway 10.67.21.189

#A8
auto eth1
iface eth1 inet static
address 10.67.0.1
netmask 255.255.248.0

#A9
auto eth2
iface eth2 inet static
address 10.67.21.65
netmask 255.255.255.224
```

- Lamaru (468 host)

```
#A11
auto eth0
iface eth0 inet static
address 10.67.16.2
netmask 255.255.254.0
gateway 10.67.16.1
```

- Bangkirai

```
#A11
auto eth0
iface eth0 inet static
address 10.67.16.3
netmask 255.255.254.0
gateway 10.67.16.1
```

- KALIMANTAN-TIMUR

```
auto lo
iface lo inet loopback

#A12
auto eth0
iface eth0 inet static
address 10.67.21.194
netmask 255.255.255.252
gateway 10.67.21.193

#A10
auto eth1
iface eth1 inet static
address 10.67.21.189
netmask 255.255.255.252

#A11
auto eth2
iface eth2 inet static
address 10.67.16.1
netmask 255.255.254.0
```

- Selimau (200 host)

```
#A13
auto eth0
iface eth0 inet static
address 10.67.18.2
netmask 255.255.255.0
gateway 10.67.18.1
```

- KALIMANTAN-UTARA

```
auto lo
iface lo inet loopback

#A14
auto eth0
iface eth0 inet static
address 10.67.21.198
netmask 255.255.255.252
gateway 10.67.21.197

#A12
auto eth1
iface eth1 inet static
address 10.67.21.193
netmask 255.255.255.252

#A13
auto eth2
iface eth2 inet static
address 10.67.18.1
netmask 255.255.255.0
```

- KALIMANTAN

```
auto lo
iface lo inet loopback

#A15
auto eth0
iface eth0 inet static
address 10.67.21.202
netmask 255.255.255.252
gateway 10.67.21.201

#A14
auto eth1
iface eth1 inet static
address 10.67.21.197
netmask 255.255.255.252
```

- Tobelo (511 host)

```
#A16
auto eth0
iface eth0 inet static
address 10.67.8.2
netmask 255.255.248.0
gateway 10.67.8.1
```

- Ternate (511 host)

```
#A16
#A16
auto eth0
iface eth0 inet static
address 10.67.8.3
netmask 255.255.248.0
gateway 10.67.8.1
```

- Morotai

```
#A16
auto eth0
iface eth0 inet static
address 10.67.8.4
netmask 255.255.248.0
gateway 10.67.8.1
```

- MALUKU-UTARA

```
auto lo
iface lo inet loopback

#A17
auto eth0
iface eth0 inet static
address 10.67.20.2
netmask 255.255.255.128
gateway 10.67.20.1

#A16
auto eth1
iface eth2 inet static
address 10.67.8.1
netmask 255.255.248.0
```

- PC-Gorontalo (32 host)

```
#A17
auto eth0
iface eth0 inet static
address 10.67.20.3
netmask 255.255.255.128
gateway 10.67.20.1
```

- PC-Marisa (30 host)

```
#A17
auto eth0
iface eth0 inet static
address 10.67.20.4
netmask 255.255.255.128
gateway 10.67.20.1
```

- Madini (30 host)

```
#A18
auto eth0
iface eth0 inet static
address 10.67.21.2
netmask 255.255.255.192
gateway 10.67.21.1
```

- Baru (30 host)

```
#A18
auto eth0
iface eth0 inet static
address 10.67.21.3
netmask 255.255.255.192
gateway 10.67.21.1
```

- BELAWA

```
auto lo
iface lo inet loopback

#A20
auto eth0
iface eth0 inet static
address 10.67.21.163
netmask 255.255.255.248
gateway 10.67.21.161

#A18
auto eth1
iface eth1 inet static
address 10.67.21.1
netmask 255.255.255.192
```

- Galesong

```
#A19
auto eth0
iface eth0 inet static
address 10.67.21.170
netmask 255.255.255.248
gateway 10.67.21.169
```

- Topejawa-Takalar

```
#A19
auto eth0
iface eth0 inet static
address 10.67.21.171
netmask 255.255.255.248
gateway 10.67.21.169
```

- MAKASAR

```
auto lo
iface lo inet loopback

#A20
auto eth0
iface eth0 inet static
address 10.67.21.162
netmask 255.255.255.248
gateway 10.67.21.161

#A19
auto eth1
iface eth1 inet static
address 10.67.21.169
netmask 255.255.255.248
```

- SULAWESI

```
auto lo
iface lo inet loopback

#A21
auto eth0
iface eth0 inet static
address 10.67.21.206
netmask 255.255.255.252
gateway 10.67.21.205

#A20
auto eth1
iface eth1 inet static
address 10.67.21.161
netmask 255.255.255.248

#A17
auto eth2
iface eth2 inet static
address 10.67.20.1
netmask 255.255.255.128
```

### Routing

### Testing

## CPT - CIDR

a

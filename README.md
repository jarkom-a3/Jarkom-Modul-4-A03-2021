# Jarkom-Modul-4-A03-2021

## Anggota

| Nama | NRP |
| :----: | :----: |
| Jessica Tasyanita | 05111940000043 |
| Daniel Sugianto | 05111940000075 |
| Ryan Fernaldy | 05111940000152 |

## Topologi

![image](https://user-images.githubusercontent.com/62937814/143009423-a7c5e6a1-76d6-4533-8a3d-5742cd626015.png)

## VLSM (Variable Length Subnet Masking)
  - Subnetting
![image](https://user-images.githubusercontent.com/62937814/143012499-109ecbd4-5e18-4406-8ec1-08bd424a2545.png)

Melalui pembagian subnet pada gambar diatas, kita dapat menghitung jumlah IP dan Netmask dari setiap subnet. Untuk jumlah IP dapat dilihat melalui jumlah host pada setiap subnet yang ada. contoh A1(chiper-water7) memiliki 700 host. Maka jumlah IP ditambah 1 dari jumlah host. Untuk subnet yang tersambung dengan server seperti pada A5(pucci-water7) memiliki jumlah host 1 yang berarti jumlah IP nya adalah 2. 

Untuk pembagian Netmask dapat dilihat melalui usable IP pada gambar berikut

![image](https://user-images.githubusercontent.com/62937814/143679015-cc61d98a-46d2-49d5-81a2-46f570132a3e.png)

Penentuan Netmask diambil dari Jumlah IP dari setiap subnet dan juga usable IP pada gambar diatas. contoh A1(Chiper-water7) memiliki jumlah IP 701, oleh karena itu netmask yang dipilih adalah /22 karena dapat mencover jumlah IP 701 tersebut. Begitu pula untuk subnet yang lainnya.

| Subnet  | Alias | Jumlah IP | Netmask |
| ------------- | ------------- | ------------- | ------------- |
| A1 | cipher-water7 | 701 | /22  |
| A2 | blueno-foosha  | 1001  | /22 |
| A3 | jipangu-pucci | 101 | /25  |
| A4 | pucci-calmbelt-courtyard | 2021 | /21  |
| A5 | pucci-water7 | 2 | /30  |
| A6 | water7-foosha | 2 | /30  |
| A7 | foosha-doriki | 2 | /30  |
| A8 | jabra-guanhao | 521 | /22  |
| A9 | foosha-guanhao | 2 | /30  |
| A10 | guanhao-maingate-alabasta | 502 | /23  |
| A11 | alabasta-jorge | 13 | /28  |
| A12 | oimo-enieslobby-seastone | 252 | /24  |
| A13 | seastone-elena | 721 | /22  |
| A14 | guanhao-oimo | 2 | /30  |
| A15 | oimo-fukurou | 2 | /30  |
|  |  | 5845 | /19  |

   - Tree

Untuk root atau puncak dari tree diambil dari prefix setiap kelompok ditambah dengan 0.0. dan untuk netmask nya diambil dari total netmask yang tercover.    Setiap turun, maka netmask akan dikurangi 1. Untuk penentuan IP berikutnya diambil dari IP saat ini, dan dilihat dari wildcard, yang tertera pada wildcard akan ditambah 1 lalu dibagi 2.

![image](https://user-images.githubusercontent.com/62937814/143012403-f2555e5c-fdc2-4b36-bdf3-2ed36b0c4491.png)

   - Pembagian IP
     Dari Tree akan mendapat pembagian IP sebagai berikut.
 
![image](https://user-images.githubusercontent.com/62937814/143023925-dae0a13d-4d99-4182-9b65-2fd8bba59034.png)


## CIDR (Classless Inter Domain Routing)

Menggabungkan subnet-subnet dalam topologi dimulai dari subnet yang terbawah seperti berikut.

![image](https://user-images.githubusercontent.com/62937814/143012930-1b408677-c986-482c-a713-7db662afe60d.png)
![image](https://user-images.githubusercontent.com/62937814/143013273-85d01ad4-9397-470b-9bc2-c84638ab5630.png)
![image](https://user-images.githubusercontent.com/62937814/143013595-a6a8d3a2-17d6-4600-addf-beb6460e25d5.png)
![image](https://user-images.githubusercontent.com/62937814/143013683-900380af-d5ad-4b29-a53d-223a7d7c3f9e.png)
![image](https://user-images.githubusercontent.com/62937814/143013945-45832870-8557-4c99-bb54-53d339f39223.png)
![image](https://user-images.githubusercontent.com/62937814/143014088-625d5e10-34d3-4c2f-902b-8c7a726aaa52.png)
![image](https://user-images.githubusercontent.com/62937814/143014256-27045a82-230d-495d-9d13-d15e08ea2e7f.png)
![image](https://user-images.githubusercontent.com/62937814/143014369-d76a9a48-ad98-45b8-810f-55edaa37f60c.png)

   - Tree
 
![image](https://user-images.githubusercontent.com/62937814/143014573-e8dd9f71-547c-4168-b9ce-d4edef8b42fc.png)

   - Pembagian IP
     Dari Tree akan mendapat pembagian IP sebagai berikut.
     
![image](https://user-images.githubusercontent.com/62937814/143024759-17f5f51a-4b1b-4a4c-a5a6-9a44a7d23152.png)

## CPT Menggunakan VLSM

### A2
- Atur IP pada interface FOOSHA (Fa 1/0) yang mengarah ke client BLUENO dengan 192.170.8.1 dan Subnet Mask 255.255.252.0
  ![image](https://user-images.githubusercontent.com/68326540/143527094-50621698-fd95-4a58-8879-64b2a175ba82.png)
- Atur IP pada client BLUENO dengan 192.170.8.2 dan Subnet Mask 255.255.252.0 serta Default Gateway ke FOOSHA (192.170.8.1)
  ![image](https://user-images.githubusercontent.com/68326540/143527132-d4369351-a3af-4277-85d0-583b8bcacdfa.png)

### A7
- Atur IP pada interface FOOSHA (Eth 1/1/0) yang mengarah ke client DORIKI dengan 192.170.27.161 dan Subnet Mask 255.255.255.252
  ![image](https://user-images.githubusercontent.com/68326540/143527169-8e094731-ed2d-49e1-8fa5-e094f26c15bd.png)
- Atur IP pada DORIKI dengan 192.170.27.162 dan Subnet Mask 255.255.255.252 serta Default Gateway ke FOOSHA (192.170.27.161)
  ![image](https://user-images.githubusercontent.com/68326540/143527206-1dca73e3-aa03-4b79-b238-7bfea7969b8a.png)

### A9
- Atur IP pada interface FOOSHA (Fa 1/1) yang mengarah ke GUANHAO dengan 192.170.27.153 dan Subnet Mask 255.255.255.252
  ![image](https://user-images.githubusercontent.com/68326540/143527282-3be1c4d1-c993-4476-9148-b65c88f526c6.png)
- Atur IP pada interface GUANHAO (Fa 0/0) yang mengarah ke FOOSHA dengan 192.170.27.154 dan Subnet Mask 255.255.255.252
  ![image](https://user-images.githubusercontent.com/68326540/143527316-c9cc0585-33e0-4b16-aec8-95606b975b8b.png)
- Tambahkan Default Routing pada GUANHAO ke FOOSHA
  ![image](https://user-images.githubusercontent.com/68326540/143527341-881a76b3-ebdd-4779-b1c6-7d48b7e01afe.png)

### A8
- Atur IP pada interface GUANHAO  (Fa 1/0) yang mengarah ke client JABRA dengan 192.170.16.1 dan Subnet Mask 255.255.252.0
  ![image](https://user-images.githubusercontent.com/68326540/143527440-1f12cba5-a15b-4482-b01d-ed462dc08654.png)
- Atur IP pada client JABRA dengan 192.170.16.2 dan Subnet Mask 255.255.252.0 serta Default Gateway ke GUANHAO(192.170.16.1)
  ![image](https://user-images.githubusercontent.com/68326540/143527447-32ef7946-66ae-43b9-94ef-416aa57fce48.png)
- Tambahkan Static Routing pada FOOSHA menuju network yang digunakan JABRA melalui Router GUANHAO  (192.170.27.154)
  ![image](https://user-images.githubusercontent.com/68326540/143527461-78bdced9-bf30-4b5f-8eb0-979e8ed56e4b.png)

### A10
- Atur IP pada interface GUANHAO  (Fa 1/1) yang mengarah ke client MAINGATE dengan 192.170.24.1 dan Subnet Mask 255.255.254.0
  ![image](https://user-images.githubusercontent.com/68326540/143527558-8a60b6ab-03f4-4d3c-a74b-b16d1baffcd7.png)
- Atur IP pada client MAINGATE dengan 192.170.24.2 dan Subnet Mask 255.255.254.0 serta Default Gateway ke GUANHAO(192.170.24.1)
  ![image](https://user-images.githubusercontent.com/68326540/143527586-d13d5c56-5759-4c3b-a3ea-f0b0ee07ee65.png)
- Tambahkan Static Routing pada FOOSHA menuju network yang digunakan MAINGATE melalui Router GUANHAO  (192.170.27.154)
  ![image](https://user-images.githubusercontent.com/68326540/143527592-330081e4-93dd-41a9-9995-a4eb627a4040.png)
- Atur IP pada interface ALABASTA (Fa 0/0) yang mengarah ke router GUANHAO dengan 192.170.24.3 dan Subnet Mask 255.255.254.0 karena interface ini berada di jaringan A10
 ![image](https://user-images.githubusercontent.com/68326540/143527658-ec793695-25a2-4dbe-b79c-95ed92d987c7.png)
- Tambahkan Default Routing pada ALABASTA ke GUANHAO
  ![image](https://user-images.githubusercontent.com/68326540/143527693-ade90f60-8a86-4338-a2e9-e651f73e2e89.png)

### A11
- Atur IP pada interface ALABASTA (Fa 0/1) yang mengarah ke client JORGE dengan 192.170.27.129 dan Subnet Mask 255.255.255.240
  ![image](https://user-images.githubusercontent.com/68326540/143527725-84d15d95-8673-4c84-87ae-9c5a33d1686f.png)
- Atur IP pada client JORGE dengan 192.170.27.130 dan Subnet Mask 255.255.255.240 serta Default Gateway ke ALABASTA(192.170.27.129)
  ![image](https://user-images.githubusercontent.com/68326540/143527765-17530170-e435-4d57-8772-7e1caa32ea30.png)
- Tambahkan static routing menuju jaringan yang digunakan client JORGE di Router GUANHAO melalui Router ALABASTA
  ![image](https://user-images.githubusercontent.com/68326540/143527779-b11a8be1-59fc-4769-a0d3-74e92622aceb.png)
- Tambahkan Static routing menuju jaringan yang digunakan client JORGE di Router FOOSHA melalui Router GUANHAO
  ![image](https://user-images.githubusercontent.com/68326540/143527788-0121125c-82ee-4d91-8a3c-f581b9368511.png)

### A14
- Atur IP pada interface GUANHAO (Fa 0/1) yang mengarah ke OIMO dengan 192.170.27.157 dan Subnet Mask 255.255.255.252
  ![image](https://user-images.githubusercontent.com/68326540/143527888-71e677f7-25cb-47ef-9208-a928835224d2.png)
- Atur IP pada interface OIMO(Fa 0/0) yang mengarah ke GUANHAO dengan 192.170.27.158 dan Subnet Mask 255.255.255.252
  ![image](https://user-images.githubusercontent.com/68326540/143527921-badae26a-f0f6-4e12-b2d7-244b05b270c0.png)
- Tambahkan Default Routing pada OIMO ke GUANHAO
  ![image](https://user-images.githubusercontent.com/68326540/143527952-6b9cb59e-4481-474d-8d68-3474bb0003bb.png)
- Tambahkan static routing dari foosha ke jaringan ini
  ![image](https://user-images.githubusercontent.com/68326540/143527981-d4d10ebc-6d58-477f-a681-4c03a1b8fbf3.png)

### A12
- Atur IP pada interface OIMO(Fa 0/1) yang mengarah ke client ENIESLOBBY dengan 192.170.26.1 dan Subnet Mask 255.255.255.0
  ![image](https://user-images.githubusercontent.com/68326540/143528043-f336bcc8-cea8-4f27-84ee-bf019948fbad.png)
- Atur IP pada client ENIESLOBBY dengan 192.170.26.2 dan Subnet Mask 255.255.255.0 serta Default Gateway ke OIMO(192.170.26.1)
  ![image](https://user-images.githubusercontent.com/68326540/143528062-5ac35e30-ed92-42aa-b8d2-7d4e13515332.png)
- Tambahkan static routing menuju jaringan yang digunakan client ENIESLOBBY di Router GUANHAO melalui Router OIMO
  ![image](https://user-images.githubusercontent.com/68326540/143528181-cde7f5d8-8e99-436b-a4d7-3e1fb4b906f3.png)
- Tambahkan static routing menuju jaringan yang digunakan client ENIESLOBBY di Router FOOSHA melalui Router GUANHAO
  ![image](https://user-images.githubusercontent.com/68326540/143528226-a1c1e349-5c55-40d8-bf2b-fdebdc7c6e82.png)
- Atur IP pada interface router SEASTONE(Fa 0/0) yang mengarah ke router OIMO dengan 192.170.26.3 dan Subnet Mask 255.255.255.0
  ![image](https://user-images.githubusercontent.com/68326540/143528518-886dd2f3-436a-4e52-a54c-442b4fcfa350.png)
- Tambahkan Default Routing pada SEASTONE ke OIMO
  ![image](https://user-images.githubusercontent.com/68326540/143528533-6dd91ae3-4deb-4547-af81-214c9efebda4.png)


### A15
- Atur IP pada interface OIMO(Fa 1/0) yang mengarah ke FUKOROU dengan 192.170.27.165 dan Subnet Mask 255.255.255.252
  ![image](https://user-images.githubusercontent.com/68326540/143528272-7798fef7-27bd-4df2-85e2-0abed91007f9.png)
- Atur IP pada client FUKOROU dengan 192.170.27.166 dan Subnet Mask 255.255.255.252 serta Default Gateway ke OIMO(192.170.27.165)
  ![image](https://user-images.githubusercontent.com/68326540/143528305-309ddf52-f5c5-4971-bd3e-8fa48f7892ac.png)
- Tambahkan static routing menuju jaringan yang digunakan FUKOROU di Router GUANHAO melalui Router OIMO
  ![image](https://user-images.githubusercontent.com/68326540/143528394-c91fbff0-8734-4049-a8f9-f2f8263c3549.png)
- Tambahkan static routing menuju jaringan yang digunakan FUKOROU di Router FOOSHA melalui Router GUANHAO
  ![image](https://user-images.githubusercontent.com/68326540/143528369-776377fa-915c-4255-ae80-14983e9d6b6e.png)

### A13
- Atur IP pada interface SEASTONE(Fa 0/1) yang mengarah ke client ELENA dengan 192.170.20.1 dan Subnet Mask 255.255.252.0
  ![image](https://user-images.githubusercontent.com/68326540/143528597-55d9f401-c210-4bc9-9097-d64e44911608.png)
- Atur IP pada client ELENA dengan 192.170.20.2 dan Subnet Mask 255.255.252.0 serta Default Gateway ke SEASTONE(192.170.20.1)
  ![image](https://user-images.githubusercontent.com/68326540/143528624-b235e7dc-4bf1-4201-b247-cc9934f2b1ae.png)
- Tambahkan static routing menuju jaringan yang digunakan client ELENA di Router OIMO melalui Router SEASTONE
  ![image](https://user-images.githubusercontent.com/68326540/143528643-4f548c59-d3b1-4607-a7c8-320bc31bce8d.png)
- Tambahkan static routing menuju jaringan yang digunakan client ELENA di Router GUANHAO melalui Router OIMO
  ![image](https://user-images.githubusercontent.com/68326540/143528671-841fb9c6-e57b-47a8-aa67-811e5ee5246f.png)
- Tambahkan static routing menuju jaringan yang digunakan client ELENA di Router FOOSHA melalui Router GUANHAO
  ![image](https://user-images.githubusercontent.com/68326540/143528690-7e563d7e-4323-40c7-8d77-2d9a3951c7e8.png)

### A6
- Atur IP pada interface FOOSHA (Fa 0/1) yang mengarah ke WATER7 dengan 192.170.27.149 dan Subnet Mask 255.255.255.252
  ![image](https://user-images.githubusercontent.com/68326540/143528736-93ac3657-e92a-4319-b128-3b630ad74cbb.png)
- Atur IP pada interface WATER7(Fa 0/0) yang mengarah ke FOOSHA dengan 192.170.27.150 dan Subnet Mask 255.255.255.252
  ![image](https://user-images.githubusercontent.com/68326540/143528755-803c5f70-1e14-4279-92bd-81f9372d0c0c.png)
- Tambahkan Default Routing pada WATER7 ke FOOSHA
  ![image](https://user-images.githubusercontent.com/68326540/143528775-c2a4a830-c6ec-4303-98c2-6a850e1dc91d.png)

### A1
- Atur IP pada interface WATER7(Fa 1/0) yang mengarah ke CIPHER dengan 192.170.12.1 dan Subnet Mask 255.255.252.0
  ![image](https://user-images.githubusercontent.com/68326540/143528832-04c3542b-920c-4cbd-ae31-6c154ba1451f.png)
- Atur IP pada client CIPHER dengan 192.170.12.2 dan Subnet Mask 255.255.252.0 serta Default Gateway ke WATER7(192.170.12.1)
  ![image](https://user-images.githubusercontent.com/68326540/143528843-50503092-2c3c-41a0-8e4b-fb4c5542b604.png)
- Tambahkan static routing menuju jaringan yang digunakan CIPHER di Router FOOSHA melalui Router WATER7
  ![image](https://user-images.githubusercontent.com/68326540/143528876-4f6b7615-4ead-436c-9c5d-eb12e25326bc.png)

### A5
- Atur IP pada interface WATER7(Fa 0/1) yang mengarah ke PUCCI dengan 192.170.27.145 dan Subnet Mask 255.255.255.252
  ![image](https://user-images.githubusercontent.com/68326540/143528923-866fead9-b2fc-4346-8aa7-19e36bb3a6a9.png)
- Atur IP pada interface PUCCI(Fa 0/0) yang mengarah ke WATER7dengan 192.170.27.146 dan Subnet Mask 255.255.255.252
  ![image](https://user-images.githubusercontent.com/68326540/143528937-faedbb8d-93f4-48f3-9601-41cf7a62675a.png)
- Tambahkan Default Routing pada PUCCI ke WATER7
  ![image](https://user-images.githubusercontent.com/68326540/143528963-56d0a630-bd4a-4476-8e51-6e6f5ab93657.png)
- Tambahkan static routing dari foosha ke jaringan ini
  ![image](https://user-images.githubusercontent.com/68326540/143528982-15984049-46e2-4216-a7b3-d59d0da8a991.png)

### A3
- Atur IP pada interface PUCCI(Fa 1/0) yang mengarah ke JIPANGU dengan 192.170.27.1 dan Subnet Mask 255.255.255.128
  ![image](https://user-images.githubusercontent.com/68326540/143529032-a97260d7-7240-48d6-9a56-225a42049b02.png)
- Atur IP pada client JIPANGU dengan 192.170.27.2 dan Subnet Mask 255.255.255.128 serta Default Gateway ke PUCCI(192.170.27.1)
  ![image](https://user-images.githubusercontent.com/68326540/143529044-3a902fff-2233-485e-b70d-eca4736d6da2.png)
- Tambahkan static routing menuju jaringan yang digunakan CIPHER di Router WATER7 melalui Router PUCCI
  ![image](https://user-images.githubusercontent.com/68326540/143529078-c773c2ed-7ebe-489a-b461-9afd4e251b8f.png)
- Tambahkan static routing menuju jaringan yang digunakan CIPHER di Router FOOSHA melalui Router WATER7
  ![image](https://user-images.githubusercontent.com/68326540/143529100-72e5476d-0db0-431c-b975-e58bd38e12b9.png)

### A4
- Atur IP pada interface PUCCI(Fa 1/0) yang mengarah ke jaringan A4 dengan 192.170.0.1 dan Subnet Mask 255.255.248.0
  ![image](https://user-images.githubusercontent.com/68326540/143529286-5181760d-8c8c-4d57-a449-461bf1070c03.png)
- Atur IP pada client CALMBET dengan 192.170.0.2 dan Subnet Mask 255.255.248.0 serta Default Gateway ke PUCCI(192.170.0.1)
  ![image](https://user-images.githubusercontent.com/68326540/143529351-57a54e71-7bde-4df0-a398-06719fed4c44.png)
- Atur IP pada client COURTYARD dengan 192.170.0.3 dan Subnet Mask 255.255.248.0 serta Default Gateway ke PUCCI(192.170.0.1)
  ![image](https://user-images.githubusercontent.com/68326540/143529389-fb68cbcd-324d-4722-84fd-7e8befd14522.png)
- Tambahkan static routing menuju jaringan A4 di Router WATER7 melalui Router PUCCI
  ![image](https://user-images.githubusercontent.com/68326540/143529415-6f0f0fb4-da7e-4684-a766-e3b5b897ebf1.png)
- Tambahkan static routing menuju jaringan A4 di Router FOOSHA melalui Router WATER7
  ![image](https://user-images.githubusercontent.com/68326540/143529425-9513e387-0bf5-4b7a-ab90-e1d9c7da7512.png)

### Hasil
![image](https://user-images.githubusercontent.com/68326540/143529668-db051cbf-0323-4482-9ced-c5f6c55a5503.png)

### Kendala
CPT sedikit kurang responsif (butuh beberapa kali pengiriman untuk mendapatkan success)

## GNS3 Menggunakan CIDR

### Koneksi Internet
Setiap node diminta agar dapat terhubung dengan internet, maka pada Foosha, jalankan command berikut.

```
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 192.170.0.0/15
```

![image](https://user-images.githubusercontent.com/58259649/143665931-9b742c0c-f62c-45a5-a772-1f6c33b99244.png)

Untuk setiap node selain Foosha, jalankan command berikut.

```
echo nameserver 192.168.122.1 > /etc/resolv.conf
```

Terakhir, mencoba ping ke google.com dari salah satu node.

![ping-pucci-google](https://user-images.githubusercontent.com/58259649/143665996-177173bc-1bd4-454b-b84c-6e2275a641c2.png)

### A1
### Cara Pengerjaan

Ubah network configuration pada CIPHER(eth0) yang mengarah ke WATER7(eth2) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143672243-7d46e53e-4c5c-44b8-9482-40d306007abf.png)

Ubah network configuration pada WATER7(eth2) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143672258-ef5c7e83-c01d-4e05-b162-59bc7ab1f9b2.png)

Tambahkan default routing pada WATER7 yang mengarah ke FOOSHA dengan command berikut.

```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.171.64.1
```

Tambahkan static routing menuju jaringan A1 di router FOOSHA melalui router WATER7

```
route add -net 192.171.32.0 netmask 255.255.252.0 gw 192.171.64.2
```

### Kendala

Tidak ada

### A2
### Cara Pengerjaan

Ubah network configuration pada BLUENO(eth0) yang mengarah ke FOOSHA(eth1) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143672973-3911910c-b684-462d-83c2-a03319a44df4.png)

Ubah network configuration pada FOOSHA(eth1) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143672986-3b2e4635-233f-4265-8548-7bda762ff447.png)

### Kendala

Tidak ada
### A3
### Cara Pengerjaan

Ubah network configuration pada PUCCI(eth1) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143673063-9e48a805-0bf8-4551-a205-df856791ecda.png)

Ubah network configuration pada JIPANGU(eth0) yang mengarah ke PUCCI(eth1) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143673094-8b154c8a-189e-460f-bc88-b4ac037dff51.png)

Tambahkan static routing menuju jaringan A3 di router WATER7 melalui router PUCCI

```
route add -net 192.171.8.0 netmask 255.255.255.128 gw 192.171.16.2
```

Tambahkan static routing menuju jaringan A3 di router FOOSHA melalui router WATER7

```
route add -net 192.171.8.0 netmask 255.255.255.128 gw 192.171.64.2
```

### Kendala

Tidak ada
### A4
### Cara Pengerjaan

Ubah network configuration pada PUCCI(eth2) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143673764-31454ae3-099d-40b5-acdc-61eaeddbf79a.png)

Ubah network configuration pada CAMBELT(eth0) dan COURTYARD(eth0) yang mengarah ke PUCCI(eth2) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143673821-70c3c03d-a2a0-49ab-88f5-03dbe67165ea.png)

![image](https://user-images.githubusercontent.com/58259649/143673830-b5c6d0f5-1576-43e5-a43e-948f5a375138.png)

Tambahkan static routing menuju jaringan A4 di router WATER7 melalui router PUCCI

```
route add -net 192.171.0.0 netmask 255.255.248.0 gw 192.171.16.2
```

Tambahkan static routing menuju jaringan A3 di router FOOSHA melalui router WATER7

```
route add -net 192.171.0.0 netmask 255.255.248.0 gw 192.171.64.2
```

### Kendala

Tidak ada
### A5
### Cara Pengerjaan

Ubah network configuration pada WATER7(eth1) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143674029-6ef5b50b-fd18-45c1-bd92-b3e31d6d963b.png)

Ubah network configuration pada PUCCI(eth0) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143674047-2e39b401-6f3a-4436-86a6-166bbac95939.png)


Tambahkan default routing pada PUCCI yang mengarah ke WATER7 dengan command berikut.

```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.171.16.1
```

Tambahkan static routing menuju jaringan A5 di router FOOSHA melalui router WATER7

```
route add -net 192.171.16.0 netmask 255.255.248.0 gw 192.171.64.2
```

### Kendala

Tidak ada
### A6
### Cara Pengerjaan

Ubah network configuration pada FOOSHA(eth2) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143674217-bb541d2d-7a9d-452d-a6b9-e9f01766fa7a.png)

Ubah network configuration pada WATER7(eth0) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143674224-cab9b8e5-5923-46da-8aab-fcb4dfa8899e.png)

### Kendala

Tidak ada
### A7
### Cara Pengerjaan

Ubah network configuration pada FOOSHA(eth3) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143674353-a109a386-661c-4675-82f0-ad6f103ea0f4.png)

Ubah network configuration pada DORIKI(eth0) yang mengarah ke FOOSHA(eth3) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143674292-84973ee3-b1c8-4b92-acef-e6898709d738.png)

### Kendala

Tidak ada
### A8
### Cara Pengerjaan

Ubah network configuration pada JABRA(eth0) yang mengarah ke GUANHAO(eth1) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143674535-4bcdafbc-90a3-4263-8b5b-70ffbfea4841.png)

Ubah network configuration pada GUANHAO(eth1) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143674563-bf65ff63-a2b5-4cb3-9ffa-85fe18056ca9.png)

Tambahkan static routing menuju jaringan A8 di router FOOSHA melalui router GUANHAO

```
route add -net 192.170.36.0 netmask 255.255.252.0 gw 192.170.64.2
```

### Kendala

Tidak ada
### A9
### Cara Pengerjaan

Ubah network configuration pada FOOSHA(eth4) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143674696-a487081f-43e5-4395-8e7f-53f1949847ab.png)

Ubah network configuration pada GUANHAO(eth0) yang mengarah ke FOOSHA(eth4) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143674748-56e812da-b1c8-4b76-becf-f1d37f3ba357.png)

Tambahkan default routing pada GUANHAO yang mengarah ke FOOSHA dengan command berikut.

```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.170.64.1
```

### Kendala

Tidak ada
### A10
### Cara Pengerjaan

Ubah network configuration pada MAINGATE(eth0) yang mengarah ke GUANHAO(eth2) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143675075-934b6134-0b6f-4f59-8bb6-3dfd2171e78d.png)

Ubah network configuration pada GUANHAO(eth2) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143675091-a07f8f36-571e-48bf-b62b-5cfc56a95bfc.png)

Tambahkan static routing menuju jaringan A10 di router FOOSHA melalui router GUANHAO

```
route add -net 192.170.32.0 netmask 255.255.254.0 gw 192.170.64.2
```

Ubah network configuration pada ALABASTA(eth0) yang mengarah ke GUANHAO(eth2) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143675167-b62b1bf2-8357-427f-9701-0c0b3dabbf27.png)

Tambahkan default routing pada ALABASTA yang mengarah ke GUANHAO dengan command berikut.

```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.170.32.1
```

### Kendala

Tidak ada
### A11
### Cara Pengerjaan

Ubah network configuration pada JORGE(eth0) yang mengarah ke ALABASTA(eth1) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143675390-5eacb8ec-f57a-4154-beab-6c8be9ffd10a.png)

Ubah network configuration pada ALABASTA(eth1) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143675400-e3f12154-f5f6-4218-bd04-d092c4d2a422.png)

Tambahkan static routing menuju jaringan A11 di router GUANHAO melalui router ALABASTA

```
route add -net 192.170.34.0 netmask 255.255.255.240 gw 192.170.32.3
```

Tambahkan static routing menuju jaringan A11 di router FOOSHA melalui router GUANHAO

```
route add -net 192.170.34.0 netmask 255.255.255.240 gw 192.170.64.2
```

### Kendala

Tidak ada
### A12
### Cara Pengerjaan

Ubah network configuration pada OIMO(eth1) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143679193-af2ed06f-6a46-45ee-abb3-6fa5a89298e9.png)

Ubah network configuration pada ENIESLOBBY(eth0) yang mengarah ke OIMO(eth1) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143679214-64858e2d-3454-481b-81d6-cb2bfbb5d056.png)

Tambahkan static routing menuju jaringan A12 di router GUANHAO melalui router OIMO

```
route add -net 192.170.4.0 netmask 255.255.255.0 gw 192.170.16.2
```

Tambahkan static routing menuju jaringan A12 di router FOOSHA melalui router GUANHAO

```
route add -net 192.170.4.0 netmask 255.255.255.0 gw 192.170.64.2
```

Ubah network configuration pada SEASTONE(eth0) yang mengarah ke OIMO(eth1) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143679595-ae1c351d-1a25-4b46-b063-038b3fe52055.png)


Tambahkan default routing pada SEASTONE yang mengarah ke OIMO dengan command berikut.

```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.170.4.1
```

### Kendala

Tidak ada
### A13
### Cara Pengerjaan

Ubah network configuration pada SEASTONE(eth1) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143679860-b1d665dc-e52a-4aa3-a7df-1ca37a1e3c3a.png)

Ubah network configuration pada ELENA(eth0) yang mengarah ke SEASTONE(eth1) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143679887-186ec5ab-e83c-4d7c-8ca9-a74ba11f49c3.png)

Tambahkan static routing menuju jaringan A13 di router OIMO melalui router SEASTONE

```
route add -net 192.170.0.0 netmask 255.255.252.0 gw 192.170.4.3
```

Tambahkan static routing menuju jaringan A13 di router GUANHAO melalui router OIMO

```
route add -net 192.170.0.0 netmask 255.255.252.0 gw 192.170.16.2
```

Tambahkan static routing menuju jaringan A13 di router FOOSHA melalui router GUANHAO

```
route add -net 192.170.0.0 netmask 255.255.252.0 gw 192.170.64.2
```

### Kendala

Tidak ada
### A14
### Cara Pengerjaan

Ubah network configuration pada GUANHAO(eth3) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143680312-d75ef2ed-d515-4cca-8625-8014f6aa808d.png)

Ubah network configuration pada OIMO(eth0) menjadi seperti berikut.

![image](https://user-images.githubusercontent.com/58259649/143680316-d9e8efd4-17bf-4488-a2d7-9c80b232af90.png)

Tambahkan default routing pada OIMO yang mengarah ke GUANHAO dengan command berikut.

```
route add -net 0.0.0.0 netmask 0.0.0.0 gw 192.170.16.1
```

Tambahkan static routing menuju jaringan A14 di router FOOSHA melalui router GUANHAO

```
route add -net 192.170.16.0 netmask 255.255.255.252 gw 192.170.64.2
```

### Kendala

Tidak ada
### A15
### Cara Pengerjaan
### Kendala

Tidak ada












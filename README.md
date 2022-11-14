# jarkom-modul-3-F14-2022
## Laporan Praktikum Modul 2 
**Nama  : Rivaldo Panangian Tambunan dan Ghazzi Buana Dewa**

**NRP   : 5025201134 dan 5025201074**

**Kelompok : F14**

***
## **Soal 1**
Loid bersama Franky berencana membuat peta tersebut dengan kriteria WISE sebagai DNS Server, Westalis sebagai DHCP Server, Berlint sebagai Proxy Server
Ostania

auto eth0

iface eth0 inet dhcp

auto eth1
iface eth1 inet static

	address 192.206.1.1
	
	netmask 255.255.255.0

auto eth2
iface eth2 inet static
	address 192.206.2.1
	netmask 255.255.255.0

auto eth3

iface eth3 inet static

	address 192.206.3.1
	
	netmask 255.255.255.0

WISE

auto eth0

iface eth0 inet static

	address 192.206.2.2
	
	netmask 255.255.255.0
	
	gateway 192.206.2.1
  
Berlint

auto eth0

iface eth0 inet static

 address 192.206.2.3
 
 netmask 255.255.255.0
 
 gateway 192.206.2.1
 
 Westalis
 
 auto eth0
iface eth0 inet static

	address 192.174.2.4
	
	netmask 255.255.255.0
	
	gateway 192.174.2.1

Eden

auto eth0
iface eth0 inet static

        address 192.174.3.2
	
        netmask 255.255.255.0
	
        gateway 192.174.3.1
        
NewstonCastle

auto eth0

iface eth0 inet static

        address 192.174.3.3
	
        netmask 255.255.255.0
	
          gateway 192.174.3.1
          
KemonoPark

auto eth0
iface eth0 inet static

        address 192.174.3.4
	
        netmask 255.255.255.0
	
        gateway 192.174.3.1
        
SSS

auto eth0

iface eth0 inet static
        address 192.174.1.2
	
        netmask 255.255.255.0
	
        gateway 192.174.1.1
        
Garden

auto eth0

iface eth0 inet static
        address 192.174.1.3
	
        netmask 255.255.255.0
	
        gateway 192.174.1.1

Wise DNS Server 
(scriptWise.sh)

apt-get update
apt-get install bind9 -y

Westalis DHCP Server
(scriptWestalis.sh)

apt-get update
apt-get install isc-dhcp-server -y


Berlint Proxy Server
(scriptBerlint.sh)

apt-get update
apt-get install squid -y

## **Soal 2**
Ostania sebagai DHCP Relay
Ostania DHCP Relay
(script.sh)

apt-get update
apt-get install isc-dhcp-relay -y

Kemudian edit file /etc/default/isc-dhcp-relay dengan menambahkan SERVER = "192.206.2.4" dan INTERFACES = "eth1 eth2 eth3"

service isc-dhcp-relay restart

![image](https://user-images.githubusercontent.com/71111983/201684707-1026af57-2e09-4fa1-aae6-cdf28982c5d5.png)


## **Soal 3**
Client yang melalui Switch1 mendapatkan range IP dari [prefix IP].1.50 - [prefix IP].1.88 dan [prefix IP].1.120 - [prefix IP].1.155

Konfigurasi Westalis

(tambahan di script.sh)

![image](https://user-images.githubusercontent.com/71111983/201686762-5ae08076-fa34-4ef0-8b42-7e0c04294c1e.png)


SSS

(scriptSSS.sh)

![image](https://user-images.githubusercontent.com/71111983/201686897-b835e762-6373-458d-8bd4-2dc020c3255d.png)

Garden

script(Garden.sh)

![image](https://user-images.githubusercontent.com/71111983/201687119-c4568226-9063-4063-87f6-84280e08751a.png)

## **Soal 4**
Client yang melalui Switch3 mendapatkan range IP dari [prefix IP].3.10 - [prefix IP].3.30 dan [prefix IP].3.60 - [prefix IP].3.85

Konfigurasi Westalis

(tambahan di scriptWestalis.sh)

![image](https://user-images.githubusercontent.com/71111983/201687444-7f633af9-2be8-4dd1-a28a-8572313493aa.png)

Eden

![image](https://user-images.githubusercontent.com/71111983/201687583-dcf2c0da-ea1e-4cb8-a056-0910abfea536.png)

NewstonCastle

![image](https://user-images.githubusercontent.com/71111983/201687719-8c058e97-0b49-4fff-a5ee-91431689c525.png)

Kemonopark

![image](https://user-images.githubusercontent.com/71111983/201687977-88806329-627a-4eff-a3b0-8bc8ca108b3c.png)

## **Soal 5**
Client mendapatkan DNS dari WISE dan client dapat terhubung dengan internet melalui DNS tersebut

![image](https://user-images.githubusercontent.com/71111983/201688187-efcf95ef-dd9d-4a4e-a614-1abc9e4fcf68.png)

SSS

![image](https://user-images.githubusercontent.com/71111983/201688419-3c79cf70-f1a6-4329-b91f-002f4afbf370.png)

Garden

![image](https://user-images.githubusercontent.com/71111983/201688588-7a704f0f-2321-4277-a4a6-664c40b8bbfd.png)

Newston Castle

![image](https://user-images.githubusercontent.com/71111983/201689652-c091ecc3-1310-4855-b1e1-1a33887fe369.png)

KemonoPark

![image](https://user-images.githubusercontent.com/71111983/201689787-59f476f8-9c79-4dba-830e-58833ba860cb.png)

## **Soal 6**

Lama waktu DHCP server meminjamkan alamat IP kepada Client yang melalui Switch1 selama 5 menit sedangkan pada client yang melalui Switch3 selama 10 menit. Dengan waktu maksimal yang dialokasikan untuk peminjaman alamat IP selama 115 menit.

## **Soal 7**

Loid dan Franky berencana menjadikan Eden sebagai server untuk pertukaran informasi dengan alamat IP yang tetap dengan IP [prefix IP].3.13

![image](https://user-images.githubusercontent.com/71111983/201690224-293f966b-eb53-41b6-88a4-bbde673dd5f5.png)


Proxy

## **Soal 1**
Client hanya dapat mengakses internet diluar (selain) hari & jam kerja (senin-jumat 08.00 - 17.00) dan hari libur (dapat mengakses 24 jam penuh)

![image](https://user-images.githubusercontent.com/71111983/201690623-e0e2a6d5-d7c3-4d1b-ab0d-22b14e43a368.png)

![image](https://user-images.githubusercontent.com/71111983/201691277-8bba9e8f-cf01-48df-927f-a0ad11ecf240.png)

![image](https://user-images.githubusercontent.com/71111983/201691336-94fd7326-a7d4-45ab-be7a-675430d4990d.png)

![image](https://user-images.githubusercontent.com/71111983/201691649-988f3aad-42c1-4306-90f9-0458710d4806.png)

![image](https://user-images.githubusercontent.com/71111983/201691518-446c8e8f-2dc7-4f07-9011-cb90a899f1ca.png)










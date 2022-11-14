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



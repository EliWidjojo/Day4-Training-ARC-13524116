# Day4-Training-ARC-13524116

##Konfigurasi Jaringan Packet Tracer 

### File  
File konfigurasi dapat ditemukan di repository ini.

### Topologi  
Jaringan terdiri dari:  
- 1 Router (College)
- 2 Switch (Class-A, Class-B) 
- 4 PC (Student-1, Student-2, Student-3, Student-4)

### Konfigurasi Router College
Current configuration : 1111 bytes
!
version 15.1
no service timestamps log datetime msec
no service timestamps debug datetime msec
service password-encryption
!
hostname College
!
!
!
enable secret 5 $1$mERr$9cTjUIEqNGurQiFU.ZeCi1
!
!
!
!
!
!
ip cef
ipv6 unicast-routing
!
no ipv6 cef
!
!
!
!
license udi pid CISCO1941/K9 sn FTX1524PMLM
!
!
!
!
!
!
!
!
!
!
!
spanning-tree mode pvst
!
!
!
!
!
!
interface GigabitEthernet0/0
 description Connection to Class-A
 ip address 128.107.20.1 255.255.255.0
 duplex auto
 speed auto
 ipv6 address FE80::3 link-local
 ipv6 address 2001:DB8:A::1/64
!
interface GigabitEthernet0/1
 description Connection to Class-B
 ip address 128.107.30.1 255.255.255.0
 duplex auto
 speed auto
 ipv6 address FE80::1 link-local
 ipv6 address 2001:DB8:B::1/64
!
interface Vlan1
 no ip address
 shutdown
!
ip classless
!
ip flow-export version 9
!
!
!
no cdp run
!
banner motd ^CUnauthorized access is strictly prohibited!!!^C
!
!
!
!
line con 0
 password 7 0822455D0A16
 login
!
line aux 0
 password 7 0822455D0A16
 login
!
line vty 0 4
 password 7 0822455D0A16
 login
line vty 5 15
 password 7 0822455D0A16
 login
!
!
!
end

### Konfigurasi Switch Class-B
Current configuration : 1549 bytes
!
version 15.0
no service timestamps log datetime msec
no service timestamps debug datetime msec
service password-encryption
!
hostname Class-B
!
!
enable secret 5 $1$mERr$9cTjUIEqNGurQiFU.ZeCi1
!
!
!
!
!
!
spanning-tree mode pvst
spanning-tree extend system-id
!
interface FastEthernet0/1
 description Connected to Student-3
 switchport mode trunk
!
interface FastEthernet0/2
 description Connected to Student-4
 switchport mode trunk
!
interface FastEthernet0/3
!
interface FastEthernet0/4
!
interface FastEthernet0/5
!
interface FastEthernet0/6
!
interface FastEthernet0/7
!
interface FastEthernet0/8
!
interface FastEthernet0/9
!
interface FastEthernet0/10
!
interface FastEthernet0/11
!
interface FastEthernet0/12
!
interface FastEthernet0/13
!
interface FastEthernet0/14
!
interface FastEthernet0/15
!
interface FastEthernet0/16
!
interface FastEthernet0/17
!
interface FastEthernet0/18
!
interface FastEthernet0/19
!
interface FastEthernet0/20
!
interface FastEthernet0/21
!
interface FastEthernet0/22
!
interface FastEthernet0/23
!
interface FastEthernet0/24
 switchport mode trunk
!
interface GigabitEthernet0/1
 description Uplink to College Router
!
interface GigabitEthernet0/2
!
interface Vlan1
 description Management Interface for Class-B
 ip address 128.107.30.15 255.255.255.0
!
ip default-gateway 128.107.30.1
!
banner motd ^CUnauthorized access is strictly prohibited!!!^C
!
!
!
!
!
line con 0
 password 7 0822455D0A16
 login
!
line vty 0 4
 password 7 0822455D0A16
 login
line vty 5 15
 password 7 0822455D0A16
 login
!
!
!
!
end

### Konsfigurasi PC Student-1
IPv4
- IPv4 Address: 128.107.20.25  
- Subnet Mask: 255.255.255.0  
- Default Gateway: 128.107.20.1
- DNS Server: 0.0.0.0

IPv6
- IPv6 Address: 2001:DB8:A::25
- Link Local Address: FE80::2E0:F7FF:FED8:60A
- Default Gateway: FE80::3

### Konsfigurasi PC Student-2
IPv4
- IPv4 Address: 128.107.20.30  
- Subnet Mask: 255.255.255.0  
- Default Gateway: 128.107.20.1
- DNS Server: 0.0.0.0

IPv6
- IPv6 Address: 2001:DB8:A::30
- Link Local Address: FE80::2E0:F7FF:FED8:60A
- Default Gateway: FE80::3

### Konsfigurasi PC Student-3
IPv4
- IPv4 Address: 128.107.30.25  
- Subnet Mask: 255.255.255.0  
- Default Gateway: 128.107.30.1
- DNS Server: 0.0.0.0

IPv6
- IPv6 Address: 2001:DB8:B::25
- Link Local Address: FE80::2E0:F7FF:FED8:60A
- Default Gateway: FE80::1

### Konsfigurasi PC Student-4
IPv4
- IPv4 Address: 128.107.30.30
- Subnet Mask: 255.255.255.0  
- Default Gateway: 128.107.30.1
- DNS Server: 0.0.0.0

IPv6
- IPv6 Address: 2001:DB8:B::30
- Link Local Address: FE80::2E0:F7FF:FED8:60A
- Default Gateway: FE80::1

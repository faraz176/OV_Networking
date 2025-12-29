**Legend:**



R0 = \[Router 0] 

R1 = \[Router 1]

PC0 = \[Personal Computer 0]

PC1 = \[Personal Computer 1]

PC2 = \[Personal Computer 2]



#

# OV Networking Plan:



**Goal:**



We are building a boss/employee based topology. The switches are used for the expansion of the employee base. while the managers/bosses stay in isolated part of the network. Our company is called OV. We are small, ambitious startup. With 2 employees with Dadima as the Boss 



**What does OV do?**



Well its actually very simple. We take videos of the clients spot and build a dataset and train a custom video model. The reason for the computers, is that our employees still need to clean and format the data to input into lamda labs for cloud training. This job requires consistent, fast communication between the members of the company along with expansion Which explains why we decided to go with industrial cisco hardware. 



**Who have we hired to build the network stack?**

Well we hired Shuaib, the same employee for our company as well. He is cheap labor. That

boy will do anything. The hustler. Lets take advantage of him. 









### Shuaib's Network Configurations V1:



**Interface Map:**

PC0 -> SW0 [f0/1]
PC1 -> SW1 [f0/1]
SW0 [f0/2] -> SW1 [f0/2]
SW0 [f0/3] -> R0 [g0/0]
SW1 [f0/3] -> R0 [g0/1]
R0 [g0/2] -> R1 [g0/0]
R1 [g0/1] -> SW2 [f0/1]
SW2 [f0/2] -> PC2 





**Legend:**



R0 = \[Router 0]

R1 = \[Router 1]

PC0 = \[Personal Computer 0]

PC1 = \[Personal Computer 1]

PC2 = \[Personal Computer 2]





\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*



**IP Configurations:**





\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*



192.168.1.0 /30 



192.168.1.0 (Network) 



192.168.1.1 (First Host)  



192.168.1.2 (Second Host) -------------- > Unallocated IP Space



192.168.1.3 (Broadcast) 



--------------------------------- R0 \& PC0 



192.168.1.4 /30 (Network) 



192.168.1.5 (First Host) Personal Computer 0 



192.168.1.6 (Second Host) Router 0 



192.168.1.7 (Broadcast) 



----------------------------------



192.168.1.8 /30 (Network) 



192.168.1.9 (First Host) Router 1 



192.168.1.10 (Second Host) 



192.168.1.11 (Broadcast) 



----------------------------------- R1 \& PC2



192.168.1.12 /30 (Network) 



192.168.1.13  (First Host) Personal Computer 2	



192.168.1.14  (Second Host) Router 1 



192.168.1.15 (Broadcast) 



------------------------------------ R0  



192.168.1.16 /30 (Network) 



192.168.1.17 (First Host) Router 0  



192.168.1.18 (Second Host) 



192.168.1.19 (Broadcast) 





-------------------------------------



192.168.1.20 (Network) 



192.168.1.21 (First Host) 



192.168.1.22 (Second Host) ------------- > Unallocated IP Space



192.168.1.23 (Broadcast) 



-------------------------------------



192.168.1.24 (Network) 



192.168.1.25 (First Host) 



192.168.1.26 (Second Host) ------------- > Unallocated IP Space 



192.168.1.27 (Broadcast)



------------------------------------



192.168.1.28 (Network)



192.168.1.29 (First Host) 



192.168.1.30 (Second Host) ------------ > Unallocated IP Space 



192.168.1.31 (Broadcast) 



------------------------------------- R0 \& PC1



192.168.1.32 (Network)



192.168.1.33 (First Host) Personal Computer 1 



192.168.1.34 (Second Host) Router 0 



192.168.1.35 (Broadcast)



\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*



**STATIC ROUTES SYNTAX**





ip route \[Destination] \[Subnet Mask] \[Next Hop] 





Router 0:



ip route 192.168.1.12 255.255.255.252 192.168.1.22





Router 1: 



ip route 192.168.1.4 255.255.255.252 192.168.1.21
ip route 192.168.1.32 255.255.255.252 192.168.1.21



\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*



**Troubleshooting connectivity between \[Personal Computer 0 --- Router 0] (ERR 1)**

Subnets need to match between routers 


\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*


**Troubleshooting connectivity between \[Personal Computer 0 -- Personal Computer 2] (ERR 3)**

Wrong ip 


**Solution to (ERR 1)**



I began working the tree of cause and effect for networking beginning with the how?
how will the router be able to reach the gateway. I looked at the subnet of the PC and the router interface and found that there was a mismatched subnet. By itself, the PC doesn't have routing capabilities. Meaning, its unable to send packets outside of its subnet so it requires a router to forward packets outside of its subnet. Knowing this i correctly fixed the subnet mismatch of the router and the pc after which the connectivity between the gateway and pc still failed so we move further down the line. 





**Router or Switch configuration isolation:**



Test Attempt:



10.0.0.0/24



10.0.0.1 PC



10.0.0.2 Router





**Whether isolation worked or failed:** 



I successfully isolated the issue to be the switch after setting up a basic connection 

between the pc and the router using similar settings to the main topology and achieving connectivity I have identified that the issue is with the switch configuration. After checking these basic things:





**Switch Diagnostic:**

SW0:



VLAN 20

-f0/1 (access) 

-f0/3 (not in vlan and or access) <-- Root issue in order for packets to be forwarded to the router when a switch is placing a vlan on a host or networking device. The interface connecting the switch to the router must also be placed in the vlan 





\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*\*



**Potential Errors:**



-IP address space is too tight preventing expansion

-Security, redundancy, and reliability concerns unaddressed 

-Better organization of IP address space for predictability 



**Configurations used:**

SW0:

Current configuration : 1206 bytes
!
version 15.0
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname Switch
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
 switchport access vlan 20
 switchport mode access
!
interface FastEthernet0/2
 switchport mode access
!
interface FastEthernet0/3
 switchport access vlan 20
 switchport mode access
!


SW1:

Current configuration : 1250 bytes
!
version 15.0
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname Switch
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
 switchport access vlan 10
 switchport mode access
!
interface FastEthernet0/2
 switchport mode access
!
interface FastEthernet0/3
 switchport access vlan 10
 switchport mode access
!

R0:

Current configuration : 840 bytes
!
version 15.1
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname Router
!
!
!
!
!
!
!
!
ip cef
no ipv6 cef
!
!
!
!
license udi pid CISCO2911/K9 sn FTX15240HDZ-
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
 ip address 192.168.1.6 255.255.255.252
 duplex auto
 speed auto
!
interface GigabitEthernet0/1
 ip address 192.168.1.34 255.255.255.252
 duplex auto
 speed auto
!
interface GigabitEthernet0/2
 ip address 192.168.1.21 255.255.255.252
 duplex auto
 speed auto
!
interface Vlan1
 no ip address
 shutdown
!
ip classless
ip route 192.168.1.12 255.255.255.252 192.168.1.14 
ip route 192.168.1.12 255.255.255.252 192.168.1.22 
!
ip flow-export version 9
!
!
!
!
!
!
!
line con 0
!
line aux 0
!
line vty 0 4
 login
!
!
!
end

R1:

Current configuration : 824 bytes
!
version 15.1
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname Router
!
!
!
!
!
!
!
!
ip cef
no ipv6 cef
!
!
!
!
license udi pid CISCO2911/K9 sn FTX15240LIC-
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
 ip address 192.168.1.22 255.255.255.252
 duplex auto
 speed auto
!
interface GigabitEthernet0/1
 ip address 192.168.1.14 255.255.255.252
 duplex auto
 speed auto
!
interface GigabitEthernet0/2
 no ip address
 duplex auto
 speed auto
 shutdown
!
interface Vlan1
 no ip address
 shutdown
!
ip classless
ip route 192.168.1.4 255.255.255.252 192.168.1.21 
ip route 192.168.1.32 255.255.255.252 192.168.1.21 
!
ip flow-export version 9
!
!
!
!
!
!
!
line con 0
!
line aux 0
!
line vty 0 4
 login
!
!
!
end


SW2:

Building configuration...

Current configuration : 1182 bytes
!
version 15.0
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname Switch
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
 switchport access vlan 30
 switchport mode access
!
interface FastEthernet0/2
 switchport access vlan 30
 switchport mode access
!



























&nbsp;



















## **PURDUE MODEL**
It is a hierarchical framework developed in the 1990s by Purdue University other name that it is called is the Purdue Enterprise Reference Architecture.Its main objective is to organize and structure the Industrial Control System (ICS) and its interactions with Enterprise Networks dividing on 6 levels.

Level 0: Physical - Devices like sensors and actuators that interact directly with the physical environmen.

Level 1: Inteligent Devices - PLCs and RTUs that process data from level 0 and execute controls orders. 

Level 2: Local supervision - HMIs and SCADA that allow operators to monitor and control  processes in real time.

Level 3: Control and management at the site level - Systems like historians  and MES for planning and operative analysis. 

Level 3.5: Demilitarized zone (DMZ) - Buffer between OT and IT that filters and regulates traffic bewtween these zones. 

Level 4: Bussines Systems - ERP, CRM and other Bussines logistic system.

Level 5: Bussines Network - General functions of IT like Email and Storage.

## **INFORMATION TECHNOLOGY**
 Is the use of computers, storage, networking, and other physical devices, infrastructure, and processes to create, process, store, secure, and exchange all forms of electronic data.

## **OPERATION TECHNOLOGY**
It is the set of hardware and software that monitors and controls physical devices, processes and infrastructure within an organization.OT systems are essential in critical sectors such as manufacturing, oil and gas, utilities and healthcare, where the correct functioning of physical processes is essential for continuous and safe operation

## **DEMILITARIZED ZONE**
It is a an area or network that acts as an isolated space between two networks, usually between an organization's internal network and an untrusted external network.

## **IP CONFIGURATION**

##### Router_IT 
	interface g0/0
	ip address 192.168.10.1 255.255.255.0
	no shutdown
	
	interface g0/1
	ip address 10.0.0.1 255.255.255.252
	no shutdown
	
	ip route 192.168.20.0 255.255.255.0 10.0.0.2
	ip route 192.168.30.0 255.255.255.0 10.0.0.2

##### Router DMZ1-Firewall simulation 
	`interface g0/0`
	`ip address 10.0.0.2 255.255.255.252`
	`no shutdown`
	
	`interface g0/1`
	`ip address 10.0.0.5 255.255.255.252`
	`no shutdown`
	
	`interface g0/2`
	`ip address 192.168.20.0 255.255.255.252`
	`no shutdown`
	
	`ip route 192.168.10.0 255.255.255.0 10.0.0.1`
	`ip route 192.168.20.0 255.255.255.0 10.0.0.6`
	`ip route 192.168.30.0 255.255.255.0 10.0.0.6`

##### Router DMZ2-Firewall simulation 
	interface g0/0
	ip address 10.0.0.6 255.255.255.252
	no shutdown
	
	interface g0/1
	ip address 10.0.0.9 255.255.255.252
	no shutdown
	
	ip route 192.168.10.0 255.255.255.0 10.0.0.5
	ip route 192.168.20.0 255.255.255.0 10.0.0.5
	ip route 192.168.30.0 255.255.255.0 10.0.0.10

##### Router_OT
	interface g0/0
	ip address 10.0.0.10 255.255.255.252
	no shutdown
	
	interface g0/1
	ip address 192.168.30.1 255.255.255.0
	no shutdown
	
	ip route 192.168.10.0 255.255.255.0 10.0.0.9
	ip route 192.168.20.0 255.255.255.0 10.0.0.9

## VLANS

| VLANS   | AREA  |
| ------- | ----- |
| VLAN 10 | IT    |
| VLAN 20 | DMZ   |
| VLAN 30 | HMI   |
| VLAN 40 | SCADA |

## DESIGN JUSTIFICATION 
This project was developed with this specific design to serve as a demonstration of a secure Industrial Environment. Typically, network engineers employ different architectures that often overlook area-specific security, relying solely on VLANs or basic routing for segmentation. However, these methods are insufficient for advancing cybersecurity. This project implements a more robust approach to bridge that gap.
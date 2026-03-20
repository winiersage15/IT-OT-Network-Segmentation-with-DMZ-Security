## **INTRODUCTION**
This project implements international cybersecurity standards used for protecting industrial control system (ICS). These standards provide guidelines for network segmentation,access control and protection of operational technology environments. 
The standars that it was on this project were: 

## **PRUDEL ENTERPRISE REFERENCE ARCHITECTURE**
The network architecture that was implemented in this project is based on Prudel Enterprise Reference Architecture model,Wich isolate enterprise IT system from operation techcology (OT) network environments using intermediate security zones such as the industrial DMZ implementing a Jump Server.

| Purdue Level | Implementación    |
| ------------ | ----------------- |
| Level 4      | IT Network        |
| Level 3.5    | DMZ (Jump Server) |
| Level 2      | OT Network        |

## **ISA/IEC 62443**

The implemented architecture use the zone and conducted model defined  in ISA/IEC 62443.The IT network, DMZ network and OT network are treated as separete security zones connected through controlled conduits enforced by firewalls. 

| Zona     | Red          |
| -------- | ------------ |
| IT Zone  | 192.168.10.0 |
| DMZ Zone | 192.168.20.0 |
| OT Zone  | 192.168.30.0 |
## **CISA**

The architecture also reflects recommendations from CISA for protecting industrial control systems, including network segmentation, restricted access to OT environments, and the use of a DMZ jump server for remote access.

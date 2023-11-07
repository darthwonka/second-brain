# Zywall 110

Created: 2023-02-07 18:22:03 -0700

Modified: 2023-02-08 11:32:23 -0700

---

| Internal IP    | 10.0.0.1           |                      |
|----------------|--------------------|-----------------------|
| Model          | Zywall 110         |                      |
| Serial Number  | S142L31030304      |                      |
| Management URL | <https:/10.0.0.1> |                      |
| Login          | Admin              | Password is in Keeper |
|               |                   |                      |

![Infrastructure-Network-Firewall-Zywall-110-image1](999-Archive/StudioCompletiva/attachment/Infrastructure-Network-Firewall-Zywall-110-image1.png)

![Infrastructure-Network-Firewall-Zywall-110-image2](999-Archive/StudioCompletiva/attachment/Infrastructure-Network-Firewall-Zywall-110-image2.png)

WAN

| Wan1     | Internet Gateway      | 0.0.0.0        | Does not have IP address, this is done through the PPP interface underneath                           |
|----------|-------------|----------------|-----------------------------------|
| Wan1-ppp | Actual ISP connection | 65.103.124.150 | Authenticates with Century link with PPP and is given IP Address by Century Link DHCP - though static |
|         |                      |               |                                                                                                      |

LAN

| Lan1 | Internal Network | 10.0.0.1 | DHCP, DNS functions have been moved to STUDIOSRV2 |
|---------|---------------|---------|----------------------------------------|
|     |                 |         |                                                  |

Firewall Rules

Firewall Rules should rarely need to be changed. But if you need to, you will need to be sure that the Machine/IP is defined in an object or as part of an object group and the services involved are also defined.

![Infrastructure-Network-Firewall-Zywall-110-image3](999-Archive/StudioCompletiva/attachment/Infrastructure-Network-Firewall-Zywall-110-image3.png)

Machine/GEO/IP Object Definitions

To Add/Change/Modify Machine locations, groups, etc, go to Object|Address/GEO IP


![Infrastructure-Network-Firewall-Zywall-110-image4](999-Archive/StudioCompletiva/attachment/Infrastructure-Network-Firewall-Zywall-110-image4.png)

To Add/Change/Modify Service Objects, go to OBJECT|Service

![Infrastructure-Network-Firewall-Zywall-110-image5](999-Archive/StudioCompletiva/attachment/Infrastructure-Network-Firewall-Zywall-110-image5.png)

Most are pre-defined for convenience, but many were added and grouped for specific applications like newforma, Wireguard, etc.

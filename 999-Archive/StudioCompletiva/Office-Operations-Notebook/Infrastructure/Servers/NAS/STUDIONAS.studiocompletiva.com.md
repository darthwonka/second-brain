# STUDIONAS.studiocompletiva.com

Created: 2023-02-08 10:52:07 -0700

Modified: 2023-02-13 17:12:48 -0700

---

10.0.0.250

Synology

| Serial #      | 2090ODN012100                                                               |
|--------------------|----------------------------------------------------|
| Model          | DS3617xs                                                                    |
| Management URL | <https://10.0.0.250:5001/> or <https://studionas.studiocompletiva.com:5001> |
| Admin Login    | Nasadmin                                                                    |
| SSH Port       | 1022                                                                        |
| SSH Command    | ssh -p 1022 nasadmin@10.0.0.250                                             |

Services

| VPN    | Application | Native Application    | Through Management URL      |
|--------|--------------|-----------------------|-----------------------------|
| VPN    | Wireguard    | Docker                | <http://10.0.0.250:51821/>  |
| Docker | Portainer    | Docker                | <http://10.0.0.250:9000>    |
| Docker | mkdocs       | Docker                | <http://10.0.0.250:8000>    |
| Backup | Idrive       | 3rd Party Application | <https://10.0.0.250/IDrive> |
| DNS    | DNS Server   | Native Application    | Through Management URL      |
| Shares | File Station | Native Application    | Through Management URL      |

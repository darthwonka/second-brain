

Created: 2023-02-08 17:16:06 -0700
Modified: 2023-05-29 21:28:38 -0600

---
![Howto-VPN-WireGuard-Client-Configuration-image1](999-Archive/StudioCompletiva/attachment/Howto-VPN-WireGuard-Client-Configuration-image1.png)

# Install and Configure the client!

1. Request a configuration file from your systems administrator
2. Download the configuration file to the system you will be connecting to the vpn
3. Download and install Wireguard client for your Operating System <https://www.wireguard.com/install/>
4. Run the installer and open Wireguard
5. Click on Add Tunnel (or Import Tunnel in the display window button #1)

![Howto-VPN-WireGuard-Client-Configuration-image2](999-Archive/StudioCompletiva/attachment/Howto-VPN-WireGuard-Client-Configuration-image2.png)

6. Locate the config file you downloaded in step #2 using the select file dialog box presented and press Open

![Howto-VPN-WireGuard-Client-Configuration-image3](999-Archive/StudioCompletiva/attachment/Howto-VPN-WireGuard-Client-Configuration-image3.png)

7. Start Wireguard by clicking on Activate in the right pane under the configuration display

![Howto-VPN-WireGuard-Client-Configuration-image4](999-Archive/StudioCompletiva/attachment/Howto-VPN-WireGuard-Client-Configuration-image4.png)

You should now have full access to the NAS and all internal network resources!

Please report any issues to [support@studiocompletiva.com](mailto:support@studiocompletiva.com)>

Remove Configuration and Start Over

NOTE: If you need to start over with a new configuration file,

1. Disconnect from the Wireguard connection

![Howto-VPN-WireGuard-Client-Configuration-image5](999-Archive/StudioCompletiva/attachment/Howto-VPN-WireGuard-Client-Configuration-image5.png)

2. Remove the old tunnel

![Howto-VPN-WireGuard-Client-Configuration-image6](999-Archive/StudioCompletiva/attachment/Howto-VPN-WireGuard-Client-Configuration-image6.png)

3. Proceed to **STEP 5**n the instructions above!

>[!NOTE] If the old conf file is in the same place, Windows may rename the file using special characters. Watchguard does not like that. Delete the old conf and rename the new file.

Example: wireguard_user(1).conf should be renamed to wireguard_user.conf

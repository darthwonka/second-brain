# OpenVPN

Created: 2023-02-09 15:26:32 -0700
Modified: 2023-02-10 14:57:22 -0700

---

![Howto-VPN-OpenVPN-image1](999-Archive/StudioCompletiva/attachment/Howto-VPN-OpenVPN-image1.png)

# INSTALL INSTRUCTIONS

1. Download the VPN Connect Client directly from Openvpn.net here: <https://openvpn.net/vpn-client/>
2. Install on the computer you will be connecting to the Studio Completiva network
3. Download this zip file to the same machine
4. Remove or rename the old zip file and extracted folder to avoid conflicts and confusion.
5. Unzip the file by right-clicking on the file and selecting Extract -- or by using the highly recommended [7-Zip](https://www.7-zip.org/) program.
6. Run **OpenVPN Connect** on your computer. If you have no other profiles active, the IMPORT PROFILE wizard will start automatically.
7. Click on the File Tab
8. Drag and drop the **StudioCompletiva.ovp**n file into the square area or click BROWSE to navigate to the file extracted from the zip file above.
9. Enter your Username in the field underneath the Server Hostname

		a.  Your username is in the following format : <DOMAIN><USERNAME>

For example: STUDIOCmichael.belanger

10. Check **Save Password**
11. Enter your Studio Completiva account Windows/Email password
12. Click CONNECT

![Howto-VPN-OpenVPN-image2](999-Archive/StudioCompletiva/attachment/Howto-VPN-OpenVPN-image2.png)

12. In the **Missing external certificate** window, check **Don't show again for this profile**
13. Click **CONTINUE**

![Howto-VPN-OpenVPN-image3](999-Archive/StudioCompletiva/attachment/Howto-VPN-OpenVPN-image3.png)

You should now be connected to the VPN

![Howto-VPN-OpenVPN-image4](999-Archive/StudioCompletiva/attachment/Howto-VPN-OpenVPN-image4.png)

# REMOVE OLD CONFIG FILE

To remove the old profile in favor of the updated profile, follow these instructions

1. Start OpenVPN Connect client
2. Disconnect, if you are connected, by using the toggle

![Howto-VPN-OpenVPN-image5](999-Archive/StudioCompletiva/attachment/Howto-VPN-OpenVPN-image5.png)

3. Edit the current profile by clicking on the pencil icon to the right of the profile

![Howto-VPN-OpenVPN-image6](999-Archive/StudioCompletiva/attachment/Howto-VPN-OpenVPN-image6.png)

4. Take a screenshot or write down your username, if you need it.
5. On the bottom left of the window, click on **DELETE PROFILE**

![Howto-VPN-OpenVPN-image7](999-Archive/StudioCompletiva/attachment/Howto-VPN-OpenVPN-image7.png)

6. Confirm in the pop-up that you want to remove the profile.
7. Proceed to STEP 6 in the instructions above!

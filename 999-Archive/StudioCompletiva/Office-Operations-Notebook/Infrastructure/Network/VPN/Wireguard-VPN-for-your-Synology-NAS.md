# Wireguard VPN for your Synology NAS

Created: 2023-02-08 14:36:24 -0700
Modified: 2023-02-08 21:36:36 -0700

---

Clipped from: <https://www.blackvoid.club/wireguard-vpn-for-your-synology-nas/>

![Infrastructure-Network-VPN-Wireguard-VPN-for-your-Synology-NAS-image1](999-Archive/StudioCompletiva/attachment/Infrastructure-Network-VPN-Wireguard-VPN-for-your-Synology-NAS-image1.png)
![Infrastructure-Network-VPN-Wireguard-VPN-for-your-Synology-NAS-image1]\(/attachment/Infrastructure-Network-VPN-Wireguard-VPN-for-your-Synology-NAS-image1.png)


This article is the **second** one out of the **two** Wireguard ones. This article is about running your Wireguard VPN server on your Synology NAS! For information on how to build an SPK package in order to give your NAS Wireguard support, use the article titled **[Wireguard SPK for your Synology NAS](https://www.blackvoid.club/wireguard-spk-for-your-synology-nas/).**

Following on the **[previous Wireguard article](https://www.blackvoid.club/wireguard-spk-for-your-synology-nas/) on how to give your Synology NAS support for this protocol, let's see now how you can actually configure your NAS to be an incoming Wireguard VPN server.**

This means that you will be able to use the Wireguard server as your incoming point back to your LAN when you are out and about. With the use of Wireguard clients for any device out there (desktop, mobile, tablet, etc), you will have a way to get back into your local network, apps, documents, or services, safely and securely.

# Prerequisites
For this to work you will need some prerequisites:

- You will need to open an incoming UDP port
- Have Docker running on your NAS
- Have some skill in running containers (not mandatory but it would help)


**NOTE**: Keep in mind that if you will need to connect back to your LAN from any current location (or network that you are on), that network **will need to allow access to the Wireguard port over the UDP connection**. If this is not something that is allowed, you will not be able to connect successfully.

For this setup, I have decided to use a Wireguard implementation that has a web-based UI to help with monitoring connections, QR code generations, and the easy creation of new Wireguard client profiles.

The Github repository is **[WeeJeWel/wg-easy](https://github.com/WeeJeWel/wg-easy), and all credits go to Emile Nijssen** for his work on this solution.

![Infrastructure-Network-VPN-Wireguard-VPN-for-your-Synology-NAS-image2]\(/StudioCompletiva/attachment/Infrastructure-Network-VPN-Wireguard-VPN-for-your-Synology-NAS-image2.png)

# WG-Easy web UI example

### Running WG-EASY in Docker using Portainer

You can run the Docker version of this solution using the **weejewel/wg-easy** image from the hub.docker.com repository.

There are options to use the docker run command or run it via docker-composemethod (personally I prefer it over Portainer).

If you are looking to run it via docker run use the following block via SSH as a root user on your NAS.

```
$ docker run -d
--name=wg-easy
-e WG_HOST=YOUR_SERVER_IP
-e PASSWORD=YOUR_ADMIN_PASSWORD
-v ~/.wg-easy:/etc/wireguard
-p 51820:51820/udp
-p 51821:51821/tcp
--cap-add=NET_ADMIN
--cap-add=SYS_MODULE
--sysctl="net.ipv4.conf.all.src_valid_mark=1"
--sysctl="net.ipv4.ip_forward=1"
--restart unless-stopped
weejewel/wg-easy
```

>[!NOTE]  Be sure to change the WG_HOST and PASSWORD to values that correspond to your needs. For the WG_HOST enter your **public IP address or DDNS name**, and the PASSWORD is any password that you will use in order to access the web UI for this server.

Unlike docker run you can run and maintain this container using docker-compose. I run it over **Portainer's** stack function. If you are unfamiliar with [Portainer](https://www.blackvoid.club/portainer-docker/) or its [stack feature](https://www.blackvoid.club/portainer-2-6-using-stacks/), be sure to check the articles before moving forward. Of course, you can run the following docker-compose code via command line as well if you do not want to use Portainer or some other Docker solution.

```
version: "3.5"
services:
wgeasy:
image: weejewel/wg-easy
network_mode: "bridge"
container_name: wgeasy
ports:
- "51820:51820/udp"
- "51821:51821"
cap_add:
- NET_ADMIN
- SYS_MODULE
sysctls:
- net.ipv4.conf.all.src_valid_mark=1
- net.ipv4.ip_forward=1
volumes:
- /volume1/docker/wgeasy:/etc/wireguard
environment:
- WG_HOST=<public IP or DDNS address>
- PASSWORD=<Wireguard web ui password>
restart: always
```

After you have made your container and have it up and running, you can check its log. If they look something like this, all is well and running.

```
2022-07-23T11:15:17.553Z Server Listening on <http://0.0.0.0:51821>
2022-07-23T11:15:17.555Z WireGuard Loading configuration...
2022-07-23T11:15:17.567Z WireGuard Configuration loaded.
2022-07-23T11:15:17.568Z WireGuard Config saving...
2022-07-23T11:15:17.569Z WireGuard Config saved.
```

```
$ wg-quick down wg0
$ wg-quick up wg0
```

We can see that the server is running on port **51821** on your NAS local IP address. In order to access the web UI, go to the following URL (<http://yourNASIP:51821>) and enter the password you have configured.

![Infrastructure-Network-VPN-Wireguard-VPN-for-your-Synology-NAS-image3]\(/attachment/Infrastructure-Network-VPN-Wireguard-VPN-for-your-Synology-NAS-image3.png)

Wireguard easy web UI. Enter the password you have configured and login

### Accessing the Wireguard UI and configuring your clients

Now that you have the server side up and running it is time to connect your clients using the official Wireguard client app. Depending on the device, visit the mobile or desktop stores, and download them.

>[!WARN]  Be sure to *open the Wireguard UDP port* (51820 in this case) *on your router*. Without it, your clients will not be able to connect to your server!

One more thing that we need to do is port forward (open) the Wireguard port in order for our clients to be able to connect. This will depend on your router, but if you are running a Synology router, then do the following.

First, log into your router's SRM UI, open the **Network Center** app, and click on the **Port Forwarding** section in the left menu.

Click the **Create** button and configure the rule as follows.

![Infrastructure-Network-VPN-Wireguard-VPN-for-your-Synology-NAS-image4]\(/StudioCompletivva/attachment/Infrastructure-Network-VPN-Wireguard-VPN-for-your-Synology-NAS-image4.png)

### Configure port forward rule on your Synology router

As the image shows, enter a descriptive **name**, choose your **NAS IP address** from the menu, and finally e**nter the port and protocol**. Confirm your settings by clicking again on the **create** button.

Now we have everything ready to connect our Wireguad compatible devices. Using the UI, click the **+New** button to create a new client configuration. Give it a name, and click **Create**.

![Infrastructure-Network-VPN-Wireguard-VPN-for-your-Synology-NAS-image5]\(/StudioCompletiva/attachment/Infrastructure-Network-VPN-Wireguard-VPN-for-your-Synology-NAS-image5.png)

### Creating a new Wireguard client profile

![Infrastructure-Network-VPN-Wireguard-VPN-for-your-Synology-NAS-image6]\(/StudioCompletiva/attachment/Infrastructure-Network-VPN-Wireguard-VPN-for-your-Synology-NAS-image6.png)

New Wiregurad profile ready to be used. Click the QR button to display the code

Considering that this is a client profile for a mobile device we can use the **QR code** button to present the code and import the configuration that way to your mobile device.

![Infrastructure-Network-VPN-Wireguard-VPN-for-your-Synology-NAS-image7]\(/StudioCompletiva/attachment/Infrastructure-Network-VPN-Wireguard-VPN-for-your-Synology-NAS-image7.png)

Scan the code to pull in the Wiregurad configuration on your mobile device

On your mobile Wiregurad mobile app, click the "+" button to initiate the creation of a new connection and select the **Crate from the QR code** option.

![Infrastructure-Network-VPN-Wireguard-VPN-for-your-Synology-NAS-image8]\(/StudioCompletiva/attachment/Infrastructure-Network-VPN-Wireguard-VPN-for-your-Synology-NAS-image8.png)

Select the second option on your mobile device to activate the camera and scan the QR code

Now just scan the QR code that was presented, and you are good to go.

Once you have the configuration ready, connect and check the UI if your server is registering a successful connection. Also, you are welcome to test access to your LAN resources and see if all is working well.

![Infrastructure-Network-VPN-Wireguard-VPN-for-your-Synology-NAS-image9]\(/StudioCompletiva/attachment/Infrastructure-Network-VPN-Wireguard-VPN-for-your-Synology-NAS-image9.png)

Connection is successfully indicated by the red dot next to your profile avatar. Also, the upload and download indicators will show network traffic in real-time

If your devices are not mobile, you can use the **download** button next to the QR code one to download the configuration and import it into your client Wireguard app.

There you have it, your very own Wireguard server running on your Synology NAS. If you have any questions, comments, or suggestions, feel free to comment in the section below.

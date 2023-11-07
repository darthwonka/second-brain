# Firewall Rules list

Created: 2020-07-02 10:16:43 -0600

Modified: 2020-07-04 21:34:27 -0600

---

10:16 AM

Discord:

You have to open port 443 TCP for textchat and in my case discord everytime uses a different UDP port for voice chat. It is a random UDP port between 50.000 - 65.535. It would be much better to limit discord to 2-3 UDP ports.

*From < <https://www.reddit.com/r/discordapp/comments/3k3ux1/q_how_to_allow_discord_through_firewall/>>*

Slack:

- Check that your network is set up to allow outbound UDP connections on port 22466
- If you don't allow outbound UDP connections on port 22466, allow outbound TCP connections on port 22466 or 443

*From < <https://slack.com/help/articles/115003538426-Troubleshoot-Slack-calls?nojsmode=1>>*

![](../media/Pages-Firewall-Rules-list-image1.png){width="3.1368055555555556in" height="1.6069444444444445in"}

![](../media/Pages-Firewall-Rules-list-image2.png){width="2.904861111111111in" height="2.6368055555555556in"}

Calyptix VPN

CalyptixVPN operates on UDP/1194.

Other Calyptix Ports:

TCP/9443 - Web GUI

TCP/7022 - SSH

UDP/500, UDP/4500 - IPsec

**Required Ports for Steam**

Which ports do I need to open on my router or firewall for Steam?

**To log into Steam and download content:**

- HTTP (TCP remote port 80) and HTTPS (443)
- UDP remote port 27015--27030
- TCP remote port 27015--27030

**Steam Client**

- UDP remote port 27000--27100: Game traffic
- UDP local port 27031-27036: Remote Play
- TCP local port 27036: Remote Play
- UDP remote port 4380

**Dedicated or Listen Servers**

- TCP local port 27015 (default): SRCDS Rcon port
- UDP local port 27015 (default): gameplay traffic

**Steamworks P2P Networking and Steam Voice Chat**

- UDP remote port 3478
- UDP remote port 4379
- UDP remote port 4380

*From < <https://support.steampowered.com/kb_article.php?ref=8571-GLVN-8711>>*

Ubisoft

- TCP: 80,443,50000:52000
- UDP: 3074,30000:32000

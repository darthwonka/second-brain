# Windows Server 2012-2019

Created: 2023-01-25 17:54:06 -0700

Modified: 2023-01-25 17:54:48 -0700

---

Get a Quick look at the health of the AD Forest

dcdiag /v /c /d /e /s:dcname >c:dcdiag.txt

netdiag /v >c:netdiag.txt [from each DC, netdiag may work but isn't supported with Windows server 2008 and higher]

repadmin /showrepl dc* /verbose /all /intersite >c:repl.txt (if more then one DC exists)

dnslint /ad /s "DCipaddress" (<http://support.microsoft.com/kb/321045>)

*From < <https://social.technet.microsoft.com/Forums/windowsserver/en-US/ff235b57-b533-4a62-a0c4-34203ae5d7bb/dfs-management-shows-sysvol-member-is-missing>>*

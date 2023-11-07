# Forest Information

Created: 2023-02-08 11:33:10 -0700
Modified: 2023-02-13 17:17:22 -0700

---

## Get a Quick look at the health of the AD Forest

```
dcdiag /v /c /d /e /s:dcname >c:dcdiag.txt
```

```
netdiag /v >c:netdiag.txt 
```
>[!INFO] from each DC, netdiag may work but isn't supported with Windows server 2008 and higher


```
repadmin /showrepl dc* /verbose /all /intersite >c:repl.txt (if more then one DC exists)
dnslint /ad /s "DCipaddress"
```


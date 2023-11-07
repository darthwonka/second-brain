# Power Failure Shutdown and Recovery

Created: 2023-02-08 17:52:13 -0700
Modified: 2023-02-08 17:56:32 -0700

---

If you have notice of the power outage, or happen to be in the office when one occurs, you can preemptively power down the computers and network devices gracefully. Sometimes this is not possible. If it is, see below:

Locally:

1. Printers/plotters
2. All workstations
3. NAS - use lcd menu navigation to shutdown
4. STUDIOSRV2 (Primary DC) - Hold Power button for 2 seconds
5. STUDIOSRV3 (VM Server) - Hold Power button for 2 seconds
6. printers/plotters (from web interface)
7. all workstations - remote shutdown
8. NAS (remote shutdown).

Power Restored

Steps to power on equipment

*Wait 4 minutes in steps 1 through 4

1. STUDIOSRV2 (Secondary DC)
2. NAS
3. STUDIOSRV3 (VM Server)
4. Wireless router
5. Printers
6. Workstations

If UPS (batteries) keep beeping after power is restored, either power off then on, or, if available, press the status button to silence/clear alarm.


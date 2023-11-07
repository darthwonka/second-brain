# AD/Azure: DirSync on disabling status for more than 72 hours

Created: 2020-06-05 12:40:57 -0600

Modified: 2022-12-08 10:30:18 -0700

---

<table>
<colgroup>
<col style="width: 17%" />
<col style="width: 13%" />
<col style="width: 69%" />
</colgroup>
<thead>
<tr class="header">
<th>Microsoft</th>
<th></th>
<th><p>DirSync on disabling status for more than 72 hours.</p>
<p>Include ticket number and your email.</p>
<p></p>
<p>Send Erwin email with new ticket.</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

1:03 PM Connecting...

1:03 PM Connected. A support representative will be with you shortly.

1:03 PM Support session established with Feroz.

1:03 PM You have granted full permission to Feroz. To revoke, click the red X on the toolbar or press Pause/Break on the keyboard.

1:03 PM Desktop Viewing started by Feroz.

1:26 PM Feroz: Set-ExecutionPolicy RemoteSigned

1:27 PM Feroz: $UserCredential = Get-Credential

1:28 PM Feroz: $Session = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri <https://outlook.office365.com/powershell-liveid/> -Credential $UserCredential -Authentication Basic -AllowRedirection

1:29 PM Feroz: Import-PSSession $Session -DisableNameChecking

1:31 PM Feroz: start-adsyncsynccycle -policytype delta

1:32 PM Feroz: Get-ADSyncScheduler

1:34 PM Feroz: If you need to manually run a sync cycle, then from PowerShell run Start-ADSyncSyncCycle -PolicyType Delta

@DannyBain-4058

As directory synchronization isn't activated or deactivated after 72 hrs, follow these steps, and then contact Support:

Run below PowerShell cmdlets:

- Connect-MSOLService
- (Get-MSOLCompanyInformation).DirectorySynchronizationStatus

If the output is "PendingEnabled" or "PendingDisabled" after the expected enablement time period has passed, this is a known issue with Exchange Online.

Collect the following information from the Windows PowerShell connection:

- Context ID: To collect the context ID, type the following cmdlet, and then press Enter:
		(Get-MSOLCompanyInformation).objectID

- Service instance: To collect the service instance, type the following cmdlet, and then press Enter:
		(Get-MSOLCompanyInformation).AuthorizedServiceInstances

*From < <https://learn.microsoft.com/en-us/answers/questions/33038/directory-synchronization-shows-pendingdisabled-fo.html>>*

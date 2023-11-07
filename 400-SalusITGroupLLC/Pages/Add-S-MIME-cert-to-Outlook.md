# Add S/MIME cert to Outlook

Created: 2022-08-25 10:27:35 -0600

Modified: 2022-09-15 12:42:28 -0600

---

1. Let office 365 be aware of the CA (cacert.org)
2. Import the Cert into Windows Certificates database
3. Associate the Cert with Contact in Outlook

A S/MIME certificate allows users to send you encrypted emails.

You will need the 3rd partie's S/MIME certificate to send encrypted emails to the 3rd party.

Import-ModuleExchangeOnlineManagement

Connect-ExchangeOnline -UserPrincipalName <UPN> [-Showcover:$false] [-ExchangeEnvironmentName <Value>] [-DelegatedOrganization <String>] [-PSSessionOption $ProxyOptions]

Get-ChildItem -Path cert:<StoreCertPath> | Export-Certificate -FilePath "C:My DocumentsExported Certificate Store.sst" -Type SST

Set-SmimeConfig -SMIMECertificateIssuingCA ([System.IO.File]::ReadAllBytes('C:My DocumentsExported Certificate Store.sst'))

$sst = Get-Content <sst file copied from the box>.sst -Encoding Byte

(Example: $sst = Get-Content TenantRoot.sst -Encoding Byte)

Set-SmimeConfig -SMIMECertificateIssuingCA $sst

*From < <https://techcommunity.microsoft.com/t5/exchange-team-blog/how-to-configure-s-mime-in-office-365/ba-p/584516>>*

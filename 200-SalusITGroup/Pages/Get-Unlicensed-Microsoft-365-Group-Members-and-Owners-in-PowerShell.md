# Get Unlicensed Microsoft 365 Group Members and Owners in PowerShell

Created: 2022-01-11 16:56:14 -0700

Modified: 2022-01-11 17:05:00 -0700

---

**Get Unlicensed Microsoft 365 Group Members and Owners in PowerShell**

January 29, 2021by [Morgan](https://morgantechspace.com/author/morgan)

Microsoft 365 Group (aka Office 365 Group) is a cross-application membership service for Microsoft 365 services such as Microsoft Teams, Planner. etc. To use the service like Microsoft Teams, users should have been added as a member in required teams and they should have a valid Teams license.

We can use the **Get-AzureADGroupMember** cmdlet to get members of a group. This command also returns basic user details and applied licenses. Before start, install the Azure AD V2 PowerShell module and run the following to connect the module.

| 1   | Connect-AzureAD |
|-----|-----------------|

Run the below command to get members of a group and their license details.

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 87%" />
</colgroup>
<thead>
<tr class="header">
<th><p>1</p>
<p>2</p>
<p>3</p></th>
<th><p>$Group = Get-AzureADGroup -SearchString '&lt;GroupName&gt;'</p>
<p>#Get Group Members and their license assignments</p>
<p>Get-AzureADGroupMember -ObjectId $Group.ObjectId -All $true | Select DisplayName, AssignedLicenses, UserPrincipalName</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

We can use the **Get-AzureADGroupOwner** cmdlet to get owners of the group.

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 87%" />
</colgroup>
<thead>
<tr class="header">
<th><p>1</p>
<p>2</p></th>
<th><p>$Group = Get-AzureADGroup -SearchString '&lt;GroupName&gt;'</p>
<p>Get-AzureADGroupOwner -ObjectId $Group.ObjectId -All $true | Select DisplayName, AssignedLicenses, UserPrincipalName</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

**Find unlicensed members**

The following command gets the list of group members who are without any license.

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 87%" />
</colgroup>
<thead>
<tr class="header">
<th><p>1</p>
<p>2</p></th>
<th><p>$Group = Get-AzureADGroup -SearchString '&lt;GroupName&gt;'</p>
<p>Get-AzureADGroupMember -ObjectId $Group.ObjectId -All $true | Where-Object { $_.AssignedLicenses.Count -eq 0}</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

**Find unlicensed owners**

<table>
<colgroup>
<col style="width: 12%" />
<col style="width: 87%" />
</colgroup>
<thead>
<tr class="header">
<th><p>1</p>
<p>2</p></th>
<th><p>$Group = Get-AzureADGroup -SearchString '&lt;GroupName&gt;'</p>
<p>Get-AzureADGroupOwner -ObjectId $Group.ObjectId -All $true | Where-Object { $_.AssignedLicenses.Count -eq 0}</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

**Export License Status of all the Group members**

<table>
<colgroup>
<col style="width: 11%" />
<col style="width: 88%" />
</colgroup>
<thead>
<tr class="header">
<th><p>1</p>
<p>2</p>
<p>3</p>
<p>4</p>
<p>5</p>
<p>6</p>
<p>7</p>
<p>8</p>
<p>9</p>
<p>10</p>
<p>11</p>
<p>12</p>
<p>13</p>
<p>14</p>
<p>15</p>
<p>16</p>
<p>17</p>
<p>18</p>
<p>19</p>
<p>20</p></th>
<th><p>$Result = @()</p>
<p>#Get all M365 groups</p>
<p>$AllGroups = Get-AzureADMSGroup -Filter "groupTypes/any(c:c eq 'Unified')" -All $true</p>
<p>$TotalGroups = $AllGroups.Count</p>
<p>$i = 1</p>
<p>ForEach ($Group in $AllGroups) {</p>
<p>Write-Progress -Activity "Processing $($Group.DisplayName)" -Status "$i out of $TotalGroups groups completed"</p>
<p>#Fetch group members</p>
<p>$GroupMembers = Get-AzureADGroupMember -ObjectId $Group.Id -All $true</p>
<p>ForEach ($User in $GroupMembers) {</p>
<p>$Result += New-Object PSObject -property $([ordered]@{</p>
<p>GroupName = $Group.DisplayName</p>
<p>UserName = $User.DisplayName</p>
<p>UserPrincipalName = $User.UserPrincipalName</p>
<p>IsLicensed = if ($User.AssignedLicenses.Count -ne 0) { $true } else { $false }</p>
<p>})</p>
<p>}</p>
<p>$i++</p>
<p>}</p>
<p>$Result | Export-CSV "C:AllGroupMembers.CSV" -NoTypeInformation -Encoding UTF8</p></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

**Get licensed and unlicensed members from all groups**

The below command returns licensed users from all Microsoft 365 groups.

| 1   | $Result | Where-Object {$_.IsLicensed -eq $true} | Select GroupName, UserName |

|----------|--------------------------------------------------------------|

Run the below command to list only the unlicensed group members.

| 1   | $Result | Where-Object {$_.IsLicensed -eq $false} | Select GroupName, UserName |

|----------|--------------------------------------------------------------|

**Get unlicensed users list**

The above command returns the result for all group members. If an unlicensed user is a member of multiple groups, then we will get multiple user name entry for the same user. Run the following command to get only the users list without duplication.

| 1   | $Result | Where-Object {$_.IsLicensed -eq $false} | Select UserName, UserPrincipalName -Unique |

|----------|--------------------------------------------------------------|

**Export the unlicensed user details**

| 1   | $Result | Where-Object {$_.IsLicensed -eq $false} | Select UserName, UserPrincipalName -Unique | Export-CSV "C:UnlicensedMembers.CSV" -NoTypeInformation -Encoding UTF8 |

|----------|--------------------------------------------------------------|

*From < <https://morgantechspace.com/2021/01/get-unlicensed-m365-group-members-powershell.html>>*

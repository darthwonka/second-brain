# Outlook Image Display

Created: 2018-01-05 11:30:05 -0700

Modified: 2018-01-19 14:23:06 -0700

---

•Without Group Policy:

Key: HKEY_CURRENT_USERSoftwareMicrosoftOfficex.0Common

DWORD: BlockHTTPimages

Value: 1

•With Group Policy:

Key: HKEY_CURRENT_USERSoftwarepoliciesMicrosoftOfficex.0Common

DWORD: BlockHTTPimages

Value: 1

If that is the case, please right-click the BlockHTTPimages key, and then click Delete. When you are prompted to confirm the deletion, click Yes. On the File menu, click Exit to exit Registry Editor.

If that is not the cause of the issue, please add the problematic senders to the safe senders list of the Junk E-mail filter option to have a try. Also disable any COM add-ins in Outlook 2016 (File > Options > Add-ins, Manage COM Add-ins, click Go) to check if the issue persists.

*From < <https://social.technet.microsoft.com/Forums/office/en-US/5263ff2d-e435-459c-8fe4-f50771d8b260/outlook-2016-doesnt-display-all-images-in-some-emails?forum=Office2016ITPro>>*

Microsoft Outlook 2016 and 2013:

The behavior occurs if the image is not embedded in the message, and the following registry value is NOT set, or is absent:

HKEY_CURRENT_USERSoftwareMicrosoftOffice**x.0**OutlookOptionsMail

DWORD: Send Pictures With Document

Value: 1

*From < <https://support.microsoft.com/en-us/help/2779191/inline-images-may-display-as-a-red-x-in-outlook>>*

Clear Cache

**Step**

Close Outlook if you currently have it open.

**Step**

Right-click on the "Start" button and click on "Open Windows Explorer" or "Explore," depending on the version of Windows you are currently using.

**Step**

Double-click on the "C:" drive in the left-hand pane to open it in the Windows Explorer window on the right side. Navigate to the "Local SettingsApp Data MicrosoftOutlook" or the "Local SettingsApplication Data MicrosoftOutlook" folder.

**Step**

Delete the ".dat" file to clear the "Microsoft Outlook Data" file. Delete the ".fav" file to clear the favorites. Delete the ".nk2" file to clear the "Nickname Cache" file. Delete the ".oab" file to clear the offline address book. Delete the ".ost" file to clear the offline file. Delete the ".pab" file to clear the address book. Delete all or some of these files to clear the cache in Outlook. Do not delete the ".pst" file; this is your Personal Folder File that Outlook uses to open your inbox and all of your personal folders, such as your calendar items and signature settings.

**Step**

Close Windows Explorer when done and restart the computer for the changes to take effect. Click on "Start" again, then "Run." If using Windows Vista/7, you don't have to click on "Run," just start typing in the "Search" box. Type "outlook/cleanprofile." This will finish cleaning the cache and open Outlook.

*From < <https://www.techwalla.com/articles/clean-outlook-cache>>*

Another thing to try:

Reset the Internet Explorer settings to their default settings (Control Panel / Internet Options / Advanced tab) and it cleared up the problem in Outlook.

*From < <https://social.technet.microsoft.com/Forums/office/en-US/5263ff2d-e435-459c-8fe4-f50771d8b260/outlook-2016-doesnt-display-all-images-in-some-emails?forum=Office2016ITPro>>*

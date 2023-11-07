# Upgrade to 12.3

Created: 2020-06-08 11:47:27 -0600
Modified: 2020-06-08 11:47:43 -0600

---

# Project: 2014.6.10 **Release Distribution**

Notification about File Transfer **Update Package (12.3.0.16427) - Newforma Project Center**

A transfer (Shared Folder) has arrived on the Newforma Info Exchange Site.

# Remarks

This transfer contains the executables and links to documentation for updating Newforma Project Center Twelfth Edition to the latest release.

Release Notes for Newforma Project Center 12.3.0 can be found in this transfer package as well as on the [Newforma Customer Community](https://customercommunity.newforma.com/s/topic/0TOU0000000CwXbOAK/release-notes) (Login Required).<br><br>Please **carefully** read the following links for important information regarding your upgrade:|

---

# Step 1: Download files to Newforma servers

Please download **all files** (at the end of this email) included in this transfer and distribute to each of your Newforma servers:

## Info Exchange Server

• NewformaInfoExchangeServerSetup64.exe

## Project Center Server

• NewformaProjectCenterServerSetup64.exe
• NewformaProjectCenterOffice32Setup.exe
• Newformaapisetup.exe

# Step 2: Update Newforma Info Exchange Server

[Update Newforma Info Exchange Server](https://customercommunity.newforma.com/s/article/12-UD-NIX-SVR)

The Newforma Info Exchange Update executable is attached to the Update Transfer as **NewformaInfoExchangeServerSetup64.exe**.

# Step 3: Update Newforma Project Center Server

[Update Newforma Project Center Server](https://customercommunity.newforma.com/s/article/12-UD-NPCS-SVR)

The Newforma Project Center Server Update executable is attached to the Update Transfer as **NewformaProjectCenterServerSetup64.exe**.

NOTE: Work Services instances do not require an update.

# Step 4: Install/Update Newforma API

[Newforma Project Center Enterprise API - Install/Update](https://customercommunity.newforma.com/s/article/12-UD-NPC-API)

The Newforma Project Center Enterprise API (N-API) is required for Newforma Connectors such as Procore and BST. If N-API was installed with Newforma Project Center 12.2.x, it will automatically update however, installing this software package ahead of the update will ensure Newforma Connectors work immediately.

# Step 5: Update Newforma Project Center Clients

**NOTE: The Newforma Project Center client on ALL user systems must be upgraded to version 12.3.0.15819 after upgrading the Newforma Project Center Server. This is due to changes made in how text is stored for activity centers such as Meeting Minutes, Submittals and RFIs. Failure to upgrade the client will may cause text formatting to be lost.**

[Update Newforma Project Center Clients](https://customercommunity.newforma.com/s/article/12-UD-NPC-CLIENT)

There are two client update installers included in the Update Transfer:
|---|---|
|NewformaProjectCenterOffice32Setup.exe | For clients with 32-Bit Microsoft Office | 
|NewformaProjectCenterOffice64Setup.exe | For clients with 64-Bit Microsoft Office |

>[!NOTE]  MSI versions of the installers are not provided for this release as there are Microsoft prerequisites included in the .EXE that cannot be installed using a .MSI.


# Step 6: Install/Upgrade Newforma Project Center System Health Tracker

Version 4.0 of the Newforma System Health Tracker uses a PowerShell script to deploy and upgrade the dashboard. For guidance and instructions on how to upgrade the Newforma System Health Tracker dashboard or deploy it for the first time in your Newforma environment, please refer to the [Newforma System Health Tracker Version 4.0 Installation and Upgrade Instructions](https://customercommunity.newforma.com/s/article/Newforma-System-Health-Tracker-Version-4-0-Installation-and-Upgrade-Instructions). For details on the defects that were fixed in this version of the dashboard, along with all of the enhancements and new functionality that was added, please refer to the [Newforma System Health Tracker Version 4.0 Release Notes](https://customercommunity.newforma.com/s/article/Newforma-System-Health-Tracker-4-0-Release-Notes). For instructions on how to customize and configure the System Health Tracker dashboard, please refer to the [System Health Tracker Post-Configuration Considerations](https://customercommunity.newforma.com/s/article/Newforma-System-Health-Tracker-Post-Installation-Configuration-Considerations) document for instructions.

Last minute update!

A new delighter in 12.3 is the addition of the Company Logo in the Email Notification Template. An issue was discovered with Mac clients viewing the email notification where the logo overlapped some text. While it didn’t make the release cut, we feel you would get value from the new template. After 12.3 is installed, drop the GenericNotification.docx template into the C:NewformaTemplatesTwelfth EditionGenericNotification directory. If you don't update the Generic Notification template, you will still receive the new look and feel, it just won't have the Company logo at the top. We will include this new template version in our next NPC Enterprise Suite release.

Congratulations! You made it through the update!

Learn More

[What's New in Project Center](http://help.newforma.com/Newforma_Project_Center_Twelfth_Edition/desktop/Whats_New/What_s_New_in_Version_2.htm)

[Automatic Client Install](http://help.newforma.com/Newforma_Project_Center_Twelfth_Edition/desktop/How_Tos/Update_Project_Center_Clients_Automatically.htm)

[Database stored Project Templates](http://help.newforma.com/Newforma_Project_Center_Twelfth_Edition/desktop/Overviews/Project_Overview.htm)

[Newforma Customer Community](https://customercommunity.newforma.com/s/)

Need Help?

|If you have any questions about your update, please email [services@newforma.com](mailto:services@newforma.com).|
 [Download all files](https://infoexchange.newforma.com/DownloadWeb/predownload.aspx?qs=LR82FPL2GKZR6PLHJYMHCNNRNK7MULWTTRYH2G5JFJAH6XKLJWSGX535GMH4UZFKCUTZ2K6RP75C5N2ZRMAB7NG555GLGF99D3B4FRDGWGUKTPPEVU6RY63WP4KTZ79D8VK58MLCRRHDNMRWUMD4JS23R9D82DGAWCA52BMVFHC4TB3985LAH7V686D6H6Q4N6CQ5SS8U57XK3P6L38TQ6VXR2)

File Transfer Info
Expiration Date: **None**
Transferred Files

|[**12.3.1 Release Notes.pdf**](https://infoexchange.newforma.com/DownloadWeb/predownload.aspx?qs=LR82FPL2GKZR6PLHJYMHCNNRNK7MULWTTRYH2G5JFJAH6XKLJWSGX535GMH4UZFKCUTZ2K6RP75C5N2ZRMAB7NG555GLGF99D3B4FRDGWGUKTPPEVU6RY63WP4KTZ79D8VK58MLCRRHDNMRWUMD4JS23R9D82DGAWCA52BMVFHC4TB3985LAH7V686D6H6Q4N6CQ5SS8U57XRG82326WTEULRFK3ENT4YK5KMWS5PT7GZAZ7G99FP37PKBYM77K6)|5/8/2020|12:29 PM|795 KB|
|---|---|---|---|
|[**GenericNotification.docx**](https://infoexchange.newforma.com/DownloadWeb/predownload.aspx?qs=LR82FPL2GKZR6PLHJYMHCNNRNK7MULWTTRYH2G5JFJAH6XKLJWSGX535GMH4UZFKCUTZ2K6RP75C5N2ZRMAB7NG555GLGF99D3B4FRDGWGUKTPPEVU6RY63WP4KTZ79D8VK58MLCRRHDNMRWUMD4JS23R9D82DGAWCA52BMVFHC4TB3985LAH7V686D6H6Q4N6CQ5SS8U57XKM5R79KHHXSAZGK3JLZVLP358SEVTZGLG2EU7H3XY3MURQMAW3SL)|3/13/2020|4:08 PM|34 KB|
|[**MySQLMigrator-12.3.zip**](https://infoexchange.newforma.com/DownloadWeb/predownload.aspx?qs=LR82FPL2GKZR6PLHJYMHCNNRNK7MULWTTRYH2G5JFJAH6XKLJWSGX535GMH4UZFKCUTZ2K6RP75C5N2ZRMAB7NG555GLGF99D3B4FRDGWGUKTPPEVU6RY63WP4KTZ79D8VK58MLCRRHDNMRWUMD4JS23R9D82DGAWCA52BMVFHC4TB3985LAH7V686D6H6Q4N6CQ5SS8U57XRDEMZDZAD7BZR9YR7FWS3JTZNM8E6D6AXKDGZJPCDYGH29B3JG4F)|5/15/2020|5:49 PM|628,407 KB|
|[**newformaapisetup.exe**](https://infoexchange.newforma.com/DownloadWeb/predownload.aspx?qs=LR82FPL2GKZR6PLHJYMHCNNRNK7MULWTTRYH2G5JFJAH6XKLJWSGX535GMH4UZFKCUTZ2K6RP75C5N2ZRMAB7NG555GLGF99D3B4FRDGWGUKTPPEVU6RY63WP4KTZ79D8VK58MLCRRHDNMRWUMD4JS23R9D82DGAWCA52BMVFHC4TB3985LAH7V686D6H6Q4N6CQ5SS8U57XRHHH4BNY6XB3W5MKNN744KL9K593N8MHJ9BVHRCT5M6WHZG7BRLM)|3/9/2020|4:45 PM|66,159 KB|
|[**NewformaInfoExchangeServerSetup64.exe**](https://infoexchange.newforma.com/DownloadWeb/predownload.aspx?qs=LR82FPL2GKZR6PLHJYMHCNNRNK7MULWTTRYH2G5JFJAH6XKLJWSGX535GMH4UZFKCUTZ2K6RP75C5N2ZRMAB7NG555GLGF99D3B4FRDGWGUKTPPEVU6RY63WP4KTZ79D8VK58MLCRRHDNMRWUMD4JS23R9D82DGAWCA52BMVFHC4TB3985LAH7V686D6H6Q4N6CQ5SS8U57XRUN7D6W3CHAYGMZ7EZMF9Z7ZPXTQXN2ANA8LCBNKUSLBRAHU6FTBEKMAU8VYQWCPPGXXR6R2VKU5QS)|4/23/2020|11:45 AM|1,075,771 KB|
|[**NewformaProjectCenterOffice32Setup.exe**](https://infoexchange.newforma.com/DownloadWeb/predownload.aspx?qs=LR82FPL2GKZR6PLHJYMHCNNRNK7MULWTTRYH2G5JFJAH6XKLJWSGX535GMH4UZFKCUTZ2K6RP75C5N2ZRMAB7NG555GLGF99D3B4FRDGWGUKTPPEVU6RY63WP4KTZ79D8VK58MLCRRHDNMRWUMD4JS23R9D82DGAWCA52BMVFHC4TB3985LAH7V686D6H6Q4N6CQ5SS8U57XRUN7D6W3CHAYGMFCWZX52A5QLFC3KQNKRR4KXNRUNXSCNWVTSCQA62YNEAG26LVXSGECQ95GN2Y2Z2)|4/29/2020|9:50 AM|553,903 KB|
|[**NewformaProjectCenterOffice64Setup.exe**](https://infoexchange.newforma.com/DownloadWeb/predownload.aspx?qs=LR82FPL2GKZR6PLHJYMHCNNRNK7MULWTTRYH2G5JFJAH6XKLJWSGX535GMH4UZFKCUTZ2K6RP75C5N2ZRMAB7NG555GLGF99D3B4FRDGWGUKTPPEVU6RY63WP4KTZ79D8VK58MLCRRHDNMRWUMD4JS23R9D82DGAWCA52BMVFHC4TB3985LAH7V686D6H6Q4N6CQ5SS8U57XRUN7D6W3CHAYGMFCWZX52A5QLFC3KQNKRR4KXNRUNXSCNWVTSCQA4CBSEWVZAV8VPQ574BFYSCM4VS)|4/29/2020|10:36 AM|559,766 KB|
|[**NewformaProjectCenterServerSetup64.exe**](https://infoexchange.newforma.com/DownloadWeb/predownload.aspx?qs=LR82FPL2GKZR6PLHJYMHCNNRNK7MULWTTRYH2G5JFJAH6XKLJWSGX535GMH4UZFKCUTZ2K6RP75C5N2ZRMAB7NG555GLGF99D3B4FRDGWGUKTPPEVU6RY63WP4KTZ79D8VK58MLCRRHDNMRWUMD4JS23R9D82DGAWCA52BMVFHC4TB3985LAH7V686D6H6Q4N6CQ5SS8U57XRUN7D6W3CHAYGMFCWZX52A5QLFC3KQNKRR4KXNRQKGSFE5VB5DB43F65DBDSMSQ7T3ZCG9845FBJNX)|4/23/2020|11:45 AM|1,435,542 KB|
|[**NewformaWorkService64Setup.exe**](https://infoexchange.newforma.com/DownloadWeb/predownload.aspx?qs=LR82FPL2GKZR6PLHJYMHCNNRNK7MULWTTRYH2G5JFJAH6XKLJWSGX535GMH4UZFKCUTZ2K6RP75C5N2ZRMAB7NG555GLGF99D3B4FRDGWGUKTPPEVU6RY63WP4KTZ79D8VK58MLCRRHDNMRWUMD4JS23R9D82DGAWCA52BMVFHC4TB3985LAH7V686D6H6Q4N6CQ5SS8U57XRUN7D6W3CHAYGMRZ9A8S34B6YG6TAR37BKP74NY474YLGYY7S7256J3KKXB8Q5WZS)|4/23/2020|11:32 AM|1,275,549 KB|
|[**NPC System Health Tracker version 4.01.zip**](https://infoexchange.newforma.com/DownloadWeb/predownload.aspx?qs=LR82FPL2GKZR6PLHJYMHCNNRNK7MULWTTRYH2G5JFJAH6XKLJWSGX535GMH4UZFKCUTZ2K6RP75C5N2ZRMAB7NG555GLGF99D3B4FRDGWGUKTPPEVU6RY63WP4KTZ79D8VK58MLCRRHDNMRWUMD4JS23R9D82DGAWCA52BMVFHC4TB3985LAH7V686D6H6Q4N6CQ5SS8U57XKXCN248R2YNJH5TJVX5DJVCWJWXW7DJGLUXLZRNSFFXZ6X6MC87M6EWHWLZZ9VCPXX6QPSYS9DBPGXLYZAFZUUWKQNA)|3/19/2020|3:26 PM|12,888 KB|

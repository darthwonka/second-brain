# Merge Duplicate users

Created: 2020-06-16 11:41:13 -0600

Modified: 2020-06-16 11:41:52 -0600

---

Answer

Use the **Merge Contacts** tool in Project Center to merge two contacts into one. This tool is also useful for reassigning project items when a user leaves the company.

**Additional information**

The information for the two contacts will be merged across all projects. Choose the contact whose information you want to use throughout Project Center. The other contact will be safely deleted from the Newforma database.

The following fields are affected on the new primary contact:

- The primary contact fields (names, email address, phone numbers, company, and office location, etc.) are preserved.
- If the deleted contact has [Info Exchange](http://help.newforma.com/robohelp/robo/server/general/projects/Project%20Center%20Tenth%20Edition%20Help/Overviews/Info_Exchange_Overview.htm) access but the primary does not, the primary contact inherits the deleted contact's Info Exchange settings.
- If the deleted contact has a user association and the primary does not, the primary contact inherits the deleted contact's user.
- The primary contact inherits all of the deleted contact's My Projects list.
- The primary contact becomes a project team member on all of the deleted contact's project teams with the following settings:
		- Project team member settings are preserved at the highest level including primary contact, Info Exchange access, accepted disclaimer, team visibility, and permission sets.
		- The primary contact becomes a group member on all project team groups the deleted contact belonged to.
		- The primary contact inherits all of the deleted contact's member/group subscriptions.
		- If the deleted contact has project administrator/manager/principle in charge/main contact associations but the primary contact does not, the primary contact inherits the deleted contact's values.

**To merge contacts**

1. Open Project Center and then open Project Center Administration.
2. Click the **Contacts** tab.
3. In the **Tasks** list, click **Show Ad Hoc Contacts** to display all the contacts. If the option is already enabled, **Hide Ad Hoc Contacts** will appear in the list instead.
4. Sort the contacts by the **Email Address** field and check if the user in question is listed twice.
5. If there are duplicates of the user, select two of the contacts, then click **Merge Contacts** from the **Tasks** panel.
6. Click **View** in the **Merge Contacts dialog box** to open the **View Contact dialog box** to view details about the selected contact.
7. Click **OK** to merge the contacts.
8. If there are multiple instances of the contact, continue this same process as you can only merge 2 contacts at one time.

*From < <https://customercommunity.newforma.com/s/article/How-to-combine-users>>*

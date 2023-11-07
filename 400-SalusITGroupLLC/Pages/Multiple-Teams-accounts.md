# Multiple Teams accounts

Created: 2019-06-27 09:43:49 -0600

Modified: 2019-06-27 10:36:21 -0600

---

Microsoft launched [Guest access for Microsoft Teams](https://blogs.office.com/en-us/2017/09/11/expand-your-collaboration-with-guest-access-in-microsoft-teams/) this week, in a move that was welcomed by many. It allows you to invite others from outside your organisation to participate in your Teams.

It's a great move from Microsoft and [once it's set up and working](https://support.office.com/en-us/article/Guest-access-in-Microsoft-Teams-bd4cdeec-4044-4b4b-9df1-beb139013a3f?ui=en-US&rs=en-US&ad=US#ID0EAACAAA=Manage) (you need to enable it as an administrator), it works pretty well.

The experience for this first version does leave a little to be desired, because you need to switch between tenants to see conversations in external organizations. This means if you are chatting with a colleague in your organization's Teams, then you'll have to halt that conversation to go and chat and participate in an external team that you've been invited too.

You can see what the experience of switching is like below:

![Pages-Multiple-Teams-accounts-image1](400-SalusITGroupLLC/attachment/Pages-Multiple-Teams-accounts-image1.gif)

**You can only log into one organization's Teams at once**

On the desktop, you can only launch one copy of Teams at once. On the web, Teams only lets you sign into and chat once per logged in session -- so the only workaround on the web is multiple Chrome profiles, or perhaps an "InPrivate" profile to log into a second instance.

**The good news is, there is a workaround**

What if you could launch multiple Teams clients on the desktop, each configured to a separate tenant?

Well -- you can -- and this can be irrespective of the actual sign in account (for example, if you've got multiple Office 365 identities) -- but here it is well suited to logging into multiple organizations as a Guest alongside your home tenant.

If you like what you see below -- then follow the next few steps.

![Pages-Multiple-Teams-accounts-image2](SalusITGroupLLC/attachment/Pages-Multiple-Teams-accounts-image2.gif)

As a caveat, it's important to note that we aren't actually launching multiple desktop teams clients. What we're doing is "wrapping" the guest access to each tenant into a Chromium based app using something called [Electron](https://electron.atom.io/apps/). It is NOT a desktop Teams client, but it's pretty close.

**How to make your additional Teams clients**

To make the apps themselves we need to install a tool. These are only used for the creation and can be uninstalled straight after.

We use Node.js to run Nativefier, which allows us to quickly make an app from any web page. [Download and install the current version of Node.js](https://nodejs.org/en/download/), then install it. I chose the 64-bit Windows MSI version.

![Pages-Multiple-Teams-accounts-image3](SalusITGroupLLC/attachment/Pages-Multiple-Teams-accounts-image3.gif)

After installation, it's recommended to reboot.

Next, you'll need to know the URL to use. We need the teams.microsoft.com URL, plus the tenant ID.

Go into Teams via a web browser, then navigate to the Teams organization/account you want your app to always launch into:

![Pages-Multiple-Teams-accounts-image4](SalusITGroupLLC/attachment/Pages-Multiple-Teams-accounts-image4.gif)

After choosing the Teams org/account, grab the URL from the address bar. It should look like this:


![Pages-Multiple-Teams-accounts-image5](SalusITGroupLLC/attachment/Pages-Multiple-Teams-accounts-image5.gif)

If you want, [grab the Teams icon as PNG](https://www.allabout365.com/wp-content/uploads/Teams.png) and save it locally. This will allow you to have a Teams icon for your app.

Next, launch a command prompt.

![Pages-Multiple-Teams-accounts-image6](SalusITGroupLLC/attachment/Pages-Multiple-Teams-accounts-image6.gif)

Run **npm install nativefier** to get the nativefier application.

Then, from your home directory (for example, c:userssteve) run **node_modules.binnativefier.cmd** followed by the URL, the --name parameter which will be used to name your app, and the --icon parameter with the path to the Teams icon.

**node_modules.binnativefier.cmd <https://teams.microsoft.com/_?tenantID=GUID> --name "Teams -- Ext Network" --icon Teams.png**

node_modules.binnativefier.cmd <https://teams.microsoft.com/_?tenantID=6838dd9b-7604-4959-8854-569a22be3d44> --name "Teams - ASFMRA" --icon Teams.png

node_modules.binnativefier.cmd <https://teams.microsoft.com/_?tenantID=e324f2de-1328-4297-a192-4ce02acb49ef> --name "Teams - StudioCompletiva" --icon Teams.png

node_modules.binnativefier.cmd <https://teams.microsoft.com/_?tenantID=ad6ca1cb-6b5c-44fb-8596-9e2e20a959c5> --name "Teams - SalusITGroup" --icon Teams.png

A folder containing the application will be created in the current directory. Once it's created, move it to somewhere you prefer. Launch your Teams app from within the folder, or even create a shortcut where it's convenient -- it's up to you.

![Pages-Multiple-Teams-accounts-image7](SalusITGroupLLC/attachment/Pages-Multiple-Teams-accounts-image7.gif)

Repeat the step to grab the tenant ID, and run the nativefier command as many times as you like for each Teams organisation / account you want to make an application for:

![Pages-Multiple-Teams-accounts-image8](SalusITGroupLLC/attachment/Pages-Multiple-Teams-accounts-image8.gif)

Launch each one, and sign in. Between launches it will remember your sign-in.

Remember, for full Teams features and supportability, use the official Teams client -- this will not support any more functionality than you will get in the web browser; but if you are just looking to keep up to date with chats across multiple Teams orgs/accounts, then this is a great interim solution.

![Pages-Multiple-Teams-accounts-image9](SalusITGroupLLC/attachment/Pages-Multiple-Teams-accounts-image9.gif)


Enjoy!

*From < <https://www.allabout365.com/2017/09/multiple-teams-accounts/>>*

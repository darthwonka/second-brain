---
dg-publish: true
---

---


# Microsoft Teams 

## How do I use Teams with multiple business accounts? 
Ideally, Microsoft will do what they do with other applications like OneNote and Outlook -- both can handle multiple business accounts.  But they don't do this for Teams.. yet. 

There are a lot of options on the Internet for this issue, but most require using the browser version of teams and a 'Container' extension for the browser to separate the instances.    This definitely works... 

I prefer to use the suggestion from [this reddit post](https://www.reddit.com/r/MicrosoftTeams/comments/igde53/script_to_launch_multiple_microsoft_teams/)

1. Install the latest Teams.  
2. Create a folder on your Desktop called 'Teams'  
>[!note]
> Substitute Desktop/Teams for whatever location you choose to use.
1.  Create a text file in the new folder that represents the teams profile you will use with it.  i.e. `default-teams` or `companyB-teams`  and change the file extension from `.txt` to `.cmd`
2. Copy this code below into the new file.     

``` @ECHO OFF
REM Uses the file name as the profile name
SET MSTEAMS_PROFILE=%~n0
ECHO - Using profile "%MSTEAMS_PROFILE%"
SET "OLD_USERPROFILE=%USERPROFILE%"
SET "USERPROFILE=%LOCALAPPDATA%\Microsoft\Teams\CustomProfiles%MSTEAMS_PROFILE%"
ECHO - Launching MS Teams with profile %MSTEAMS_PROFILE%
cd "%OLD_USERPROFILE%\AppData\Local\Microsoft\Teams"
"%OLD_USERPROFILE%\AppData\Local\Microsoft\Teams\Update.exe" --processStart "Teams.exe" 
```

3. Copy the new file to the same location and rename the file for each additional Teams profile you want to run.
```
companyA-teams.cmd
companyB-teams.cmd
companyC-teams.cmd
etc.
```

## Run the separate instances
Run each of the files by double-clicking on them. 
You will be prompted to authenticate with microsoft.  
Use the credentials for the Teams account associated with the profile  you double-clicked on. 

Repeat for each cmd file.  

done. 
> [!NOTE]
 > This also seems to work with GUEST Teams accounts

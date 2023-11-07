# Disable Bing Search windows 10

Created: 2020-02-10 14:03:19 -0700

Modified: 2020-02-10 14:04:31 -0700

---

Given the volume of people reporting this in a short period of time, the issue is likely server side. I wouldn't do anything about it at this time, the issue should resolve itself soon.

If you really must have a working search before then, you can disable the online search feature. By default, search mixes offline and online results, and the issue is with the online portion. You just need to change or create a pair of registry keys

- Run **Regedit.exe**
- Browse to **HKEY_CURRENT_USERSOFTWAREMicrosoftWindowsCurrentVersionSearch**
- Look for "**BingSearchEnabled**", if you don't see it you will need to create it, just right click in a blank area and pick New **DWORD 32 bit**. Type in **BingSearchEnabled**
- Double click on **BingSearchEnabled** and set it to **0** and press OK.
- Do the same steps for **CortanaConsent**, if you don't see it, create a **DWORD 32 bi**t, again set it to **0**.
- Reboot.

Here are pictures and more details on each step. There is also a zip file you can download that has the registry keys so if you are not comfortable messing with the registry you can run that instead. <https://www.howtogeek.com/224159/how-to-disable-bing-in-the-windows-10-start-menu/>

To undo this after Microsoft fixes the issue, just delete the two registry keys we created, or change their values from 0 to 1.

*From < <https://www.reddit.com/r/Windows10/comments/ez8gan/windows_10_search_bar_not_working_after/>>*

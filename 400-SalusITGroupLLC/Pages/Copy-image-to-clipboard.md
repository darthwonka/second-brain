# Copy image to clipboard

Created: 2019-04-17 13:41:20 -0600

Modified: 2019-04-17 13:41:32 -0600

---

Download [nircmd](http://www.nirsoft.net/utils/nircmd.html) and extract it or install it to "C:nircmd" or a similar location. Within the folder will be 'nircmdc.exe.'

This can be used to copy an image to the clipboard. But, this still isn't quite as easy as you were hoping, so let's make it easier:

[Open your registry editor](http://www.wikihow.com/Open-Regedit).

Now, if you are unfamiliar with regedit, you may wish to find more help, but I will try to make this as simple as possible. First expand "HKEY_CLASSES_ROOT," then "*," then "Shell." Right-click on "Shell" and select "New->Key." Name this key whatever you want for example, "Copy Image to Clipboard." Now, right-click on this newly created key and once again select "New->Key." This one you will name, "command." On the right side, you will now see a value labeled "(default)". Double-click this item and under "Value Data:" put,

C:nircmdnircmdc.exe clipboard copyimage "%1"

Quoting the %1 parameter allows this to work with filenames that contain spaces.

Please note if you did not install it the same way as I did this may not be the exact location and you would need to replace "C:nircmdnircmdc.exe" with the proper address to that executable file.

Once complete, you will be able to right-click a file and select "Copy Image to Clipboard." From this point forward doing what you need will be just that simple.

*From < <https://superuser.com/questions/372602/how-to-copy-picture-from-a-file-to-clipboard>>*

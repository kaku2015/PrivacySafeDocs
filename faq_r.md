### Why Sgallery needs "Allow access to all files" permission on Android 11?

Because of the limitation of Google Play, on Android 11 devices, apps must require "Allow access to all files" permission to access the files in the external storage. The permission was granted through a permission request dialog on the Android 10 and lower devices.

**Here is the reason why Sgallery needs permission:**

1. Sgallery stores the encrypted files in .privacy_safe on external storage. By doing this, the encrypted files will stay there if Sgallery is uninstalled accidentally and after you install Sgallery again, Sgallery can restore the data for you.

2. Sgallery supports encrypting any type of files on your external storage. Without permission, it is impossible to add the files on external storage to Sgallery.

3. The backup and restore function also needs permission.

And this is the official explanation: https://developer.android.com/training/data-storage/manage-all-files#all-files-access-google-play

Thanks for understanding.

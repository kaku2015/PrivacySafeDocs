### Device Owner (Non ROOT) Mode Setup

### Notice:
- Due to limitations of the MIUI system such as Xiaomi, Hide App feature may be invalid. Please activate it with caution.
- The latest version of the Huawei EMUI system (341 or above) may cause mobile phone restart and lose individual system apps after activating ADB. This is caused by the latest version of the EMUI bug. Please activate it with caution. The solution after this problem occurs: Hide the missing apps and unhide it. You can also restore after uninstalling the app and restarting your phone.
- Please clear the lock screen password before Samsung S8+ Android8.0 is activated. After ADB is activated, it may cause the administrator to lock and inaccessible after booting, and may cause problems such as facial recognition unusable. Please activate it with caution.

### Setup steps:
1. Make sure your phone running Android  6.0+ and you know how to use [ADB](https://www.xda-developers.com/install-adb-windows-macos-linux/) clearly.
</br>[Click here to view the ADB tutorial](https://www.xda-developers.com/install-adb-windows-macos-linux/)
2. Go to "Settings > Accounts", remove **all accounts** including your Google account.
</br>**Take Huawei mobile phone as an example:**
</br>` Exit Huawei account `

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images/delete_account_1.jpg)

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images/delete_account_2.jpg)

` Delete multiple users `

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images/delete_account_3.jpg)

` All of the following accounts need to be deleted `

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images/delete_account_4.jpg)

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images/delete_account_5.jpg)

` After deleting all accounts as follows `

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images/delete_account_6.jpg)

It is recommended that the phone remain on this account interface, as some apps will be automatically added back soon after the account is deleted, ensuring that the account is not automatically added before activation.

3. If multi-user or guest mode has been set on your device, also need to be closed or deleted.
4. Run ```adb shell dpm set-device-owner com.hld.anzenbokusu/.receiver.DPMReceiver``` on your computer.

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images/cmd_1.png)

5. If you see the words Success, you can open the Sgallery to use (may need to restart your phone) , then you can add your accounts and guest mode back.

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images/cmd_2.png)

### FAQ

- **Q: It shows "no devices/emulators found"**
- A: USB debugging is not turned on, or the USB is not connected properly.

- **Q: It shows "Not allowed to ... already several accounts on the device"**
- A: Please follow step 2 and remove ALL accounts. PS: Pulling out SIM card may be required for Xperia and ZUK devices.
</br>**Added: You can use the command ```adb shell pm list users``` view the accounts, use the command ```adb shell pm remove-user user id``` to delete the account.**

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images/delete_account.png)

- **Q: It shows "Not allowed to ... already several users on the device"**
- A: Please follow step 3 and remove the guest mode or multi app/private mode.

- **Q: It shows "Trying to set the device owner, but device owner is already set"**
- A: You have set up other app using Device Owner mode, please cancel the settings of other app.

- **Q：After removing the account, you are prompted "Your administrator will not allow this change"**
- A：Please remove the fingerprint and lock screen password before removing the account.

- **Q: It shows "Sets the given component as active admin..."**
- A: Please reboot your phone.

- **Q: After all the above operation still shows "xxx"**
- A: Please reboot your phone.

- **Q: Huawei EMUI system, individual system apps disappear after activating ADB.**
- A: This is caused by a bug in the latest version (more than 341) of the EMUI system. The solution to this problem is to hide the missing app and then unhide it. You can also restore after uninstalling the app and restarting your phone.

- **Q: There is "Device is managed by your organization" on my notification center after setting up. Why?**
- A: That is how Sgallery works.

- **Q: How to uninstall Sgallery?**
- A: Just select "Uninstall" in the settings of Sgallery.



###Device Owner (Non Root) Mode Setup

1. Make sure your phone running Android  5.0+ and you know how to use [ADB](https://www.xda-developers.com/install-adb-windows-macos-linux/) clearly.
2. Go to "Settings - Accounts", remove ALL ACCOUNTS including your Google account.
3. If multi-user or guest mode has been set on your device, also need to be closed or deleted
4. Run "adb shell dpm set-device-owner com.hld.anzenbokusu/.receiver.DPMReceiver " on your computer.
5. Reboot then you can add your accounts and guest mode back.

###FAQ

- Q: It shows "Not allowed to ... already several users on the device"
- A: Please follow step 2 and remove the guest mode.

- Q: It shows "Trying to set the device owner, but device owner is already set"
- A: You have set up other app using Device Owner mode, please cancel the settings of other app.

- Q: There is "Device is managed by your organization" on my notification center after setting up. Why?
- A: That is how BlackHole works.

- Q: How to uninstall BlackHole?
- A: Just select "Uninstall" in the settings of BlackHole.



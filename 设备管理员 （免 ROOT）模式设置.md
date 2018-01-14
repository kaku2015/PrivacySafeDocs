### 设备管理员 （免 ROOT）模式设置方法
※通过设置设备管理员模式可以免 ROOT 使用应用隐藏功能。 


1. 确保您的手机 Android 版本大于等于 5.0，打开了 [USB 调试](https://jingyan.baidu.com/article/0eb457e50b99d003f0a9055f.html)，并且您的电脑已下载好了 [ADB]( https://developer.android.google.cn/studio/releases/platform-tools.html) 工具包。
2. 解压缩下载好的 ADB 压缩包，并进入到 adb 所在目录（platform-tools 目录）。
3. （Windows）按住 Shift 键，并在空白处点击鼠标右键，选择“在此处打开命令窗口”。
4. （macOS）打开 Finder，进入“应用程序”，进入“实用工具”，打开“终端”，把“adb”拖到“终端”里，请使用这个带全路径的“adb”代替下面执行命令里的“.\adb”（复制指令时，请删除重复的“adb”）
5. 进入手机「设置 > 帐户」，删除 **所有** 的帐户，包括你的 Google 帐户（之后可以再登录回来）。
6. 如果您之前设置过多用户或手机自带访客模式、应用双开等，也需要一并关闭或删除（之后可以打开）。
7. 在电脑上执行命令： ```.\adb shell dpm set-device-owner com.hld.anzenbokusu/.receiver.DPMReceiver``` 
8. 如果显示 Success 之类的字样，即可打开第二空间使用了（可能需要重启您的手机），也可以把之前删除的帐号加回来了。

### 常见问题：

- **问：提示 “no devices/emulators found”**
- 答：没有打开 USB 调试，或 USB 没有连接好。

- **问：提示 “Not allowed to ... already several users on the device”**
- 答：第 6 步的多用户没删干净，请删除或关闭所有多用户/访客模式/应用双开。

- **问：提示 “Not allowed to ... already several accounts on the device”**
- 答：第 5 步的账户没删干净，请注销您手机上所有的账户，包括 Google 账号和系统自带的如小米账户、三星账户等。
</br>**补充：如已确定删除了所有账户还是提示存在账户，可使用命令 ```adb shell pm list users``` 查看账户后，使用命令 ```adb shell pm remove-user 用户id``` 删除账户。**

- **问：提示 “Trying to set the device owner, but device owner is already set”**
- 答：您已设置过其他应用使用了设备管理员模式，请取消其他应用的设置。

- **问：MIUI 用户提示 “Neither user xxx nor current process has android.permission.MANAGE_DEVICE_ADMINS”**
- 答：MIUI 用户请手动在系统设置- 开发者设置里，开启「USB 调试（安全设置）」。

- **问：以上都操作后还是提示 “xxx”**
- 答：请重启手机再尝试。

- **问：设置完成后手机通知栏出现提示「手机被管理」，这是正常的吗？**
- 答：正常的，这正是第二空间的免 Root 工作原理。

- **问：我不想用了，怎么卸载第二空间？**
- 答：请先取消隐藏掉所有应用，然后到第二空间设置里点击「卸载」即可。

※注意：因为 ROOT 模式与设备管理员模式的隐藏原理不同所以不能互通。如：使用 ROOT 模式隐藏的应用必须通过 ROOT 模式取消隐藏。


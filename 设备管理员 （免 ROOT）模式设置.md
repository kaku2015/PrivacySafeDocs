### 设备管理员 （免 ROOT）模式设置方法
※通过设置设备管理员模式可以免 ROOT 使用应用隐藏功能，只需激活一次，重启无需再次激活，永久有效，除非将第二空间卸载。

秋之盒支持一键激活：https://www.atmb.top/

### 注意事项：
不同厂家的手机系统时常添加各种特色功能，因此其与设备管理员模式的兼容性或多或少存在一些问题，常见如下：
- 受小米 MIUI 等系统的限制，隐藏应用功能可能会无效，请谨慎激活。
- 华为 EMUI 系统最新版本(341以上)，激活 ADB 后可能会出现手机重启、个别系统应用启动图标（图库、手机管家）从桌面消失的问题，这是 EMUI 系统最新版本的 Bug 导致的，请谨慎激活。解决方法也很简单：将图标消失的应用隐藏再移出列表（取消隐藏）即可，或在第二空间内打开。卸载应用并重启手机后亦可恢复。
- 三星 S8+ Android8.0 激活前请先清除锁屏密码，激活 ADB 后可能会导致开机后提示被管理员锁定无法进入，并且可能会导致面部识别无法使用、安全文件夹被系统禁用等问题，请谨慎激活。
- 华为、锤子隐藏应用可能会弹出卸载提示，取消隐藏会弹出权限请求。
- OPPO、VIVO通知栏会提示「设备管理员已开启，点击关闭」。
- 无法隐藏应用分身。
- 一加等刚取消隐藏的应用可能无法联网，关掉后重新打开可以解决。
- 华为、小米等自带的双开可能无法使用。

### 激活步骤：
1. 确保您的手机 Android 版本大于等于 6.0，打开了 [USB 调试](https://jingyan.baidu.com/article/0eb457e50b99d003f0a9055f.html)，并且您的电脑已下载好了 [ADB]( https://developer.android.google.cn/studio/releases/platform-tools.html) 工具包。
</br>[点击这里](https://jingyan.baidu.com/article/0eb457e50b99d003f0a9055f.html)查看打开USB调试教程
</br>PS：手机第一次与PC连接，打开USB调试开关后，正常会弹出授权窗口，勾选后点击确认即可。如果始终无法连接(不弹出授权窗口)，可以尝试打开PC上的360手机助手与手机正常连接后再关闭360手机助手。

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images-zh/adb_1.jpg)

2. 解压缩下载好的 ADB 压缩包，并进入到 adb 所在目录（platform-tools 目录）。

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images-zh/adb_2.png)

3. 如果您使用的 PC 是 Windows，请按住 Shift 键，并在空白处点击鼠标右键，选择“在此处打开命令窗口”。

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images-zh/adb_3.png)

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images-zh/adb_4.png)

4. 如果您使用的 PC 是 macOS，请打开 Finder，进入“应用程序”，进入“实用工具”，打开“终端”，把“adb”拖到“终端”里，请使用这个带全路径的“adb”代替下面执行命令里的“.\adb”（复制指令时，请删除重复的“adb”）
5. 进入手机「设置 > 帐户」，删除 **所有** 的帐户，包括你的 Google 帐户（之后可以再登录回来）。
</br>**下面以华为手机为例：**
</br>退出华为账户

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images-zh/delete_account_1.png)

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images-zh/delete_account_2.png)

删除多用户

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images-zh/delete_account_3.png)

以下所有账户都需要删除

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images-zh/delete_account_4.png)

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images-zh/delete_account_5.png)

删除所有账户后如下

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images-zh/delete_account_6.png)

建议手机保持在这个账户界面，因为删除账户后有些应用很快会自动添加回来，确保激活前没有自动添加回来的账户。

6. 如果您之前设置过多用户或手机自带访客模式、应用双开等，也需要一并关闭或删除（之后可以打开）。
7. 在电脑上执行命令： ```.\adb shell dpm set-device-owner com.hld.anzenbokusu/.receiver.DPMReceiver``` 
</br>**请注意这里一定要使用以上命令，截图只是示例**

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images-zh/cmd_1.png)

8. 如果显示 Success 之类的字样，即可打开第二空间使用了（可能需要重启您的手机），也可以把之前删除的帐号加回来了。

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images-zh/cmd_2.png)

### 常见问题：

- **问：提示 “no devices/emulators found”**
- 答：没有打开 USB 调试，或 USB 没有连接好。

- **问：提示 “Not allowed to ... already several users on the device”**
- 答：第 6 步的多用户没删干净，请删除或关闭所有多用户/访客模式/应用双开。

- **问：提示 “Not allowed to ... already several accounts on the device”**
- 答：第 5 步的账户没删干净，请注销您手机上所有的账户，包括 Google 账号和系统自带的如小米账户、三星账户等。注意：如果您的设备是 Xperia 或 ZUK，请尝试拔出 SIM 卡，待配置完成后再插上。
</br>**补充：如已确定删除了所有账户还是提示存在账户，可使用命令 ```adb shell pm list users``` 查看账户后，使用命令 ```adb shell pm remove-user 用户id``` 删除账户。**

![image](https://github.com/kaku2015/PrivacySafeDocs/blob/master/images-zh/delete_account.png)

</br>**小米手机如果都已确认删除，还是提示以上两个问题的话，则需要恢复出厂后再进行设置。恢复出厂后登录小米账号时请不要同步云服务，设置成功后可以随意操作。**

- **问：移除账号后，提示 “您的管理员不允许进行此更改”**
- 答：请先移除指纹及锁屏密码后再移除账号。

- **问：提示 “Trying to set the device owner, but device owner is already set”**
- 答：您已设置过其他应用使用了设备管理员模式，请取消其他应用的设置。

- **问：MIUI 用户提示 “Neither user xxx nor current process has android.permission.MANAGE_DEVICE_ADMINS”**
- 答：MIUI 用户请手动在系统设置- 开发者设置里，开启「USB 调试（安全设置）」。如果提示无法打开安全设置，请先登录小米账户(不要同步云)后再打开安全设置，安全设置开启后请退出小米账户。

- **问：提示 “Sets the given component as active admin...”**
- 答：请重启手机再尝试。

- **问：以上都操作后还是提示 “xxx”**
- 答：PC端请不要打开360手机助手等，打开手机助手后可能会占用PC端口导致无法激活，如果还是提示错误请重启手机再尝试。

- **问：华为 EMUI 系统，激活 ADB 后个别系统应用（图库、手机管家）消失**
- 答：这是 EMUI 系统最新版本(341以上)的 Bug 导致的，出现此问题后的解决方法：隐藏消失的应用后再取消隐藏即可。卸载应用并重启手机后亦可恢复。

- **问：设置完成后手机通知栏出现提示「手机被管理」，这是正常的吗？**
- 答：正常的，这正是第二空间的免 Root 工作原理。

- **问：我不想用了，怎么卸载第二空间？**
- 答：请先取消隐藏掉所有应用，然后到第二空间设置里点击「卸载」即可。

※注意：因为 ROOT 模式与设备管理员模式的隐藏原理不同所以不能互通。如：使用 ROOT 模式隐藏的应用必须通过 ROOT 模式取消隐藏。


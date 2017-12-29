### 设备管理员 （免 ROOT）模式设置方法

1. 首先确保您的手机 Android 版本大于等于 5.0，并且您已经知道如何操作 [ADB](https://sspai.com/post/23509) 命令。
2. 进入手机「设置 > 帐户」，删除 **所有** 的帐户，包括你的 Google 帐户（之后可以再登录回来）。
3. 如果您之前设置过多用户或手机自带访客模式、应用双开等，也需要一并关闭或删除（之后可以打开）。
4. 在电脑上执行（手机终端模拟器不行） adb shell dpm set-device-owner com.hld.anzenbokusu/.receiver.DPMReceiver 
5. 如果显示 Success 之类的字样，即可打开黑洞使用了（可能需要重启您的手机），也可以把之前删除的帐号加回来了。

### 常见问题：

- **问：提示 “Not allowed to ... already several users on the device”**
- 答：第 2 步的多用户没删干净，请删除或关闭所有多用户/访客模式/应用双开。

- **问：提示 “Not allowed to ... already several accounts on the device”**
- 答：第 1 步的账户没删干净，请注销您手机上所有的账户，包括 Google 账号和系统自带的如小米账户、三星账户等。

- **问：提示 “Trying to set the device owner, but device owner is already set”**
- 答：您已设置过其他应用使用了设备管理员模式，请取消其他应用的设置。

- **问：MIUI 用户提示 “Neither user xxx nor current process has android.permission.MANAGE_DEVICE_ADMINS”**
- 答：MIUI 用户请手动在系统设置- 开发者设置里，开启「USB 调试（安全设置）」。

- **问：设置完成后手机通知栏出现提示「手机被管理」，这是正常的吗？**
- 答：正常的，这正是黑洞的免 Root 工作原理。

- **问：我不想用了，怎么卸载黑洞？**
- 答：请先取消隐藏掉所有应用，然后到黑洞设置里点击「卸载」即可。


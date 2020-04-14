# 红米K30 4G  刷欧洲版 MIUI11 + Magisk + 中国本土化组件恢复 教程 

本教程也适用于其他机型的小米手机（除了magisk模块）

## 为什么要买红米来刷机？

我的主力机是 iPhone XR ，但是在许多城市 iPhone 仍然不支持其公交卡功能，iOS 也无法复制门禁卡，大部分电器也依然需要红外线来遥控，这就萌生了我购买一台红米的想法（毕竟这是较为便宜的拥有全功能NFC+红外线的安卓品牌之一）

刷成欧洲版对99%的只用国产app的人来说都是一个没有什么用，甚至是浪费时间的事情，毕竟MIUI已经是当前国内本土化较为完善的安卓系统之一。

但是，我不喜欢国内版的MIUI里面充斥着各类广告，大部分的本土化功能我也基本不用，而欧版 MIUI 是得到欧盟分销商 ABC Data 认可的，所以刷机的首选是欧版。（注：截止发文为止，部分淘宝代刷服务给红米K30的所谓「国际版」是印度版的MIUI，印度版的MIUI同样充斥了大量广告，不建议刷入）

而且如果你像我一样在日常生活中难免会用到一些国际服务，那么拥有一个有国际服务的安卓机，你会发现生活能够便捷很多。

## 准备工作

- Windows 或 Mac
- 数据线
- 小米账号
- 良好的网络连接

在刷机前我们需要解锁手机的BL，下好第三方TWRP以及欧洲版的ROM

下载地址：

MIFLASH：[[http://miuirom.xiaomi.com/rom/u1106245679/3.5.1108.44/miflash\_unlock-3.5.1108.44.zip]](http://en.miui.com/unlock/download_en.html)
TWRP：[https://androidfilehost.com/?fid=4349826312261719578](https://androidfilehost.com/?fid=4349826312261719578)
欧版MIUI ROM：[https://sourceforge.net/projects/xiaomi-eu-multilang-miui-roms/files/xiaomi.eu/MIUI-STABLE-RELEASES/MIUIv11/](https://sourceforge.net/projects/xiaomi-eu-multilang-miui-roms/files/xiaomi.eu/MIUI-STABLE-RELEASES/MIUIv11/) 
Magisk：[https://github.com/topjohnwu/Magisk/releases](https://github.com/topjohnwu/Magisk/releases)
我制作的K30专用小米钱包和应用市场恢复模块：[https://github.com/Aozh1/mipay-extract/releases/tag/10.0](https://github.com/Aozh1/mipay-extract/releases/tag/10.0)

## 刷机流程

### 解锁BL
Bootloder是厂商为了防止用户刷入非官方统而损坏手机的一个保护机制，现在越来越多的厂商以及不提供解锁BL的选项，但是小米仍然提供。

但是小米的解锁和其他开放BL的厂商（比如Google Pixel 和 Oneplus）相比较为麻烦，**需要同时在电脑和手机登陆小米账号，手机必须保持SIM卡插入状态。**

小米的这种做法已经受到了诸多网友诟病：[https://v2ex.com/t/620487](https://v2ex.com/t/620487)

如果你和我一样不幸需要等待长达168个小时，建议出门左转淘宝购买能立即刷机的小米账号或找一个长期是小米用户的朋友借小米账号。

解锁流程非常简单，打开miflash_unlock.exe 插上数据线，重启到fast boot即可（按住电源键和音量下）

### 刷入TWRP
TWRP是知名的第三方recovery，下载解压后Windows用户可直接使用`recovery-twrp一键刷入工具`，按照提示操作,即可进入twrp界面

Mac用户下载谷歌官方ADB工具后，重命名当前的`recovery-TWRP-3.4.0B-0209-REDMI_K30-CN-wzsx150.img`为 `twrp.img`

### 输入命令

	fastboot flash recovery twrp.img
	fastboot boot twrp.img

即可进入TWRP界面

### 输入欧版MIUI

进入TWRP，先进入Wipe，勾选Dalvik/Cache/Data进行三清，然后将手机插入电脑，即可看到K30的图标，进入手机的储存根目录，复制`xiaomi.eu_multi_HMK30_V11.0.14.0.QGHCNXM_v11-10.zip ` 进根目录，回到手机，选择`Install - Select zip `选择压缩包之后等候安装完成，整个过程可能持续五到十分钟，进入系统（此时手机不要插卡和连接Wi-Fi否则会卡谷歌验证），建议整个开机引导一直选择skip，直至进入桌面。

### 刷入magisk和安装本土模块

因为刷机后欧版MIUI并不存在中国本土化的Mi Pay（也叫小米钱包），使用magisk安装是一种较为方便并减小成砖风险的方式，故使用此方法。

进入TWRP，然后将手机插入电脑，即可看到K30的图标，进入手机的储存根目录，复制`Magisk-v20.4.zip`和`k30_mipay.zip`进入进根目录，回到手机，选择`Install - Select zip `选择压缩包之后等候安装完成，整个过程可能需要十秒左右。

此时桌面就会出现Magisk 图标，点击进入，选择`Modules`，再进入手机目录，安装`k30_mipay.zip`重启即可

此时桌面便会出现 Mi Wallet 和 GetApps 两个应用，至此，刷机完成。






## 简介

这是一份适用于 Clevo P65xHP 的 Hackintosh EFI 配置，我的机型为 HASEE Z7-KP7D1，故 HASEE Z7-KP7S1 应该也是通用的。

建议使用[黑果小兵](https://blog.daliansky.net/)镜像。

## 说明

### 硬件

机器更换了以下配置：

- 无线网卡：DW1830 BCM943602BAED（会附送一根天线接到最右侧即可）
- 固态硬盘：SAMSUNG PM961
- 显示屏：SHARP SHP1430（10.13 及以上）

**关于显卡**

从 10.13 开始更换了夏普的 SHP1430 屏幕，所以核心显卡部分会不一样，使用[黑果小兵](https://blog.daliansky.net/)镜像中较为纯净的 config.json 配合 Hackintool 驱动核显即可，需要注意的是本机型的「平台 ID」为「0x591B0006」（使用「0x591B0000」存在开机黑屏的问题）

![截屏2019-10-17上午11.29.29.png](https://i.loli.net/2019/10/17/2b9OY3jDZzKLc4G.png)

**关于声卡**

本机型号（Realtek ACL892）不需要 AppleALC 仿冒，直接将 Clover 中「Devices」下「Audio」的「Inject」设置为「28」即可声卡和麦克风同时工作。

**关于蓝牙**

DW1830 的蓝牙驱动使用以下 3 个：

- BrcmBluetoothInjector.kext
- BrcmFirmwareData.kext
- BrcmPatchRAM2.kext

将以上三个放置 EFI 中即可，不需要放置「SE」（另一种解决方案是用 BrcmFirmwareRepo.kext 取代 BrcmFirmwareData.kext 的就需要放置在 SE，不过个人并不建议）

另外，10.15 中的蓝牙使用 [OS-X-BrcmPatchRAM](https://bitbucket.org/RehabMan/os-x-brcmpatchram) 2018-05-05 版本已经不可用还会导致开机和关机卡顿，本配置使用也是用了黑果小兵镜像中的修改版，已可正常使用。

触摸板手势需设置如下快捷键  
•	1 - Applications Switch: command+"left arrow"  
•	2 - App close: command+"right arrow"  
•	3 - Launchpad: control+shift+command+L  
•	4 - Mission control: control+up  
•	5 - Dashboard: F12  
•	6 - Left Space/Full Screen apps switch: control+"left arrow"  
•	7 - Right Space/Full Screen apps switch: control+"right arrow"  
•	8 - Application window: control+shift+command+A  
•	9 - Minimize app: works as expected (command+M)  
•	10 - Toggle Full screen Switch: alt+command+F  
•	11 - Backward: alt+command+"["  
•	12 - Forward: alt+command+"]"  
•	13 - Desktop: F11  
•	14 - Notification center (keyboard shortcut): control+shift+command+N (and not command+shift+N as stated in the documentation)  
•	15 - Show Properties/Info: works as expected (command+i)  
•	16 - Hide/Show Dock: alt+command+D (but it doesn't seem to work)  
•	17 - Notification center (soft mode): doesn't work  
•	18 - Zoom reset: works as expected (command+zero)  
•	19 - Finder: alt+command+space (but I'm not shure what it should be doing, doesn't seem to work)  
•	20 - Force Quit: work as expected (alt+command+esc)  
•	21 - Right click: doesn't work as right click, instead it works as "20 - Force Quit" (alt+command+esc)  
•	22 - Middle click: doesn't work  
•	33 - should work as "F23" instead it's the real right click, but only when set to a tapping gesture  
•	34 - should work as "F24" instead it's the real middle click, but only when set to a tapping gesture  
•	35 - Left click: work as expected but only when set to a tapping gesture  

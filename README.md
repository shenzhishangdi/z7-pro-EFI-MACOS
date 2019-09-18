## 简介

这是一份适用于 Clevo P65xHP 的 Hackintosh EFI 配置，我的机型为 HASEE Z7-PRO，故 HASEE Z7-KP7S1等 应该也是通用的。

## 说明

### 硬件

机器更换了以下配置：

- 无线网卡：DW1830 BCM943602BAED（会附送一根天线接到最右侧即可）
- 固态硬盘：SAMSUNG PM961
- 显示屏：SHARP SHP1430（10.13 及以上）

**关于显卡**

从 10.13 开始更换了夏普的 SHP1430 屏幕，所以核心显卡部分会不一样，可使用[黑果小兵](https://blog.daliansky.net/)镜像中较为纯净的 `config.list` 配合 Hackintool 驱动核显会达到一个很完美的效果。

VideoProc 中检测「H264」及「HEVC」显示激活，Photoshop 中「性能」中「图形处理器设置」检测为「Intel(R) HD Graphic 630」。

**关于声卡**

此类型号（Realtek ACL892）建议将 Clover 中「Devices」下「Audio」的「Inject」设置为「31」即可声卡和麦克风同时工作。

其他使用未见异常，基本完美。

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

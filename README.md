# Hackintosh-EFI-HP_Elite_Slice
## 惠普 Elite Slice，黑苹果，EFI

### 小主机简介
这台主机外观很漂亮，可以当作一台Mac mini。  
附上[惠普官网的简介](https://support.hp.com/cn-zh/product/hp-elite-slice/12710078/document/c05276346)（或者[惠普网站另存的PDF文件](https://github.com/demon3434/Hackintosh-EFI-HP_Elite_Slice/blob/main/HP%20Elite%20Slice%20%E8%A7%84%E6%A0%BC%20_%20HP%C2%AE%E5%AE%A2%E6%88%B7%E6%94%AF%E6%8C%81.pdf)）  
![小主机外观.jpeg](https://github.com/demon3434/Hackintosh-EFI-HP_Elite_Slice/blob/main/%E5%B0%8F%E4%B8%BB%E6%9C%BA%E5%A4%96%E8%A7%82.jpeg "小主机外观")

### 软件版本
| 软件 | 版本 |
| --- | :--: |
| 系统 | macOS Monterey 12.3.1 (21E258) |
| 引导 | OpenCore v0.8.0 |

### 自选硬件
|   硬件    |   型号  |
| -------- | :----: |
| 主机 | 惠普 Elite Slice |
| CPU | Intel Core i5 6600T |
| 内存 | 英睿达 DDR4 2133 4G*2 |
| 硬盘 | 三星SM961 256GB |
| 显卡 | Intel HD Graphics 530 |
| 显示器 | DIY便携屏，4K 60Hz |
| 声卡 | Conexant CX7501 |
| 无线网卡 | DW1560 |

### 完成度
+ 核显正常驱动，2048MB显存
+ 声卡正常驱动
+ Wi-Fi、蓝牙正常驱动。Big Sur 11.6.5 (20G527) 下可以双向隔空投送
+ DP、HDMI接口能亮屏，DP口未测试
+ DP接口睡眠可唤醒，HDMI睡眠无法唤醒
+ USB定制，所有USB接口正常
+ NVMe硬盘装Win10，OC可引导Win10
+ 引导界面图形化，开机没有“duang”声音

### 缺陷
+ HDMI睡眠无法唤醒
+ 隔空投送，Monterey下只能接收，不能发送

### 备注
1. 本机器的EFI配置，参考了“[惠普400G2DM](https://github.com/demon3434/Hackintosh-EFI-HP400G2DM)”的做法。配置过程中，遇到休眠无法唤醒屏幕的问题，添加“HibernationFixup.kext”，没有解决。最终解决办法为：在PlatformInfo中，DataHub的机型选择“iMac17,1”，Generic的机型选择“Macmini8,1”，虽然看起来后者的处理器是8代i7，而本机实际是6代i5，但如果两者都设置为“iMac17,1”，休眠后唤醒后，主机运行，但屏幕无信号
2. 隔空投送问题未解决，建议不要升级Monterey
3. 由于本人使用4K显示器，故设置了UIScale=02；如果用1080P显示器，苹果logo会显得巨大，请自行到nvram的“4D1EDE05-38C7-4A6A-9CC6-4BCCA8B38C14”中，修改UIScale为01
4. 如需使用此EFI，请***务必重新三码摇号***（适合OpenCore v0.8.0的OCC编辑器已放入本仓库，[图文教程](https://blog.csdn.net/xuanxue11/article/details/107873835)）

### 效果图
![关于本机.png](https://github.com/demon3434/Hackintosh-EFI-HP400G2DM/blob/main/OpenCore%20v0.8.0%20%26%20macOS%20Big%20Sur%2011.6.5%20(20G527)%20%26%20BCM94352Z/1.%E5%85%B3%E4%BA%8E%E6%9C%AC%E6%9C%BA.png "关于本机")
![PlatformInfo机型选择.png](https://github.com/demon3434/Hackintosh-EFI-HP_Elite_Slice/blob/main/OpenCore%20v0.8.0%20%26%20macOS%20Monterey%2012.3.1%20(21E258)/2.PlatformInfo%E6%9C%BA%E5%9E%8B%E9%80%89%E6%8B%A9.png "PlatformInfo机型选择")

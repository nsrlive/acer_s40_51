# acer_s40_51
适用于宏碁蜂鸟Fun的MacOS EFI文件

FIRST of ALL：宏碁的SATA MODE默认不是AHCI模式，请先在WIN10的MSCONFIG中开启“安全引导-最小”，重启先进BIOS，在BIOS设置MAIN栏里按CTRL+S，出现SATA MODE后修改为AHCI，此时进入WIN10为安全模式，再次进入MSCONFIG关闭安全引导后重启即可安装MAC系统，一定要这样否则你会在安装时找不到SSD，直接修改AHCI而不通过WIN10的安全模式会导致无法进入WIN10系统。

1. 建立在daliansky和lietxia针对联想小新Pro和Air的EFI文件的基础上
2. 无线网卡无解
3. 声卡使用了万能驱动，可以录音但有杂音，切换耳机需要手动，另外耳机麦克风不可用，录音还是通过电脑自带的麦克风。（万能声卡是通过安装包安装到EFI文件的，如果直接使用EFI文件无法驱动可以自己再装一次，安装包已附）
4. 由于声卡目前无法通过CLOVER注入LAYOUT ID驱动，可能需要给DSDT打补丁，本人是小白也没有太多时间，有能力的可以研究下
5. 添加了有线网卡驱动
6. 摄像头已驱动
7. 蓝牙已驱动，可建立连接但无法关闭
8. 触控板已驱动，如果触控板无法使用，尝试重建缓存并重启 sudo kextcache -i /
9. 修复了每次开机提示电脑因出现问题而重新启动的bug
10. 最大的BUG：疑似关机不断电，强制关机后导致BIOS恢复默认设置，需要重新修改BIOS设置和添加引导，有能力的人可以尝试修复下

遇到屏幕字体过小，可以通过开启hidpi解决:

sudo mount -uw /

killall Finder

sh -c "$(curl -fsSL https://raw.githubusercontent.com/xzhih/one-key-hidpi/master/hidpi.sh)"

选择修复1920x1080下唤醒后bug的那个

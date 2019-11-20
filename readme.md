# 我的黑苹果Clover EFI配置
250G固态 + 1T机械组融合硬盘用起来很爽，强烈推荐！

# 主板设置
```
1. 集成外设->Super IO->串口端口A 设置为关闭(10.15.1不关闭休眠后唤醒会死机,10.14.x不会有这个问题)
2. (建议)设置为启动只允许UEFI，因为我只添加了UEFI的驱动
```

# 配置如下

| 项目        | 配置   |
| --------   | :-----  |
| CPU         | 英特尔（Intel）i5-4590 | 
|内存         |芝奇 8G DDR3 1600 x 1(内存条插在离cpu远的那根插槽)|
| 主板        |   技嘉 B85M-D2V(Rev3.0)   | 
| 显卡        |    RX560D-4G白金版(AMD Yes!免驱)    | 
|无线网卡     |无线BCM94360CD蓝牙4.0 (免驱WIFI和蓝牙)|

# 注意事项
1. 最好使用Clover Configurator 5.7或以上版本。我只尝试了10.15.1和10.12.6，我感觉10.14.x应该没问题
![机型设置](screenshots/SMBIOS.png)
2. 根据实际情况设置内存信息
3. 如果可以变量设置、机型设置、系统参数序列号啥都点下生成新的😊
4. 装完把引导参数里-v去掉，这个大家都懂得

# 优点
1. 几乎精简了所有的东西，Clover设置里几乎能去掉的都去掉了，仅仅放了6个kext
2. 修改了FakeSMC.kext支持原声电源管理AppleALC [B站参考教程](https://www.bilibili.com/video/av51049909/)
3. 可以休眠很赞

# 缺点和不足
![SSDT](screenshots/ACPI.png)
1. 没有使用SSDT来进行CPU变频，不过对台式机来说Clover自动生成的也够用了
2. 核显仅仅支持硬解H264，不支持HEVC。据说可以通过在BIOS中关闭核显，然后把机型改成iMac Pro1.1可以硬解HEVC，喜欢折腾的朋友可以试试🤣
3. 没有好好的弄USB3.0，USB传输最大速度480 Mb/秒,别人都是5 Gb/秒😅
![声卡layout-id](screenshots/devices.png)
4. 声卡前置和后置不能自动切换，你得自己在系统设置->声音->输入中自己选。有一定的几率开机会没声音(也许是AppleALC.kext驱动的问题，等更新)，重启就好😫。或者自己找一下layout-id [Github连接](https://github.com/acidanthera/AppleALC/wiki/Supported-codecs)，有耐心也可以自己编译声卡驱动，记得给我也发一份

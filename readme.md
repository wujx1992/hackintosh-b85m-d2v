# 我的黑苹果Clover EFI
1. 使用OpenCore 0.6.0正式版
2. 兼容10.15.6
3. 在Release页下载EFI

## 配置

| 项目        | 配置   |
| --------   | :-----  |
| CPU         | 英特尔（Intel）i5-4590 |
|内存         |芝奇 8G DDR3 1600 x 2|
| 主板        |   技嘉 B85M-D2V(Rev3.0)   |
| 显卡        |    RX560D-4G白金版(AMD Yes!免驱)    |
|无线网卡     |无线BCM94360CD蓝牙4.0 (免驱WIFI和蓝牙)|


## 主板设置
```
1. 集成外设->Super IO->串口端口A 设置为关闭(10.15.1不关闭休眠后唤醒会死机,10.14.x不会有这个问题)
2. 如果显卡是免驱A卡，建议在BIOS中关闭核显
```

## 使用软件
```
1. OpenCore Configurator 2.10.0.0
```
## 一些注意事项
1. 如果你的CPU核显不是hd4600或者不在乎核显加速,将设备属性设置(DeviceProperties)中PciRoot(0x0)/Pci(0x2,0x0)删除或者根据自己核显信息修改
2. 如果没有声音，请修改声卡layout-id,设备属性设置(DeviceProperties)中PciRoot(0x0)/Pci(0x1B,0x0)更改layout-id
3. 更换三码!!!
4. 想要更加完善可以参考这位大神的网站[进阶学习](https://blog.xjn819.com)

## 缺点
1. 为了保证通用性，并没有添加如何补丁
2. 没有定制USB，仅仅开启了解除USB限制，可能会睡眠即唤醒

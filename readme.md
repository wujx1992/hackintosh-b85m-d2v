# 我的黑苹果Clover EFI
1. 更新为OpenCore 0.6.3正式版
2. 兼容Mac OS 11.0.1
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
```

## 使用软件
```
1. OpenCore Configurator 2.18.0
```
## 一些注意事项
1. 如果没有声音，请修改声卡layout-id,设备属性设置(DeviceProperties)中PciRoot(0x0)/Pci(0x1B,0x0)更改layout-id
2. 更换三码!!!
3. 想要更加完善可以参考这位大神的网站[进阶学习](https://blog.xjn819.com)

## 缺点
1. 没有定制USB，仅仅开启了解除USB限制，可能会睡眠即唤醒

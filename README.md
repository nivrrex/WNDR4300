# WNDR4300
WNDR4300的OpenWRT编译固件，开启了128M空间，编译参数仅加入中文语言支持包
```bash
make image PROFILE="WNDR4300V1" PACKAGES="luci luci-i18n-base-zh-cn luci-i18n-firewall-zh-cn"
```

# 支持 OpenWrt 版本
* lede-17.01.X
* openwrt-18.06.X
* openwrt-19.07.X


# 恢复原厂固件
直接刷入原厂固件会无限重启，因为变更了分区，使用以下方式可以恢复：

1. TFTP方式刷入DD-WRT
2. SSH或Telnet方式登录路由器后，输入以下命令恢复分区
```bash
mkfs.jffs2 -o /dev/mtdblock/3 -n -b -e 0x20000
mount -t jffs2 /dev/mtdblock/3 /jffs
```
3. TFTP方式刷入原厂固件
4. 开机无限重启2-3次后，关闭电源5分钟左右
5. 打开电源，开机后恢复成原厂固件

# 备注
openwrt-21.02.0 官方固件似乎已经变更了分区，直接支持128M空间，不再更新

# WNDR4300
WNDR4300的OpenWRT编译固件，开启了128M空间，编译参数仅加入中文语言支持包
```bash
make image PROFILE="WNDR4300V1" PACKAGES="luci luci-i18n-base-zh-cn luci-i18n-firewall-zh-cn"
```
分别编译了lede-17.01.X、openwrt-18.06.X和openwrt-19.07.X等3个大版本

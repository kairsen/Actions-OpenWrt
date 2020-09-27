# Forked and Modified upon [OpenWrt-Rpi](https://github.com/SuLingGG/OpenWrt-Rpi)

* 本项目提供适配于 树莓派 4 的 OpenWrt 固件
* 包含丰富的 OpenWrt 原版 LuCI 插件及社区 LuCI 插件
* 集成绝大多数有线、无线、3G/4G 网卡驱动，无需另外安装
* 预置最新版 Clash 核心、预置 oh-my-zsh 以最大程度减少配置成本
* 预置所有 kmod ipk 软件包于固件内，预配置本地 opkg 软件源，远离 kmod 冲突
* 比较全面的 IPV6 支持，固件内置 IPV6 CLI 配置工具，可快速安装/卸载/配置 IPV6
* 每日凌晨 2:00 拉取最新 OpenWrt 源码及社区插件源码编译并提供分流下载，确保始终获得最新体验
* 提供 packages-server (包含 WEB 服务器的软件包归档)，可在 Windows 下快速建立局域网软件源
* 对于高级用户，提供 OpenWrt Image Builder、OpenWrt SDK、OpenWrt Tool Chain、dl 归档文件

## 鸣谢：

P3TERX/Actions-OpenWrt (本项目基于此项目):

https://github.com/P3TERX/Actions-OpenWrt

OpenWrt Source Repository:

https://github.com/openwrt/openwrt/

Lean's OpenWrt source:

https://github.com/coolsnowwolf/lede

CTCGFW's Team:

https://github.com/project-openwrt

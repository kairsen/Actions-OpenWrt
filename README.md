# Forked and Modified upon [Action-OpenWrt-Plus](https://github.com/SuLingGG/Action-OpenWrt-Rpi)


## 写在前面

本项目基本保留了 [P3TERX/Actions-OpenWrt](https://github.com/P3TERX/Actions-OpenWrt) 项目的特性，

建议首先阅读 P3Terx 大佬的云编译教程后再使用本项目:

[使用 GitHub Actions 云编译 OpenWrt](https://p3terx.com/archives/build-openwrt-with-github-actions.html)

在此之上，本项目还添加了以下特性:

1. 提供基于 Lean 大 / 官方 OpenWrt snapshot / Project-OpenWrt 三种源码的示例文件模板；
2. 添加了若干第三方优秀的 OpenWrt 软件包项目 (添加了哪些软件包可在 DIY 脚本文件中查看)；
3. 支持一键编译所有 kmod 并集成进固件，在从软件源安装 ipk 时，所有 komd 软件包将从本地获取 (对某些不被 OpenWrt 官方支持的设备很有用)，从此摆脱 komd 冲突问题。并可根据不同平台智能修改软件源，无需进行额外设置；
4. 支持固件编译完成后生成 package-server，方便在 Windows 下建立本地软件源 (双击即用)，对不方便集成所有 kmod 进固件的小 ROM 设备来说很有用；
5. 对于官方 OpenWrt Snapshot 源码，可自动转换第三方软件包源码翻译以适配 Luci 19.07，并可自动移除二进制文件的 upx 压缩 (提高性能)；

注:

1. 本项目已集成了 Lienol 的软件包 Feeds，故无需手动添加；
2. 本项目默认保留了 luci-app-ssr-plus 和 luci-app-passwall，故无需做其他处理。

## 触发方式

本项目采用 Star 触发方式:

此外，Github Action 支持多种触发方式，比如定时触发、Star 触发等，详细操作方法请前往 [P3terx 大佬的博客](https://p3terx.com/archives/build-openwrt-with-github-actions.html) 中查看~

## 变量说明

可修改本项目 .gitbub/workflows 文件夹下存放 Github Action 工作流配置文件中的 env 一节来实现相应功能:

```
REPO_URL: # OpenWrt 源码地址
REPO_BRANCH: # OpenWrt 源码分支
CONFIG_FILE: # config 配置文件所在路径
DIY_SH: # DIY 脚本所在路径
FEEDS_CONF: # feeds.conf.default 在项目中的文件名
SSH_ACTIONS: # 是否使用 “云 menuconfig”
KMODS_IN_FIRMWARE: # 是否集成 kmod 软件包进固件(小 ROM 机器慎用)
UPLOAD_BIN_DIR: # 是否上传整个 bin 文件夹至 Github Action (包含固件/软件包/其他文件)
UPLOAD_FIRMWARE: # 功能同 UPLOAD_BIN_DIR 但未包含软件包
UPLOAD_COWTRANSFER: # 是否上传固件至奶牛快传
UPLOAD_WETRANSFER: # 是否上传固件至 WeTransfer
TZ: # 时区设置
```

## 目录说明


```
Action-OpenWrt-Rpi
├── .github
│   └── workflows  # Github Action 工作流配置文件夹
├── config # .config 文件存放文件夹
├── scripts # 项目脚本文件夹
│  ├── convert-translation.sh # 第三方软件包翻译转换脚本 (用于官方版 OpenWrt )
│  ├── enable-rpi4-wifi.sh # 用于修复树莓派 4 的 WiFi 问题 (编译树莓派的官方版 OpenWrt 需要取消 yml 文件中 Load Custom Configuration 部分的注释)
│  ├── lean-openwrt-rpi4.sh # Lean 版源码应用的 DIY 脚本文件
│  ├── offical-openwrt.sh # 官方 OpenWrt Snapshot 源码应用的 DIY 脚本文件
│  ├── project-openwrt.sh # Project-OpenWrt 版源码应用的 DIY 脚本文件
│  └── remove-upx.sh # 移除二进制文件中的 upx 压缩，以提高性能 (用于官方版 OpenWrt )
├── template 提供 Lean / 官方 OpenWrt Snapshot / Project-OpenWrt 三种 config 配置文件模板
├── LICENSE # 项目许可证文件
└── README.md # 项目描述文件
```

## 鸣谢

Action-OpenWrt-Plus (本项目基于此项目):

<https://github.com/SuLingGG/Action-OpenWrt-Plus>

P3TERX/Actions-OpenWrt:

<https://github.com/P3TERX/Actions-OpenWrt>

OpenWrt Source Repository:

<https://github.com/openwrt/openwrt/>

Lean's OpenWrt source:

<https://github.com/coolsnowwolf/lede>

CTCGFW's Team:

<https://github.com/project-openwrt>

# 锐捷客户端认证

锐捷客户端认证，可用OpenWrt路由器安装MentoHust插件或MiniEAP插件登录拨号上网



## 1.MentoHust

### 1.1插件下载
- [链接1](https://github.com/KyleRicardo/MentoHUST-OpenWrt-ipk) 作者：KyleRicardo [个人主页](https://github.com/KyleRicardo)
- [链接2](https://www.right.com.cn/forum/thread-196317-1-1.html) 作者：bishuiwuhen [个人主页](https://www.right.com.cn/forum/space-uid-249539.html)
- [链接3](https://github.com/sbwml/luci-app-mentohust) 作者：sbwml [个人主页](https://github.com/sbwml)

---

### 1.2MentoHust 介绍

#### 1.2.1前置和安装包的说明

- 前置依赖：libpcap
- 推荐安装ttyd：包含libpcap，终端在网页就能执行命令

```
luci-app-ttyd.ipk 本体
luci-i18n-ttyd-zh-cn 汉化

luci-app-mentohust.ipk 本体
luci-i18n-mentohust-zh-cn.ipk 中文操作界面（可选）
```

#### 1.2.2MentoHust 如何使用命令操作

```

欢迎使用MentoHUST       版本: 0.3.1
Copyright (C) 2009-2010 HustMoon Studio
人到华中大，有甜亦有辣。明德厚学地，求是创新家。
Bug report to http://code.google.com/p/mentohust/issues/list

用法:   mentohust [-选项][参数]
选项:   -h 显示本帮助信息
        -k -k(退出程序) 其他(重启程序)
        -w 保存参数到配置文件
        -u 用户名
        -p 密码
        -n 网卡名
        -i IP[默认本机IP]
        -m 子网掩码[默认本机掩码]
        -g 网关[默认0.0.0.0]
        -s DNS[默认0.0.0.0]
        -o Ping主机[默认0.0.0.0，表示关闭该功能]
        -t 认证超时(秒)[默认8]
        -e 响应间隔(秒)[默认30]
        -r 失败等待(秒)[默认15]
        -l 允许失败次数[默认0，表示无限制]
        -a 组播地址: 0(标准) 1(锐捷) 2(赛尔) [默认0]
        -d DHCP方式: 0(不使用) 1(二次认证) 2(认证后) 3(认证前) [默认0]
        -b 是否后台运行: 0(否) 1(是，关闭输出) 2(是，保留输出) 3(是，输出到文件) [默认0]
        -y 是否显示通知: 0(否) 1~20(是) [默认5]
        -v 客户端版本号[默认0.00表示兼容xrgsu]
        -f 自定义数据文件[默认不使用]
        -c DHCP脚本[默认udhcpc -i]
例如:   mentohust -uusername -ppassword -neth0 -i192.168.0.1 -m255.255.255.0 -g0.0.0.0 -s0.0.0.0 -o0.0.0.0 -t8 -e30 -r15 -a0 -d1 -b0 -v4.10 -fdefault.mpf -cudhcpc -i
注意：使用时请确保是以root权限运行！

例子：
账号是123456789，密码是88888888，wan口网卡是eth0
在网页终端（ttyd）或ssh登陆后的拨号命令可以是
mentohust -u123456789 -p88888888 -neth0 -a1 -b1 -w
参数应当根据实际情况灵活调整
```

---

#### 1.2.3MentoHust 相关参考链接
- [锐捷多拨](https://github.com/tkkcc/mentohust) 作者：tkkcc [个人主页](https://github.com/tkkcc)
- [支持锐捷认证与IPv6的路由器配置指南](https://github.com/KumaTea/MentoHUST-SYSU-Guide) 作者：KumaTea [个人主页](https://github.com/KumaTea)
```
MentoHUST-SYSU-Guide

2021年更新
mentohust 已有十余年历史，部分功能可能已经不可用于当前系统。

例如，OpenWrt 更新到较新版本后，mentohust 出现了每隔数分钟掉线一次的异常情况，是否为普遍现象未明。

因此，强烈建议换用 minieap (Forked from updateing/minieap， OpenWrt package， OpenWrt index) 。

移植方式没有太多改变，十分简单，然而性能及稳定性大幅提升。
```
- [校园网网页认证环境下基于OpenWRT的路由器选型与解决方案（锐捷）](https://zhuanlan.zhihu.com/p/953514481) 作者：全能全知者 [个人主页](https://www.zhihu.com/people/quan-neng-quan-zhi-zhe-11)
- [MentoHust在Google的源码](https://code.google.com/archive/p/mentohust/)（需要科学上网）

## 2.MiniEAP

### 2.1插件下载
- [链接1](https://github.com/updateing/minieap) 作者：updateing [个人主页](https://github.com/updateing)

```
需自行编译
```

- [链接2](https://github.com/AutoCONFIG/minieap-openwrt) 作者：AutoCONFIG [个人主页](https://github.com/AutoCONFIG)

```
仅有部分架构，其余仍需自行编译

Glibc：采用glibc运行库
Musl：采用musl运行库
默认下载musl版本

aarch64：兼容全部aarch64架构（Rockchip/IPQ/部分MediaTek等ARMv8及后续64位Arm处理器）
mipsel: 兼容全部mipsel架构（MediaTek MT7620/MT7621/MT7628等）
x86_64: 兼容x86_64处理器（amd64）
```

- [链接3](https://github.com/LightWind1/minieap) 作者：LightWind1 [个人主页](https://github.com/LightWind1)

```
需自行编译
```

- [链接4](https://www.right.com.cn/forum/thread-4106567-1-1.html) 作者：你家臭狗屎 [个人主页](https://www.right.com.cn/forum/space-uid-682003.html)

```
注：可能与链接3为同一作者，需自行编译

这里不提供MiniEAP图形配置界面支持，感谢理解。关于MiniEAP图形配置，目前的几乎所有的MiniEAP图形配置工具都可以与之完美兼容，可以自行编译或者找相关帖子解决。

如有问题，欢迎恩山私信互动或者B站私信

目前支持平台：x86_generic/x86-64/mt76x8/mt7621/mt7620/armv8(aarch64)/armv7/ipq60xx/bcm53xx

声明：承诺没有加入任何后门

如果这里没有支持您的设备，欢迎自己编译，也可以留言反馈，后续会更新上（可能要等一到两天）
```  

- [链接5](https://github.com/kongfl888/openwrt-minieap) 作者：kongfl888 [个人主页](https://github.com/kongfl888)

```
minieap for OpenWrt
需自行编译
```

### 2.2MiniEAP 介绍

#### 2.2.1前置和安装包的说明

- 大部分依赖系统已预装
- 可能需要 libdl

```
luci-app-minieap Web界面插件
依赖包含
luci-base
luci-lib-jsonc
luci-compat
```

#### 2.2.2MiniEAP 详细介绍

```
MiniEAP
这是一个实现了标准 EAP-MD5-Challenge 算法的 EAP 客户端，支持通过插件来修改标准数据包以通过特殊服务端的认证。目前带有一个实现锐捷 v3 (v4) 算法的插件。本插件的认证算法来自 Hu Yunrui 的 MentoHUST 项目，在此表示感谢！

特性
通用特性
模块化设计 可在 config.mk 中直观选择所需模块。如需添加模块，直接复制一份现有的 minieap.mk 并按需修改即可。

网络帧收发由插件模块完成 可根据平台差异使用不同的插件。目前提供 libpcap 和 Raw Socket 两种插件。前者兼容性好，但需链接 libpcap，体积较大；后者不需额外动态库，但只能在 Linux 上使用。可选择任意个模块参与编译，但运行时只能选取其中之一来使用。

数据包修改同样由插件完成 可以在不修改主要认证流程的情况下适配各种环境。可以启用多个插件，也可将一个插件启用多次。程序会让标准 EAP 算法生成的数据包按照命令行中 --module 参数的顺序让数据包流经这些插件。目前提供一个锐捷 v3 认证算法插件和一个打印流经的数据包大小的示例插件。

所有数据包生成逻辑均采用结构体对缓冲区进行读写，拒绝 magic number 从我做起！

锐捷插件特性
认证算法来自 Hu Yunrui 的 MentoHUST 项目
相比原本的 MentoHUST v3 (v4) 实现，能够支持更多的字段，更容易通过验证。
二次认证时，支持位于修改常规字段以外的 IP 地址、网关、主 DNS 等信息，更容易通过验证。
所有字段都通过收集来的信息直接构造而成，不采用修改数据包模板的方式，避免各场景下偏移量不同导致的认证失败或数据包无法解析问题。
所有字段生成逻辑均采用结构体对缓冲区进行读写，拒绝 magic number 从我做起 x2！
字段中所用到的常量都有宏定义来注明其含义，定长字段的长度也通过宏定义声明，拒绝 magic number 从我做起 x3！
支持通过命令行来附加新的字段，也可覆盖程序生成的字段。可以在不修改代码的情况下进行适配。
整体程序的内存占用比 MentoHUST 小约 78%（在 256 MB 内存的 ARMv7 平台上测试）。
编译
编辑 config.mk，选择所需要的模块。 在以 if_impl 开头的模块中，Linux 环境建议只选择 if_impl_sockraw 模块，其他平台建议只选择 if_impl_libpcap 模块。 在以 packet_plugin 开头的模块中，请按需要选择。 注：若选择 if_impl_libpcap，将自动添加 -lpcap 选项。

本程序需要使用 getifaddrs。 如果您的平台没有提供此函数，可自行寻找需要的实现，并在 include/ 中添加 ifaddrs.h，在 util/ifaddrs/ 目录中添加必要的 C 文件，最后在 config.mk 中选中 ifaddrs 模块即可。

如果服务器消息乱码，可将 config.mk 中的 ENABLE_ICONV 置为 1. 若平台未提供iconv相关函数，需手动链接 libiconv 库。

执行 make 即可在根目录下编译出可执行文件。

注1：如需要交叉编译，可参考 config.mk 中的示例。

注2：如需要链接外部库，请在 COMMON_CFLAGS、COMMON_LDFLAGS、LIBS 中加入合适的 -I -L -l 等选项。

运行
具体选项请参阅 minieap -h 的输出。这里列出必需的几个选项。

-u 用户名
-p 密码
-n 网卡名
默认的网络帧收发模块是 if_impl_sockraw。如果要使用其他模块，如 libpcap，则必须指定 --if-impl libpcap。

默认不使用任何数据包修改器，将只会发送单纯的标准 EAP 数据包。 如需使用锐捷认证，则必须指定 --module rjv3。 可以指定多个 --module 参数，程序会按参数的顺序让数据包流经这些插件。

参数格式支持如下几种：

-u myname
--username myname
注意：暂不支持 -umyname 这种形式，这在插件的命令行解析中将带来错误。

示例：在 en0 上使用锐捷认证，以 libpcap 作为网络帧收发模块，并且在数据包流经锐捷认证插件前后都打印出数据包的大小：

minieap -u 201000000 -p 15000000000 -n en0 --module printer --module rjv3 --module printer --if-impl libpcap
注意事项
本项目刚成立不久，虽然有过测试，但无法保证高可靠性。欢迎大家提出意见，谢谢！

非常感谢 HustMoon 工作室以及 Hu Yunrui 同学对这个领域做出的贡献！
```

```
MiniEAP命令使用方式与MentoHust类似，但有所区别！
```

#### 2.2.3MiniEAP 相关参考链接
- [LuCI for minieap](https://github.com/kongfl888/luci-app-minieap) 作者：kongfl888 [个人主页](https://github.com/kongfl888)

```
OpenWrt/LEDE LuCI for minieap
！锐捷服务名为中文时无法使用，请等待自定义配置文件功能启用！
本软件包是 minieap 的 LuCI界面
```

-[编译并使用 minieap 实现路由器锐捷认证上网](https://www.cnblogs.com/Undefined443/p/18375072) 作者：Undefined443 [个人主页](https://www.cnblogs.com/Undefined443)




















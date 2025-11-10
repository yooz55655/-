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
- 
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
注：可能与链接3为同一作者

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

#### 2.2.3MiniEAP 相关参考链接
- [LuCI for minieap](https://github.com/kongfl888/luci-app-minieap) 作者：kongfl888 [个人主页](https://github.com/kongfl888)

```
OpenWrt/LEDE LuCI for minieap
！锐捷服务名为中文时无法使用，请等待自定义配置文件功能启用！
本软件包是 minieap 的 LuCI界面
```






















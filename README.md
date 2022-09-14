# v2ray-agent
xray 一键安装脚本
1.八合一共存脚本+伪装站点
特性
支持Xray-core[XTLS]、v2ray-core
支持VLESS/Trojan前置[VLESS XTLS -> Trojan XTLS]、[Trojan XTLS -> VLESS XTLS]
支持不同核心之间的配置文件互相读取
支持 VLESS/VMess/trojan 协议
支持Debian、Ubuntu、Centos系统，支持主流的cpu架构。
支持任意组合安装、支持多用户管理、支持DNS流媒体解锁、支持添加多端口、支持任意门解锁Netflix
支持卸载后保留tls证书
支持IPv6，IPv6注意事项
支持WARP分流、IPv6分流
支持BT下载管理、日志管理、域名黑名单管理、核心管理、伪装站点管理
支持自定义证书安装
支持的安装类型
VLESS+TCP+TLS
VLESS+TCP+xtls-rprx-direct【推荐】
VLESS+gRPC+TLS【支持CDN、IPv6、延迟低】
VLESS+WS+TLS【支持CDN、IPv6】
Trojan+TCP+TLS【推荐】
Trojan+TCP+xtls-rprx-direct【推荐】
Trojan+gRPC+TLS【支持CDN、IPv6、延迟低】
VMess+WS+TLS【支持CDN、IPv6】
线路推荐
CN2 GIA
上海CN2+HK
AS9929
AS4837
联通日本软银
联通+台湾TFN
联通+NTT
广移/珠移+HKIX/CMI/NTT
广移/CN2+Cloudflare+全球
广移/CN2/南联+香港AZ+全球
中转+cloudflare+落地机【可拉全球】
组合推荐
中转/gia/AS4837/AS9929 ---> VLESS+TCP+TLS/XTLS、Trojan
移动宽带 ---> VMESS+WS+TLS/VLESS+WS+TLS/VLESS+gRPC+TLS/Trojan+gRPC+TLS + Cloudflare
cloudflare-> VLESS+gRPC+TLS/Trojan+gRPC+TLS[多路复用、延迟低]
注意事项
修改Cloudflare->SSL/TLS->Overview->Full
Cloudflare ---> A记录解析的云朵必须为灰色【如非灰色，会影响到定时任务自动续签证书】
如用CDN又同时使用直连，关闭云朵+自选IP，自选IP参考上方的Cloudflare 优化方案
使用纯净系统安装，如使用其他脚本安装过并且自己无法修改错误，请重新安装系统后再次尝试安装
wget: command not found [这里需要自己手动安装下wget] ，如未使用过Linux，点击查看安装教程
不支持非root账户
如发现Nginx相关问题，请卸载掉自编译的nginx或者重新安装系统
为了节约时间，反馈请带上详细截图或者按照模版规范，无截图或者不按照规范的issue会被直接关闭
不推荐GCP用户使用
不推荐使用Centos以及低版本的系统，如果Centos安装失败，请切换至Debian10重新尝试，脚本不再支持Centos6、Ubuntu 16.x
如有使用不明白的地方请先查看脚本使用指南
Oracle Cloud有一个额外的防火墙，需要手动设置
Oracle Cloud仅支持Ubuntu
如果使用gRPC通过cloudflare转发,需要在cloudflare设置允许gRPC，路径：cloudflare Network->gRPC
gRPC目前处于测试阶段，可能对你使用的客户端不兼容，如不能使用请忽略
低版本脚本升级高版本时无法启动问题，请点击此链接查看解决方案
脚本使用指南、脚本目录
捐赠
您可以使用我的AFF进行购买VPS捐赠-博客

您可以使用我的AFF进行购买VPS捐赠-Github

支持通过虚拟币向我捐赠

安装脚本
支持快捷方式启动，安装完毕后，shell输入【vasma】即可打开脚本，脚本执行路径[/etc/v2ray-agent/install.sh]

Latest Version【推荐】

wget -P /root -N --no-check-certificate "https://raw.githubusercontent.com/mack-a/v2ray-agent/master/install.sh" && chmod 700 /root/install.sh && /root/install.sh

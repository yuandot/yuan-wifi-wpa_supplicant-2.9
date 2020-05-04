参考链接：

* [w1.fi](http://w1.fi/)
* [关于 Linux 无线局域网支持](https://www.hpl.hp.com/personal/Jean_Tourrilhes/Linux/Wireless.html)
* [WPA Supplicant 开发者文档](http://w1.fi/wpa_supplicant/devel/)
* [版本记录](http://w1.fi/releases.html)
* [版本记录详情](http://w1.fi/releases.html)
* [源码下载链接](http://w1.fi/releases/)
* [邮件列表](http://lists.infradead.org/mailman/listinfo/hostap)
* [其他人提交的修改](http://lists.infradead.org/pipermail/hostap/)
* [git 仓库的 web 接口](http://w1.fi/cgit)
* [git 访问](http://w1.fi/cvs.html)
* [安全更新](http://w1.fi/security/)
* [WiFi 联盟](https://www.wi-fi.org/)
* [IEEE 802](http://www.ieee802.org/)

## [Host AP](http://w1.fi/hostap-driver.html)

Host AP 是基于 Intersil's Prism2/2.5.3 芯片组的 Linux 驱动。该驱动支持所谓的 HOST AP 模式，也就是主机电脑关注 IEEE 802.11 管理功能，作为一个 AP 热点的角色。不需要无线网卡使用特定的固件。另外，该驱动也支持正常的 sta 操作在 BSS 和 IBSS 网络。当使用伴生工具，wpa_supplicant（WPA/RSN Supplicant） 和 hostapd（WPA/RSN Authenticator） 时，也会支持 WPA 和 WPA2。所有这些工具可以支持桌面或手持电脑和嵌入式系统。

Prism2 芯片组的 sta 固件支持所谓的 Host AP 模式，这个固件关注时间关键任务例如 beacon 发送和帧确认，其他的管理任务留给主机电脑驱动（也就是网卡固件处理时间严格的任务，其他的任务留给电脑驱动）。驱动实现需要初始化和配置基于 Prism2 网卡，发送接收帧，统计数据的基本功能。另外，也实现了下列 802.11 功能：authentication (and deauthentication), association (reassociation, and disassociation), data transmission between two wireless stations, power saving (PS) mode signaling and frame buffering for PS stations。该驱动还有很多关于开发调试，研究 802.11环境（访问硬件配置记录，IO 寄存器，802.11 帧头）的特性。

当使用一个用户守护进程时，Host AP驱动和 hostapd 的组合包含额外的特性。例如 IEEE 802.1X and dynamic WEP rekeying, RADIUS Accounting, RADIUS-based ACL for IEEE 802.11 authentication, minimal IAPP (IEEE 802.11f), WPA, IEEE 802.11i/RSN/WPA2.

Host AP 驱动在 Linux v2.6.14 内核版本中添加入了主内核树，内核树中的版本应该替代外部 hostap 驱动板。外部版本仅仅用于旧的内核版本，未来的开发将会在主内核树中。

## [hostapd](http://w1.fi/hostapd/)

热点 AP，暂时不予讨论

## [wpa_supplicant](http://w1.fi/wpa_supplicant/)

x86 平台最小代码空间 50kB （WPA/WPA2-Personal）和 130kB （WPA/WPA2-Enterprise）到 450kB。

更多关于 [EAP 方法和测试](http://w1.fi/cgit/hostap/plain/wpa_supplicant/eap_testing.txt)

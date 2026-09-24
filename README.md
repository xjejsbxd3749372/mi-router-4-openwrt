# 小米路由器 4 (Mi Router 4) OpenWrt 自动编译固件

基于 [coolsnowwolf/lede](https://github.com/coolsnowwolf/lede)（OpenWrt 19.07）的云端自动编译仓库。

## 目标设备

- 设备：Xiaomi Mi Router 4（小米路由器 4）
- 架构：ramips / mt7621（mipsel_24kc）
- 内核：Linux 4.14

## 内置功能

- LuCI 中文界面（zh-cn）
- **PassWall / SSR-Plus**：SS / SSR / **V2Ray（VLESS + WS + TLS）** / Trojan / Socks5
- V2Ray 4.23.1（支持 VLESS、WebSocket 传输、TLS 加密）
- Trojan、Kcptun、Redsocks2、Shadowsocks、simple-obfs、v2ray-plugin
- TCP BBR 加速、dnsmasq-full、TProxy 透明代理支持

> VLESS + WS + TLS 通过「服务 → 科学上网（SSR Plus+）」里的 V2Ray 节点类型配置：
> 协议选 `VLESS`，传输选 `WebSocket`，TLS 开启即可。

## 云端编译（GitHub Actions）

1. Fork 或新建本仓库
2. 修改 `.config` 定制固件（如需）
3. Push 到 `main` 分支，或手动触发 `workflow_dispatch`
4. 编译完成后在 Actions 页面下载 `OpenWrt-xiaomi-mir4` 产物

## 本地修改 `.config` 后再上传

直接编辑仓库根目录的 `.config` 文件即可，改动会随提交在云端生效。

## 默认信息

- 默认 IP：`192.168.1.1`
- 默认用户：`root` / 密码：`password`

## 刷入方式

编译产物为 `sysupgrade` 固件，通过不死 Boot（breed）或 SSH `sysupgrade` 刷入。
刷机有风险，请提前备份并确认闪存/分区布局。

## 免责声明

本项目仅用于学习与交流，请遵守当地法律法规，勿用于任何违法违规用途。

#
# Copyright (C) 2026 OpenClaw
#
# Xray-core precompiled binary package for mipsel_24kc (Xiaomi Mi Router 4)
#
# This is free software, licensed under the Mozilla Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=xray
PKG_VERSION:=1.8.23
PKG_RELEASE:=1

PKG_SOURCE:=Xray-linux-mips32le.zip
PKG_SOURCE_URL:=https://github.com/XTLS/Xray-core/releases/download/v$(PKG_VERSION)/
PKG_HASH:=skip

PKG_LICENSE:=MPL-2.0

include $(INCLUDE_DIR)/package.mk

define Package/xray
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=Web Servers/Proxies
  TITLE:=Xray core (VLESS / XTLS / VMess / Trojan)
  URL:=https://github.com/XTLS/Xray-core
  DEPENDS:=+ca-certificates
endef

define Package/xray/description
  Xray-core is a platform for building proxies to bypass network restrictions.
  It supports VLESS, VMess, Trojan, Shadowsocks, WebSocket, TLS, XTLS and more.
endef

define Build/Prepare
	unzip -j -o $(DL_DIR)/$(PKG_SOURCE) -d $(PKG_BUILD_DIR)/
endef

define Build/Compile
	true
endef

define Package/xray/install
	$(INSTALL_DIR) $(1)/usr/bin/v2ray
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/xray_softfloat $(1)/usr/bin/v2ray/v2ray
endef

$(eval $(call BuildPackage,xray))

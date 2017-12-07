#
# Copyright (C) 2011-2015 Entware
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ziproxy
PKG_VERSION:=3.3.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=@SF/ziproxy
PKG_MD5SUM:=9771bd4fe434b4722b0704183a9489eb

include $(INCLUDE_DIR)/package.mk

define Package/ziproxy
	SECTION:=net
	CATEGORY:=Network
	SUBMENU:=Web Servers/Proxies
	DEPENDS:=+giflib +libjpeg +libpng +zlib +libsasl2 +libpthread
	TITLE:=compressing HTTP proxy server
	URL:=http://ziproxy.sourceforge.net
	MAINTAINER:=Entware team, old.entware.net
endef

define Package/ziproxy/description
 ziproxy is a forwarding, non-caching and compressing HTTP proxy server.
 Basically it squeezes images by converting them to lower quality JPEGs
 and compresses (gzip) HTML and other text-like data.
endef

define Package/ziproxy/conffiles
/etc/xinetd.d/ziproxy
/etc/ziproxy/ziproxy.conf
/etc/ziproxy/bo_exception.list
/etc/ziproxy/change_tos.list
/etc/ziproxy/deny.list
/etc/ziproxy/http.passwd
/etc/ziproxy/noprocess.list
/etc/ziproxy/replace.list
/etc/ziproxy/replace_ct.list
/etc/ziproxy/sasl/ziproxy.conf
endef

CONFIGURE_ARGS += \
	--without-jasper \
#	--exec-prefix=/opt \
#	--prefix=/opt \
	--with-cfgfile=/etc/ziproxy/ziproxy.conf

define Package/ziproxy/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) \
		$(PKG_BUILD_DIR)/src/ziproxy \
		$(PKG_BUILD_DIR)/src/tools/ziproxylogtool \
		$(PKG_BUILD_DIR)/src/tools/ziproxy_genhtml_stats.sh $(1)/usr/bin/
	$(INSTALL_DIR) $(1)/etc/xinetd.d
	$(INSTALL_CONF) $(PKG_BUILD_DIR)/etc/xinetd.d/ziproxy $(1)/etc/xinetd.d/ziproxy
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/S25ziproxy $(1)/etc/init.d/S25ziproxy
	$(INSTALL_DIR) $(1)/etc/ziproxy
	$(INSTALL_CONF) \
		$(PKG_BUILD_DIR)/etc/ziproxy/ziproxy.conf \
		$(PKG_BUILD_DIR)/etc/ziproxy/http.passwd \
		$(PKG_BUILD_DIR)/etc/ziproxy/bo_exception.list \
		$(PKG_BUILD_DIR)/etc/ziproxy/change_tos.list \
		$(PKG_BUILD_DIR)/etc/ziproxy/deny.list \
		$(PKG_BUILD_DIR)/etc/ziproxy/noprocess.list \
		$(PKG_BUILD_DIR)/etc/ziproxy/replace.list \
		$(PKG_BUILD_DIR)/etc/ziproxy/replace_ct.list \
			$(1)/etc/ziproxy/
	$(INSTALL_DIR) $(1)/etc/ziproxy/sasl
	$(INSTALL_CONF) $(PKG_BUILD_DIR)/etc/ziproxy/sasl/ziproxy.conf $(1)/etc/ziproxy/sasl/
	$(INSTALL_DIR) $(1)/usr/var/log/ziproxy
	$(INSTALL_DIR) $(1)/usr/var/run
endef

$(eval $(call BuildPackage,ziproxy))

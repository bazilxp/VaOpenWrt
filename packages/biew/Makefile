#
# Copyright (C) 2006-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=biew
PKG_VERSION:=6.1.0
PKG_RELEASE:=1
https://sourceforge.net/projects/beye/files/biew/6.1.0/biew-610-src.tar.bz2
PKG_SOURCE:=biew-610-src.tar.bz2
PKG_SOURCE_URL:=https://sourceforge.net/projects/beye/files/biew/$(PKG_VERSION)/
##PKG_MD5SUM:=7ffe1c7cdc3233e1e0c4b502df253974
PKG_BUILD_DIR:=$(BUILD_DIR)/biew-610/
PKG_CHECK_FORMAT_SECURITY:=n
PKG_USE_MIPS16:=0

include $(INCLUDE_DIR)/package.mk

define Package/biew
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=BYE hex editor
  DEPENDS:= +libncurses
  URL:=https://sourceforge.net/projects/beye/
endef

define Package/biew/description
  Biew hex editor
endef


#			-with-extraincdir=$(STAGING_DIR)/usr/lib/libiconv-full/include \
#			-with-extralibdir=$(STAGING_DIR)/usr/lib/libiconv-full/lib \

define Build/Configure
	( cd $(PKG_BUILD_DIR); \
		./configure --prefix=/usr \
			--target-arch=generic --target-system=linux --disable-iconv --enable-curses  \
			CFLAGS=$(TARGET_CFLAGS) \
			LDFLAGS=$(TARGET_LDFLAGS)  \
	)
endef

define Package/biew/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/biew $(1)/usr/bin/
endef

$(eval $(call BuildPackage,biew))


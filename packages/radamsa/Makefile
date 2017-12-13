#
# Copyright (C) 2011-2015 Entware
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
# The newer version requires too many dependencies

include $(TOPDIR)/rules.mk

PKG_NAME:=radamsa
PKG_VERSION:=20170717
PKG_RELEASE:=1

PKG_REV:=91c913209a86f0a1e242e30e1bbac3a636e8a648
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/aoh/radamsa.git
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_USE_MIPS16:=0

include $(INCLUDE_DIR)/package.mk

define Package/radamsa
	SECTION:=net
	CATEGORY:=Network
	TITLE:=Radamsa Fuzzing tool 
	URL:=https://github.com/aoh/radamsa.git
	MAINTAINER:= Vasyl Yevstygnyeyev <yevstygn@yandex.ru>
endef

define Package/radamsa/description
  Fuzzing tool
endef


define Package/radamsa/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_BUILD_DIR)/bin/radamsa $(1)/usr/bin
endef

$(eval $(call BuildPackage,radamsa))

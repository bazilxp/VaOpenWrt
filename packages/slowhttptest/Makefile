#
# Copyright (C) 2006-2017 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=slowhttptest
PKG_VERSION:=1.7
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/shekyan/slowhttptest.git
PKG_SOURCE_VERSION:=28a863e3128df1a5d717240cbc07eec8f6f352dd
#PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.xz
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION)
PKG_LICENSE:=GPLv3
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=Vasily Yevstygnyeyev <yevstygn@yandex.ru>


include $(INCLUDE_DIR)/package.mk
EXTRA_CXXFLAGS+= -std=c++11
define Package/slowhttptest
    SECTION:=utils
    CATEGORY:=Utilities
    DEPENDS:=+libopenssl +libstdcpp
    TITLE:=slowhttptest
    URL:=https://github.com/shekyan/slowhttptest/wiki
endef

define Package/slowhttptest/description
	SlowHTTPTest is a highly configurable tool that simulates 
	some Application Layer Denial of Service attacks by prolonging HTTP connections in different ways.
endef


define Package/slowhttptest/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_BUILD_DIR)/src/slowhttptest $(1)/usr/bin
endef

$(eval $(call BuildPackage,slowhttptest))
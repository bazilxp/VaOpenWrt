#
# Copyright (C) 2006-2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ccache
PKG_VERSION:=3.3.4
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://www.samba.org/ftp/ccache/
PKG_MD5SUM:=61326f1edac7cd211a7018458dfe2d86


include $(INCLUDE_DIR)/package.mk

define Package/ccache
  SECTION:=utils
  CATEGORY:=Utilities
  DEPENDS:=+zlib
  TITLE:=ccache
  URL:=https://www.samba.org/ftp/ccache/
endef

define Package/ccache/description
	ccache is a compiler cache. It speeds up recompilation.
endef


define Package/ccache/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_BUILD_DIR)/ccache $(1)/usr/bin
endef

$(eval $(call BuildPackage,ccache))

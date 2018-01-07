#
# Copyright (C) 2006-2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=par2cmdline
PKG_VERSION:=0.8.0
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/Parchive/par2cmdline/releases/download/v$(PKG_VERSION)/
#PKG_MD5SUM:=61326f1edac7cd211a7018458dfe2d86


include $(INCLUDE_DIR)/package.mk

define Package/par2cmdline
  SECTION:=utils
  CATEGORY:=Utilities
  DEPENDS:= +libstdcpp
  TITLE:=par2cmdline
  URL:=https://github.com/Parchive/par2cmdline
endef

define Package/par2cmdline/description
   par2cmdline is a program for creating and using PAR2 files to detect 
  damage in data files and repair them if necessary. It can be used with any kind of file.
endef


define Package/par2cmdline/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_BUILD_DIR)/par2 $(1)/usr/bin
endef

$(eval $(call BuildPackage,par2cmdline))

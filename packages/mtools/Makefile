#
# Copyright (C) 2006-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=mtools
PKG_VERSION:=4.0.18
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=@GNU/$(PKG_NAME)
#PKG_MD5SUM:=7ffe1c7cdc3233e1e0c4b502df253974

include $(INCLUDE_DIR)/package.mk

define Package/mtools
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=GNU mtools
  URL:=http://ftp.gnu.org/gnu/mtools
endef

define Package/mtools/description
 Mtools is a collection of utilities to access MS-DOS disks from GNU and 
 Unix without mounting them. It supports Win'95 style long file names, 
 OS/2 Xdf disks and 2m disks (store up to 1992k on a high density 3 1/2 disk). 
 In addition to file access, it supports many FAT-specific features: volume labels,e.t.c
endef

define Package/mtools/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mtools $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mattrib $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mbadblocks $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mcat  $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mcd  $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mclasserase  $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mcopy  $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mdel  $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mdeltree  $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mdir  $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mdu $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mformat $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/minfo $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mlabel $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mmd $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mmount $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mmove $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mpartition $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mrd $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mren $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mshortname $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mshowfat $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mtoolstest $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mtype $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mzip  $(1)/usr/bin
endef

$(eval $(call BuildPackage,mtools))

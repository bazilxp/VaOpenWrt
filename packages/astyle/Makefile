#
# Copyright (C) 2010-2011 OpenWrt.org
# Copyright (C) 2010 Gianluigi Tiesi <sherpya@netfarm.it>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=astyle
PKG_VERSION:=2.04
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)_$(PKG_VERSION)_linux.tar.gz
PKG_SOURCE_URL:=https://cecas.clemson.edu/dealii/mirror
PKG_MD5SUM:=30b1193a758b0909d06e7ee8dd9627f6
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/astyle
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=astyle
  DEPENDS:= +libstdcpp
  URL:=http://astyle.sourceforge.net/

endef

define Package/astyle/description
A Free, Fast, and Small Automatic Formatter
for C, C++, C++/CLI, Objective‑C, C#, and Java Source Code
endef

MAKE_FLAGS += -f build/gcc/Makefile 
#-prefix=$(PKG_BUILD_DIR)

# notes:
#  - I'm using := and not += because it is not a standard configure script
#  - I ask not to strip, because it should be handled by the toolchain
#CONFIGURE_ARGS := \
#	--prefix=/usr \
#	--etcdir=/etc \
#	--debug=0 \
#	--i18n=0 \
#	--strip=0

define Package/astyle/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/bin/astyle $(1)/usr/bin/
endef

$(eval $(call BuildPackage,astyle))

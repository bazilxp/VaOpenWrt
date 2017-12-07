#
# Copyright (C) 2007-2008 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=links
PKG_VERSION:=2.14
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://links.twibright.com/download
PKG_MD5SUM:=2131be3232d05c56366ca3da8c7d4218
PKG_MAINTAINER:=SvOlli <svolli@svolli.de>

PKG_LICENSE:=GPL
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/host-build.mk
include $(INCLUDE_DIR)/package.mk

define Package/links/Default
  SUBMENU:=Network
  URL:=http://links.twibright.com/
endef

define Package/links
$(call Package/links/Default)
  SECTION:=utils
  CATEGORY:=Utilities
  DEPENDS:=+libbz2 zlib libevent2 libopenssl liblzma
  TITLE:=links is a console web browser
endef

define Package/links/description
	links is a freely available, minimal web browser for console.
endef

TARGET_CFLAGS += \
	$(FPIC) \
	$(TARGET_LDFLAGS)

CONFIGURE_ARGS += --prefix=/usr

MAKE_FLAGS += \
	CFLAGS="$(TARGET_CFLAGS)" \
	all

define Build/InstallDev
endef

define Package/links/install
	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/links $(1)/usr/bin/links
endef

HOST_CFLAGS += \
	$(FPIC) \
	$(HOST_LDFLAGS)

HOST_MAKE_FLAGS+= \
	CFLAGS="$(HOST_CFLAGS)" \
	all

HOST_CONFIGURE_ARGS+= \
	--prefix=$(STAGING_DIR_HOST)

define Host/Install
	$(INSTALL_DIR) $(STAGING_DIR_HOST)/bin/
	$(INSTALL_BIN) $(STAGING_DIR_HOST)/bin/links
endef

$(eval $(call HostBuild))

$(eval $(call BuildPackage,links))

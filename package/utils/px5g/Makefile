#
# Copyright (C) 2010-2015 Jo-Philipp Wich <jo@mein.io>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=px5g
PKG_RELEASE:=4
PKG_LICENSE:=LGPL-2.1

PKG_USE_MIPS16:=0

include $(INCLUDE_DIR)/package.mk

define Package/px5g
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=X.509 certificate generator (using PolarSSL)
  MAINTAINER:=Jo-Philipp Wich <jo@mein.io>
  DEPENDS:=+libpolarssl
endef

define Package/px5g/description
 Px5g is a tiny standalone X.509 certificate generator.
 It suitable to create key files and certificates in DER
 and PEM format for use with stunnel, uhttpd and others.
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
endef

define Build/Compile
	$(TARGET_CC) $(TARGET_CFLAGS) -o $(PKG_BUILD_DIR)/px5g px5g.c -lpolarssl
endef

define Package/px5g/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/px5g $(1)/usr/sbin/px5g
endef

$(eval $(call BuildPackage,px5g))

#
# Copyright (C) 2006-2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

# Package content copyright (C) 
# 2011-2012 Jan Huwald <jh@sotun.de>


include $(TOPDIR)/rules.mk

PKG_NAME:=hbbp
PKG_VERSION:=20120719
PKG_RELEASE:=1
PKG_REV:=3fda60d9ca5eac24ed24c317605bd0d52bfd4393

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://github.com/ffrl/hbbp.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

# it should be ensured, that nacl is build before this package!!!
#PKG_BUILD_DEPENDS:=+nacl

include $(INCLUDE_DIR)/package.mk

define Package/hbbp
  SECTION:=base
  CATEGORY:=Network
  SUBMENU:=Freifunk Rheinland
  DEFAULT:=n
  TITLE:=HBBP - UDP broadcast utility
#  MAINTAINER:=Jan Huwald <jh@sotun.de> # phip changed this package
  MAINTAINER:=Philipp Psurek <phip@vmail.me>, Jan Huwald <jh@sotun.de>
  URL:=http://code.sotun.de/git/hbbp
  DEPENDS:=@IPV6
endef

define Package/hbbp/description
	Send UDP based broadcast messages and process them using the
	included demon. Messages consist of a key and an optional
	payload. The payload may be assymetrically encrypted.
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR)  \
		CC="$(TARGET_CC)" \
		CFLAGS="$(TARGET_CFLAGS)" \
		LDFLAGS="$(TARGET_LDFLAGS)" \
		EXTERNAL_NACL=1
endef

define Package/hbbp/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/hbbpd $(1)/usr/sbin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/hbbpc $(1)/usr/sbin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/hbbp_keygen $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,hbbp))

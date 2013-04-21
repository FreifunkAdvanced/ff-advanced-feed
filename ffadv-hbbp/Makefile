#
# Copyright (C) 2006-2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

# Package content copyright (C) 
# 2011-2012 Jan Huwald <jh@sotun.de>


include $(TOPDIR)/rules.mk

PKG_NAME:=ffadv-hbbp
PKG_VERSION:=20130417
PKG_RELEASE:=3
PKG_REV:=c9949c5627044fb3dc3caf6f1a3902c44392bac1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://github.com/FreifunkAdvanced/hbbp.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

PKG_BUILD_DEPENDS:=+nacl

include $(INCLUDE_DIR)/package.mk

define Package/ffadv-hbbp
  SECTION:=base
  CATEGORY:=Network
  SUBMENU:=Freifunk Advanced
  DEFAULT:=n
  TITLE:=HBBP - UDP broadcast utility
  MAINTAINER:=Linus Broich <cyrus@lambdacore.de>
  URL:=http://code.sotun.de/git/hbbp
  DEPENDS:=@IPV6
endef

define Package/ffadv-hbbp/description
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

define Package/ffadv-hbbp/install
	$(INSTALL_DIR) $(1)/usr/sbin $(1)/etc/init.d $(1)/etc/config
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/hbbpd $(1)/usr/sbin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/hbbpc $(1)/usr/sbin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/hbbp_keygen $(1)/usr/sbin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/hbbpp $(1)/usr/sbin/
	$(INSTALL_BIN) ./ipkg/hbbp.init $(1)/etc/init.d/hbbp
	$(INSTALL_CONF) ./ipkg/hbbp.config $(1)/etc/config/hbbp
endef

$(eval $(call BuildPackage,ffadv-hbbp))

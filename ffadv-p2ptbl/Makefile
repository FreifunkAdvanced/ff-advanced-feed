#
# Copyright (C) 2006-2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

# Package content copyright (C) 
# 2011-2012 Jan Huwald <jh@sotun.de>
#      2012 Freifunk Rheinland e. V. <http://www.freifunk-rheinland.net/>


include $(TOPDIR)/rules.mk

PKG_NAME:=ffadv-p2ptbl
PKG_VERSION:=20130417
PKG_RELEASE:=1
PKG_REV:=5320fa5491dc3b40b116a16e2f6686ff9705e43f

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://github.com/FreifunkAdvanced/p2ptbl.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

include $(INCLUDE_DIR)/package.mk

define Package/ffadv-p2ptbl
  SECTION:=base
  CATEGORY:=Network
  SUBMENU:=Freifunk Advanced
  PKGARCH:=all
  DEFAULT:=n
  TITLE:=lightweight distributed key-value store
  MAINTAINER:=Linus Broich <cyrus@lambdacore.de>
# URL:=http://code.sotun.de/git/ffj/p2ptbl
  DEPENDS:=+ffadv-shuf +ffadv-hbbp +coreutils +coreutils-join
endef

define Package/ffadv-p2ptbl/description
	P2P tables are a lightweight distributed key-value store with
	built-in collision arbitration. Eventual consistency is maintained
	using a HBBP-based gossip protocol.
endef

define Build/Compile
endef

define Package/ffadv-p2ptbl/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/p2ptbl $(1)/usr/sbin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/p2ptbl-recv $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,ffadv-p2ptbl))

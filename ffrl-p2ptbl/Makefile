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

PKG_NAME:=ffrl-p2ptbl
PKG_VERSION:=20120521
PKG_RELEASE:=1
PKG_REV:=9e9a51fa040b372bc965e3ce7e25074257f7a6b4

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://github.com/ffrl/p2ptbl.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

include $(INCLUDE_DIR)/package.mk

define Package/ffrl-p2ptbl
  SECTION:=base
  CATEGORY:=Network
  SUBMENU:=Freifunk Rheinland
  DEFAULT:=n
  TITLE:=lightweight distributed key-value store
# MAINTAINER:=Jan Huwald <jh@sotun.de>
# URL:=http://code.sotun.de/git/ffj/p2ptbl
  DEPENDS:=+ffrl-shuf +hbbp +coreutils +coreutils-join
endef

define Package/ffrl-p2ptbl/description
	P2P tables are a lightweight distributed key-value store with
	built-in collision arbitration. Eventual consistency is maintained
	using a HBBP-based gossip protocol.
endef

define Build/Compile
endef

define Package/ffrl-p2ptbl/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/p2ptbl $(1)/usr/sbin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/p2ptbl-recv $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,ffrl-p2ptbl))

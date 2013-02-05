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

PKG_NAME:=ffadv-urlencoder
PKG_VERSION:=20121201
PKG_RELEASE:=1
PKG_REV:=d4832c2b1567a6c9abcce5ad6fd380e80e6a5ccc

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://github.com/FreifunkAdvanced/urlencoder.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

include $(INCLUDE_DIR)/package.mk

define Package/ffadv-urlencoder
  SECTION:=base
  CATEGORY:=Utilities
  SUBMENU:=Freifunk Advanced
  PKGARCH:=all
  DEFAULT:=n
  TITLE:=Url encoder and decoder
  MAINTAINER:=Linus Broich <cyrus@lambdacore.de>
# URL:=http://code.sotun.de/git/ffj/fsm
# DEPENDS:=
endef

define Package/ffadv-urlencoder/description
	Simple shell based url encoder and decoder
endef

define Build/Compile
endef

define Package/ffadv-urlencoder/install
	$(INSTALL_DIR) $(1)/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/urlencode $(1)/sbin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/urldecode $(1)/sbin/
endef

$(eval $(call BuildPackage,ffadv-urlencoder))

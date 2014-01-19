#
# Copyright (C) 2006-2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

# Package content copyright (C) 
# 2011-2012 Jan Huwald <jh@sotun.de>
# 2012	Linus Broich <lcb01@lcb01.de>
#      2012 Freifunk Rheinland e. V. <http://www.freifunk-rheinland.net/>


include $(TOPDIR)/rules.mk

PKG_NAME:=ffadv-fastdregister
PKG_VERSION:=20140119
PKG_RELEASE:=1
PKG_REV:=2dccbe3c9bc2e4ec01ff1a50d4bbd0d3a3c9f683

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://github.com/FreifunkAdvanced/fastdregister
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

include $(INCLUDE_DIR)/package.mk

define Package/ffadv-fastdregister
  SECTION:=base
  CATEGORY:=Utilities
  SUBMENU:=Freifunk Advanced
  PKGARCH:=all
  DEFAULT:=n
  TITLE:=Fastd registration
  MAINTAINER:=Linus Broich <lcb01@lcb01.de>
# URL:=https://github.com/FreifunkAdvanced/owm-update
  DEPENDS:=+netcat
endef

define Package/ffadv-fastdregister/description
	This script registers a node at fastd servers using a md5 hash of the fastd public key as hostname.
	It is designed to work together with Freifunk Rheinland registration service.
	See: https://github.com/FreifunkAdvanced/ffff
endef

define Build/Compile
endef

define Package/ffadv-fastdregister/install
	$(INSTALL_DIR) $(1)/etc/config $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/usr/sbin/fastdregister $(1)/usr/sbin/
	$(INSTALL_CONF) ipkg/fastdregister.config $(1)/etc/config/
endef

$(eval $(call BuildPackage,ffadv-fastdregister))

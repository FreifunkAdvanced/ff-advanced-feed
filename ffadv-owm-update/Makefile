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

PKG_NAME:=ffadv-owm-update
PKG_VERSION:=20130506
PKG_RELEASE:=3
PKG_REV:=4dd4c977b915c766bf7993b1026b7ad56ab116c5

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://github.com/FreifunkAdvanced/owm-update.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

include $(INCLUDE_DIR)/package.mk

define Package/ffadv-owm-update
  SECTION:=base
  CATEGORY:=Utilities
  SUBMENU:=Freifunk Advanced
  PKGARCH:=all
  DEFAULT:=n
  TITLE:=OpenWifiMap update script
  MAINTAINER:=Linus Broich <lcb01@lcb01.de>
# URL:=https://github.com/FreifunkAdvanced/owm-update
  DEPENDS:=ffadv-fsm +ffadv-nodeid +netcat
endef

define Package/ffadv-owm-update/description
	Finite State Machine Inetable States
endef

define Build/Compile
endef

define Package/ffadv-owm-update/install
	$(INSTALL_DIR) $(1)/etc/config $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/usr/sbin/owm-update $(1)/usr/sbin/
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/etc/config/owm $(1)/etc/config/
	
	mkdir -p $(1)/CONTROL
	$(INSTALL_BIN) ./ipkg/ffadv-owm-update.postinst $(1)/CONTROL/postinst
	$(INSTALL_BIN) ./ipkg/ffadv-owm-update.postrm $(1)/CONTROL/postrm
endef

$(eval $(call BuildPackage,ffadv-owm-update))

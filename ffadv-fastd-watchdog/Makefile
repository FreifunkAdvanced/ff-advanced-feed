#
# Copyright (C) 2006-2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

# Package content copyright (C) 
# 2014	Linus Broich <lcb01@lcb01.de>

include $(TOPDIR)/rules.mk

PKG_NAME:=ffadv-fastd-watchdog
PKG_VERSION:=20140121
PKG_RELEASE:=1
PKG_REV:=dd4f340dc6c2b34ad0c76c131d5250bf4fb6d689

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://github.com/FreifunkAdvanced/fastd-watchdog.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

include $(INCLUDE_DIR)/package.mk

define Package/ffadv-fastd-watchdog
  SECTION:=base
  CATEGORY:=Utilities
  SUBMENU:=Freifunk Advanced
  PKGARCH:=all
  DEFAULT:=n
  TITLE:=fastd watchdog
  MAINTAINER:=Linus Broich <lcb01@fnordeingang.de>
  DEPENDS:=+fastd
endef

define Package/ffadv-fastd-watchdog/description
	fastd watchdog
endef

define Build/Compile
endef

define Package/ffadv-fastd-watchdog/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/usr/sbin/fastd_watchdog   $(1)/usr/sbin
	mkdir -p $(1)/CONTROL
	$(INSTALL_BIN) ./ipkg/ffadv-fastd-watchdog.postinst $(1)/CONTROL/postinst
	$(INSTALL_BIN) ./ipkg/ffadv-fastd-watchdog.postrm $(1)/CONTROL/postrm
endef

$(eval $(call BuildPackage,ffadv-fastd-watchdog))

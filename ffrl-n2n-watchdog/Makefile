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

PKG_NAME:=ffrl-n2n-watchdog
PKG_VERSION:=20121201
PKG_RELEASE:=1
PKG_REV:=a21f94d51789273d40359453e2d66cb4645300fc

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://github.com/ffrl/n2n-watchdog.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

include $(INCLUDE_DIR)/package.mk

define Package/ffrl-n2n-watchdog
  SECTION:=base
  CATEGORY:=Utilities
  SUBMENU:=Freifunk Rheinland
  PKGARCH:=all
  DEFAULT:=n
  TITLE:=n2n watchdog
  MAINTAINER:=Linus Broich <lcb01@lcb01.de>
# URL:=https://github.com/ffrl/fsm-inetable
  DEPENDS:=ffrl-fsm +ffrl-urlscripts
endef

define Package/ffrl-n2n-watchdog/description
	n2n watchdog
endef

define Build/Compile
endef

define Package/ffrl-n2n-watchdog/install
	$(INSTALL_DIR) $(1)/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/n2n_watchdog   $(1)/sbin
	mkdir -p $(1)/CONTROL
	$(INSTALL_BIN) ./ipkg/ffrl-n2n-watchdog.postinst $(1)/CONTROL/postinst
	$(INSTALL_BIN) ./ipkg/ffrl-n2n-watchdog.postrm $(1)/CONTROL/postrm
endef

$(eval $(call BuildPackage,ffrl-n2n-watchdog))

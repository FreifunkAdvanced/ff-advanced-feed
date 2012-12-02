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

PKG_NAME:=ffrl-fsm-inetable
PKG_VERSION:=20121201
PKG_RELEASE:=1
PKG_REV:=52bab420075c6e1dc1014e304772cb56d700fd33

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://github.com/ffrl/fsm-inetable.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

include $(INCLUDE_DIR)/package.mk

define Package/ffrl-fsm-inetable
  SECTION:=base
  CATEGORY:=Utilities
  SUBMENU:=Freifunk Rheinland
  PKGARCH:=all
  DEFAULT:=n
  TITLE:=Finite State Machine Inetable States
  MAINTAINER:=Linus Broich <lcb01@lcb01.de>
# URL:=https://github.com/ffrl/fsm-inetable
  DEPENDS:=ffrl-fsm +ffrl-urlencoder
endef

define Package/ffrl-fsm-inetable/description
	Finite State Machine Inetable States
endef

define Build/Compile
endef

define Package/ffrl-fsm-inetable/install
	$(INSTALL_DIR) $(1)/etc/config $(1)/etc/fsm/inetable/trans $(1)/etc/fsm/inetable/watch $(1)/hbbp/p2ptbl $(1)/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/etc/fsm/inetable/trans/*   $(1)/etc/fsm/inetable/trans/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/etc/fsm/inetable/watch/* $(1)/etc/fsm/inetable/watch/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/sbin/test_connectivity $(1)/sbin/
	$(INSTALL_DATA) $(1)/etc/config/cloud $(1)/etc/config/
	$(CP) $(PKG_BUILD_DIR)/etc/fsm/inetable/{common.sh,common_queen.sh,initial_state} $(1)/etc/fsm/inetable/
	ln -s $(1)/sbin/p2ptbl-recv $(1)/hbbp/p2ptbl/gwip
	mkdir -p $(1)/CONTROL
	$(INSTALL_BIN) ./ipkg/ffrl-fsm-inetable.postinst $(1)/CONTROL/postinst
	$(INSTALL_BIN) ./ipkg/ffrl-fsm-inetable.postrm $(1)/CONTROL/postrm
endef

$(eval $(call BuildPackage,ffrl-fsm-inetable))

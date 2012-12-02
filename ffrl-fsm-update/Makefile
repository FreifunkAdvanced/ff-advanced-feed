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

PKG_NAME:=ffrl-fsm-update
PKG_VERSION:=20121201
PKG_RELEASE:=1
PKG_REV:=09ec33d60dadabb5b7ecadc5690059a5628b2799

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://github.com/ffrl/fsm-update.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

include $(INCLUDE_DIR)/package.mk

define Package/ffrl-fsm-update
  SECTION:=base
  CATEGORY:=Utilities
  SUBMENU:=Freifunk Rheinland
  PKGARCH:=all
  DEFAULT:=n
  TITLE:=Finite State Machine Update States
  MAINTAINER:=Linus Broich <lcb01@lcb01.de>
# URL:=https://github.com/ffrl/fsm-update
  DEPENDS:=ffrl-fsm
endef

define Package/ffrl-fsm-update/description
	Finite State Machine Update States
endef

define Build/Compile
endef

define Package/ffrl-fsm-update/install
	$(INSTALL_DIR) $(1)/etc/fsm/update/trans $(1)/etc/fsm/update/watch $(1)/hbbp/p2ptbl
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/etc/fsm/update/trans/*   $(1)/etc/fsm/update/trans/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/etc/fsm/update/watch/* $(1)/etc/fsm/update/watch/
	$(CP) $(PKG_BUILD_DIR)/etc/fsm/update/{common.sh,initial_state} $(1)/etc/fsm/update/
	ln -s $(1)/sbin/p2ptbl-recv $(1)/hbbp/p2ptbl/gwip
	mkdir -p $(1)/CONTROL
	$(INSTALL_BIN) ./ipkg/ffrl-fsm-update.postinst $(1)/CONTROL/postinst
	$(INSTALL_BIN) ./ipkg/ffrl-fsm-update.postrm $(1)/CONTROL/postrm
endef

$(eval $(call BuildPackage,ffrl-fsm-update))

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

PKG_NAME:=ffadv-fsm-update
PKG_VERSION:=20130417
PKG_RELEASE:=1
PKG_REV:=d51113b8618303f576e60b59ba1b882dcfc9daea

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://github.com/FreifunkAdvanced/fsm-update.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

include $(INCLUDE_DIR)/package.mk

define Package/ffadv-fsm-update
  SECTION:=base
  CATEGORY:=Utilities
  SUBMENU:=Freifunk Advanced
  PKGARCH:=all
  DEFAULT:=n
  TITLE:=Finite State Machine Update States
  MAINTAINER:=Linus Broich <lcb01@lcb01.de>
# URL:=https://github.com/FreifunkAdvanced/fsm-update
  DEPENDS:=ffadv-fsm
endef

define Package/ffadv-fsm-update/description
	Finite State Machine Update States
endef

define Build/Compile
endef

define Package/ffadv-fsm-update/install
	$(INSTALL_DIR) $(1)/lib/fsm/update/trans $(1)/lib/fsm/update/watch
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/lib/fsm/update/trans/*   $(1)/lib/fsm/update/trans/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/lib/fsm/update/watch/* $(1)/lib/fsm/update/watch/
	$(CP) $(PKG_BUILD_DIR)/lib/fsm/update/{common.sh,initial_state} $(1)/lib/fsm/update/
	mkdir -p $(1)/CONTROL
	$(INSTALL_BIN) ./ipkg/ffadv-fsm-update.postinst $(1)/CONTROL/postinst
	$(INSTALL_BIN) ./ipkg/ffadv-fsm-update.postrm $(1)/CONTROL/postrm
endef

$(eval $(call BuildPackage,ffadv-fsm-update))

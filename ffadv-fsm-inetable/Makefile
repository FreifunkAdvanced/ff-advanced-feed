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

PKG_NAME:=ffadv-fsm-inetable
PKG_VERSION:=20140113
PKG_RELEASE:=1
PKG_REV:=035d684cfdaf3f3bd731fa81330eb0abfdf3ede4

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://github.com/FreifunkAdvanced/fsm-inetable.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

include $(INCLUDE_DIR)/package.mk

define Package/ffadv-fsm-inetable
  SECTION:=base
  CATEGORY:=Utilities
  SUBMENU:=Freifunk Advanced
  PKGARCH:=all
  DEFAULT:=n
  TITLE:=Finite State Machine Inetable States
  MAINTAINER:=Linus Broich <lcb01@lcb01.de>
# URL:=https://github.com/FreifunkAdvanced/fsm-inetable
  DEPENDS:=ffadv-fsm +ffadv-urlencoder +firewall
endef

define Package/ffadv-fsm-inetable/description
	Finite State Machine Inetable States
endef

define Build/Compile
endef

define Package/ffadv-fsm-inetable/install
	$(INSTALL_DIR) $(1)/etc $(1)/lib/fsm/inetable $(1)/lib/fsm/inetable/trans $(1)/lib/fsm/inetable/watch $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/lib/fsm/inetable/trans/*   $(1)/lib/fsm/inetable/trans/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/lib/fsm/inetable/watch/* $(1)/lib/fsm/inetable/watch/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/usr/sbin/test_connectivity $(1)/usr/sbin/
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/etc/firewall.ffrl $(1)/etc/
	$(CP) $(PKG_BUILD_DIR)/lib/fsm/inetable/{common.sh,common-watch.sh,common-queen.sh,initial_state} $(1)/lib/fsm/inetable/
	mkdir -p $(1)/CONTROL
	$(INSTALL_BIN) ./ipkg/ffadv-fsm-inetable.postinst $(1)/CONTROL/postinst
	$(INSTALL_BIN) ./ipkg/ffadv-fsm-inetable.postrm $(1)/CONTROL/postrm
endef

$(eval $(call BuildPackage,ffadv-fsm-inetable))

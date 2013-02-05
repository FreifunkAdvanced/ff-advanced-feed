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

PKG_NAME:=ffadv-fsm
PKG_VERSION:=20121201
PKG_RELEASE:=3
PKG_REV:=35567e22db7b59557067608b52379fc72ce7e4a4

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://github.com/FreifunkAdvanced/fsm.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

include $(INCLUDE_DIR)/package.mk

define Package/ffadv-fsm
  SECTION:=base
  CATEGORY:=Utilities
  SUBMENU:=Freifunk Advanced
  PKGARCH:=all
  DEFAULT:=n
  TITLE:=Finite State Machine Interpreter
# MAINTAINER:=Jan Huwald <jh@sotun.de>
# URL:=http://code.sotun.de/git/ffj/fsm
  DEPENDS:=+flock +ffadv-p2ptbl
endef

define Package/ffadv-fsm/description
	Allows to implement FSMs using sets of executables (typically
	shell scripts)
endef

define Build/Compile
endef

define Package/ffadv-fsm/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/fsm $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,ffadv-fsm))

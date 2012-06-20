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

PKG_NAME:=ffrl-fsm
PKG_VERSION:=20120611
PKG_RELEASE:=1
PKG_REV:=dc7c3a5ede6ba6db0d9d018ec9581fc27f82fc66

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://github.com/ffrl/fsm.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

include $(INCLUDE_DIR)/package.mk

define Package/ffrl-fsm
  SECTION:=base
  CATEGORY:=Utilities
  SUBMENU:=Freifunk Rheinland
  DEFAULT:=n
  TITLE:=Finite State Machine Interpreter
# MAINTAINER:=Jan Huwald <jh@sotun.de>
# URL:=http://code.sotun.de/git/ffj/fsm
  DEPENDS:=+flock
endef

define Package/ffrl-fsm/description
	Allows to implement FSMs using sets of executables (typically
	shell scripts)
endef

define Build/Compile
endef

define Package/ffrl-fsm/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/fsm $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,ffrl-fsm))

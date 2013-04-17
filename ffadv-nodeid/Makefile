#
# Copyright (C) 2006-2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

# Package content copyright (C) 
# 2011-2012 Jan Huwald <jh@sotun.de>
# 2012-2013	Linus Broich <lcb01@lcb01.de>
# 2012-2013 Freifunk Rheinland e. V. <http://www.freifunk-rheinland.net/>


include $(TOPDIR)/rules.mk

PKG_NAME:=ffadv-nodeid
PKG_VERSION:=20130417
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define Package/ffadv-nodeid
  SECTION:=base
  CATEGORY:=Utilities
  SUBMENU:=Freifunk Advanced
  PKGARCH:=all
  DEFAULT:=n
  TITLE:=Node ID generator
  MAINTAINER:=Linus Broich <cyrus@lambdacore.de>
# URL:=https://github.com/FreifunkAdvanced/fsm-inetable
#  DEPENDS:=
endef

define Package/ffadv-nodeid/description
	Node ID generator
endef

define Build/Compile
endef

define Package/ffadv-nodeid/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./ipkg/nodeid $(1)/etc/init.d/nodeid
endef

$(eval $(call BuildPackage,ffadv-nodeid))

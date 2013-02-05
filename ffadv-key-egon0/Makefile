#
# Copyright (C) 2006-2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

# Package content copyright (C) 
#      2012 Freifunk Rheinland e. V. <http://www.freifunk-rheinland.net/>


include $(TOPDIR)/rules.mk

PKG_NAME:=ffadv-key-egon0
PKG_VERSION:=20130205
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define Package/ffadv-key-egon0
  SECTION:=base
  CATEGORY:=Utilities
  SUBMENU:=Freifunk Advanced
  PKGARCH:=all
  DEFAULT:=n
  TITLE:=SSH maintenance key (FFJ egon0)
  MAINTAINER:=egon0 (Freifunk Jena) <egon0@freifunk-jena.de>
  URL:=http://www.freifunk-jena.de
  DEPENDS:=+dropbear
endef

define Package/ffadv-key-egon0/description
  SSH key for maintenance
endef

define Build/Prepare
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/ffadv-key-egon0/install
	mkdir -p $(1)/CONTROL
	$(INSTALL_BIN) ./ipkg/ffadv-key-egon0.postinst $(1)/CONTROL/postinst
	$(INSTALL_BIN) ./ipkg/ffadv-key-egon0.postrm $(1)/CONTROL/postrm
endef

$(eval $(call BuildPackage,ffadv-key-egon0))

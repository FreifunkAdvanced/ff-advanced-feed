#
# Copyright (C) 2006-2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

# Package content copyright (C) 
#      2012 Freifunk Rheinland e. V. <http://www.freifunk-rheinland.net/>


include $(TOPDIR)/rules.mk

PKG_NAME:=ffrl-key-phip
PKG_VERSION:=20120624
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define Package/ffrl-key-phip
  SECTION:=base
  CATEGORY:=Utilities
  SUBMENU:=Freifunk Rheinland
  PKGARCH:=all
  DEFAULT:=n
  TITLE:=SSH maintenance key (FFW phip)
  MAINTAINER:=phip <phip@vmail.me>
  URL:=http://freifunk-rheinland.net
  DEPENDS:=+dropbear
endef

define Package/ffrl-key-phip/description
  SSH key for maintenance
endef

define Build/Prepare
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/ffrl-key-phip/install
	mkdir -p $(1)/CONTROL
	$(INSTALL_BIN) ./ipkg/ffrl-key-phip.postinst $(1)/CONTROL/postinst
	$(INSTALL_BIN) ./ipkg/ffrl-key-phip.postrm $(1)/CONTROL/postrm
endef

$(eval $(call BuildPackage,ffrl-key-phip))

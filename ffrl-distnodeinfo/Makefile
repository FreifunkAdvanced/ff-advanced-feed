#
# Copyright (C) 2006-2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

# Package content copyright (C) 
#      2012 Philipp Psurek <phip@vmail.me>

include $(TOPDIR)/rules.mk

PKG_NAME:=ffrl-distnodeinfo
PKG_VERSION:=0.8.0
PKG_RELEASE:=1
PKG_REV:=0653b550d9515901f7b4c365fd4c01ff64caab81

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://github.com/phi-psi/distnodeinfo.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/ffrl-distnodeinfo
  SECTION:=base
  CATEGORY:=Utilities
  SUBMENU:=Freifunk Rheinland
  TITLE:=Distributed information service of Freifunk nodes
  DEPENDS:=+hbbp
# URL:=
  MAINTAINER:=Philipp Psurek <phip@vmail.me>
  DEFAULT:=n
  PKGARCH:=all
endef

define Package/ffrl-distnodeinfo/description
  Generiert und verteilt Informationen über Knoten in der Freifunkwolke und
  sendet Standortkoordinaten zum Kartenserver.
endef

define Build/Prepare
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/ffrl-distnodeinfo/install
	$(CP) -ap (PKG_BUILD_DIR)/files/root/* $(1)/
	mkdir -p $(1)/CONTROL
	$(INSTALL_BIN) (PKG_BUILD_DIR)/ipkg/ffrl-distnodeinfo.postinst $(1)/CONTROL/postinst
	$(INSTALL_BIN) (PKG_BUILD_DIR)/ipkg/ffrl-distnodeinfo.postrm $(1)/CONTROL/postrm
endef

$(eval $(call BuildPackage,ffrl-distnodeinfo))

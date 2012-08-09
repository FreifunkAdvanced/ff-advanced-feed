#
# Copyright (C) 2006-2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

# Package content copyright (C) 
#      2012 Philipp Psurek <phip@vmail.me>
#
include $(TOPDIR)/rules.mk


PKG_NAME:=ffrl-nodeconfig
PKG_VERSION:=0.8.0
PKG_RELEASE:=1
PKG_REV:=c9949c5627044fb3dc3caf6f1a3902c44392bac1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://github.com/phi-psi/nodeconfig.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git
PKG_REV:=b9e46b7f5ccf2b2bcd886c62f4b7ad561b33f776

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DEPENDS := uci

include $(INCLUDE_DIR)/package.mk

define Package/ffrl-nodeconfig
  SECTION:=base
  CATEGORY:=Utilities
  SUBMENU:=Freifunk Rheinland
  PKGARCH:=all
  DEFAULT:=n
  TITLE:= fast node configurator
  MAINTAINER:=Philipp Psurek <phip@vmail.me>
# URL:=
  DEPENDS:=+uci
endef

define Package/ffrl-nodeconfig/description
 Ein Skript, welches den Router für eine Freifunkzelle umkonfiguriert.
endef

define Build/Prepare
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/ffrl-nodeconfig/install
	$(CP) -ap $(PKG_BUILD_DIR)/files/common/* $(1)/
endef

$(eval $(call BuildPackage,ffrl-nodeconfig))

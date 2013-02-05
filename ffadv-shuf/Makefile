#
# Copyright (C) 2006-2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

# Package content copyright (C) 
# 2011-2012 Jan Huwald <jh@sotun.de>



include $(TOPDIR)/rules.mk

PKG_NAME:=ffadv-shuf
PKG_VERSION:=20111203
PKG_RELEASE:=1
PKG_REV:=17ec1ab88daf4e36c5821700b0069ad33c377152

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://github.com/FreifunkAdvanced/shuf.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

include $(INCLUDE_DIR)/package.mk

define Package/ffadv-shuf
  SECTION:=base
  CATEGORY:=Utilities
  SUBMENU:=Freifunk Advanced
  PKGARCH:=all
  DEFAULT:=n
  TITLE:=shuffle lines
  MAINTAINER:=Linus Broich <cyrus@lambdacore.de>
# URL:=http://code.sotun.de/git/ffj/shuf
  DEPENDS:=@(!PACKAGE_coreutils-shuf)
endef

define Package/ffadv-shuf/description
	awk-based variant of coreutils-shuf without any of the original
	command-line parameters
endef

define Build/Compile
endef

define Package/ffadv-shuf/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/usr/sbin/shuf $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,ffadv-shuf))

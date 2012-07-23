#
# Copyright (C) 2006-2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

# Package content copyright (C) 
#      2011 2011 Darkeye <postfach@martinmichel.info>
#      2011 egon0 <ms@resonar.de>
#      2011 Frank Lanitz <frank@frank.uvena.de>
#      2011 Martin Michel <darkeye@seestern.(none)>
#      2011 frlan <frank@frank.uvena.de>
# 2011-2012 egon_ffj <egon@freifunk-jena.de>
# 2011-2012 Jan Huwald <jh@sotun.de>
# 2011-2012 Freifunk Rheinland e. V. <http://www.freifunk-rheinland.net/>
# 2011-2012 LCB01 <lcb01@fnordeingang.de>
#      2012 Kai de Haan<skaverat@funlynx.de>


include $(TOPDIR)/rules.mk

PKG_NAME:=ffrl-splash
PKG_VERSION:=0.8.0
PKG_RELEASE:=1
PKG_REV:=81b89a00a990945be5ed01cf9452f4f003513767

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://github.com/ffrl/splash.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

include $(INCLUDE_DIR)/package.mk

define Package/ffrl-splash
  SECTION:=base
  CATEGORY:=Utilities
  SUBMENU:=Freifunk Rheinland
  PKGARCH:=all
  DEFAULT:=n
  TITLE:=Freifunk Rheinland e. V. HTML splash
  MAINTAINER:=Philipp Psurek <phip@vmail.me>
  URL:=https://freifunk-rheinland.net
  DEPENDS:=+uhttpd
endef

define Package/ffrl-splash/description
  Dem Freifunknutzer wird bei der ersten Einwahl ins Freifunk eine Splash-Seite
  Präsentiert. Möchte er ins Internet gelangen muss er den Bedingungen
  zustimmen. Außerdem erhält der Nutzer auf diesen Webseiten die wichtigsten
  Informationen über den Freifunk.
endef

define Build/Compile
endef

define Package/ffrl-splash/install
	$(CP) -ap files/common/* $(1)/
endef

$(eval $(call BuildPackage,ffrl-splash))

include $(TOPDIR)/rules.mk

PKG_NAME:=geolocate
PKG_VERSION:=20120620
PKG_RELEASE:=1
PKG_REV:=769792c00de12cd885c380402aef9b5987f44d9c

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://code.sotun.de/ffj/geolocate
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

include $(INCLUDE_DIR)/package.mk

define Package/geolocate
  SECTION:=base
  CATEGORY:=Utilities
  DEFAULT:=n
  TITLE:=Learn device location using wifi neighbours
  URL:=http://code.sotun.de/git/ffj/geolocate
  DEPENDS:=uci
endef

define Package/geolocate/description
	Send the neighbouring wifi networks to google and get the
	geolocation in return. The result is stored via UCI.
endef

define Build/Compile
endef

define Package/geolocate/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/geolocate $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,geolocate))

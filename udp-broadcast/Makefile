include $(TOPDIR)/rules.mk

PKG_NAME:=udp-broadcast
PKG_VERSION:=20111205
PKG_RELEASE:=1
PKG_REV:=dcce1a8d1335e89dcf9d64bb2202e34d8f58f3cd

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://git.freifunk-jena.de/freifunk/ffj-udp-broadcast
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

include $(INCLUDE_DIR)/package.mk

define Package/udp-broadcast
  SECTION:=base
  CATEGORY:=Network
  DEFAULT:=n
  TITLE:=UDP broadcast utility
  URL:=http://dev.freifunk-jena.de:8082/projects/ffj-udp-broadcast
endef

define Package/udp-broadcast/description
	Send UDP based broadcast messages and process them using the included demon.
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR)  \
		CC="$(TARGET_CC)" \
		CFLAGS="$(TARGET_CFLAGS) -Wall" \
		LDFLAGS="$(TARGET_LDFLAGS)"
endef

define Package/udp-broadcast/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/broadcaster $(1)/usr/sbin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/listener $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,udp-broadcast))

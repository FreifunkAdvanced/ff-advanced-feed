include $(TOPDIR)/rules.mk

PKG_NAME:=hbbp
PKG_VERSION:=20120521
PKG_RELEASE:=3
PKG_REV:=cf16b2181dbd1e769b1cdd2d6c27e5300a419012

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://code.sotun.de/hbbp
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

PKG_BUILD_DEPENDS:=+nacl

include $(INCLUDE_DIR)/package.mk

define Package/hbbp
  SECTION:=base
  CATEGORY:=Network
  DEFAULT:=n
  TITLE:=HBBP - UDP broadcast utility
  URL:=http://code.sotun.de/git/hbbp
  DEPENDS:=@IPV6
endef

define Package/hbbp/description
	Send UDP based broadcast messages and process them using the
	included demon. Messages consist of a key and an optional
	payload. The payload may be assymetrically encrypted.
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR)  \
		CC="$(TARGET_CC)" \
		CFLAGS="$(TARGET_CFLAGS)" \
		LDFLAGS="$(TARGET_LDFLAGS)" \
		EXTERNAL_NACL=1
endef

define Package/hbbp/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/hbbpd $(1)/usr/sbin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/hbbpc $(1)/usr/sbin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/hbbp_keygen $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,hbbp))

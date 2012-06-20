include $(TOPDIR)/rules.mk

PKG_NAME:=p2ptbl
PKG_VERSION:=20120620
PKG_RELEASE:=1
PKG_REV:=4cfc146c8cc1470dca98a6ea6e4fcf3a5f2378c9

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://code.sotun.de/wrt/p2ptbl
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

include $(INCLUDE_DIR)/package.mk

define Package/p2ptbl
  SECTION:=base
  CATEGORY:=Network
  DEFAULT:=n
  TITLE:=lightweight distributed key-value store
  MAINTAINER:=Jan Huwald <jh@sotun.de>
  URL:=http://code.sotun.de/git/ffj/p2ptbl
  DEPENDS:=+shuf +hbbp +coreutils +coreutils-join
endef

define Package/p2ptbl/description
	P2P tables are a lightweight distributed key-value store with
	built-in collision arbitration. Eventual consistency is maintained
	using a HBBP-based gossip protocol.
endef

define Build/Compile
endef

define Package/p2ptbl/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/p2ptbl $(1)/usr/sbin/
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/p2ptbl-recv $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,p2ptbl))

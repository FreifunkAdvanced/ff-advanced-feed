include $(TOPDIR)/rules.mk

PKG_NAME:=shuf
PKG_VERSION:=20120620
PKG_RELEASE:=1
PKG_REV:=743581225719056a79a378f04ebb44cea1bc3b8e

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://code.sotun.de/wrt/shuf
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

include $(INCLUDE_DIR)/package.mk

define Package/shuf
  SECTION:=base
  CATEGORY:=Utilities
  DEFAULT:=n
  TITLE:=shuffle lines
  MAINTAINER:=Jan Huwald <jh@sotun.de>
  URL:=http://code.sotun.de/git/ffj/shuf
  DEPENDS:=@(!PACKAGE_coreutils-shuf)
endef

define Package/shuf/description
	awk-based variant of coreutils-shuf without any of the original
	command-line parameters
endef

define Build/Compile
endef

define Package/shuf/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/shuf $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,shuf))

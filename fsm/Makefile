include $(TOPDIR)/rules.mk

PKG_NAME:=fsm
PKG_VERSION:=20120620
PKG_RELEASE:=1
PKG_REV:=1ebbdbf807ddee46ab4fbac747e051b432ad8fb7

PKG_SOURCE:=$(PKG_NAME)-$(PKG_REV).tar.gz
PKG_MD5SUM:=always-use-git
PKG_SOURCE_URL:=git://code.sotun.de/ffj/fsm
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE_PROTO:=git

include $(INCLUDE_DIR)/package.mk

define Package/fsm
  SECTION:=base
  CATEGORY:=Utilities
  DEFAULT:=n
  TITLE:=Finite State Machine Interpreter
  URL:=http://code.sotun.de/git/ffj/fsm
  DEPENDS:=+flock
endef

define Package/fsm/description
	Allows to implement FSMs using sets of executables (typically
	shell scripts)
endef

define Build/Compile
endef

define Package/fsm/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/fsm $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,fsm))

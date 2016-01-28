#jq is written in C and has no runtime dependencies, so it should be possible to build it for nearly any platform. Prebuilt binaries are available for Linux, OS X and Windows.
#The binaries should just run, but on OS X and Linux you may need to make them executable first using chmod +x jq.
#jq is licensed under the MIT license. For all of the gory details, read the file COPYING in the source distribution.

include $(TOPDIR)/rules.mk

PKG_NAME:=jq
PKG_VERSION:=1.5
PKG_RELEASE:=

PKG_SOURCE_URL:=https://github.com/stedolan/jq
PKG_SOURCE_PROTO:=git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=1740fd036dc6ab464ef0937a0f3fc81618886837
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

PKG_FIXUP:=autoreconf -i
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/jq
  SECTION:=Utilities
  CATEGORY:=Utilities
  DEPENDS:=
  TITLE:=jq json interface
  URL:=
endef



define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR) CFLAGS=-msoft-float
endef

define Package/jq/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/jq $(1)/usr/bin/
	$(INSTALL_DIR) $(1)/usr/lib
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/lib/* $(1)/usr/lib/
	

endef

$(eval $(call BuildPackage,jq))

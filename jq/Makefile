#jq is written in C and has no runtime dependencies, so it should be possible to build it for nearly any platform. Prebuilt binaries are available for Linux, OS X and Windows.
#The binaries should just run, but on OS X and Linux you may need to make them executable first using chmod +x jq.
#jq is licensed under the MIT license. For all of the gory details, read the file COPYING in the source distribution.

include $(TOPDIR)/rules.mk

PKG_NAME:=jq
PKG_VERSION:=1.5
PKG_RELEASE:=

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/stedolan/jq/releases/download/$(PKG_NAME)-$(PKG_VERSION)/$(PKG_SOURCE)
PKG_MD5SUM:=0933532b086bd8b6a41c1b162b1731f9

PKG_FIXUP:=autoreconf
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
	$(TARGET_CONFIGURE_OPTS) CFLAGS="$(TARGET_CFLAGS) -I$(STAGING_DIR)/usr/include -I$(LINUX_DIR)/include -std=gnu99"  LDFLAGS="$(TARGET_LDFLAGS)" 
	$(MAKE) -C $(PKG_BUILD_DIR)
endef

define Package/jq/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/jq $(1)/usr/sbin
endef

$(eval $(call BuildPackage,jq))

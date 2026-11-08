include $(TOPDIR)/rules.mk

PKG_NAME:=ucode-mod-lvgl
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/tioan/ucode-mod-lvgl.git
PKG_MIRROR_HASH:=skip
PKG_SOURCE_DATE:=2026-11-08
PKG_SOURCE_VERSION:=4b6be68c18126b583ebfc15a66ba7ae1f84b27e3

PKG_BUILD_DEPENDS:=lvgl

PKG_LICENSE:=GPL-2.0-only
PKG_LICENSE_FILES:=LICENSE.txt
PKG_MAINTAINER:=John Crispin <john@phrozen.org>

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

CMAKE_INSTALL:=1

define Package/ucode-mod-lvgl
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=LVGL module for ucode
  DEPENDS:=+libucode +libubox +libdrm
endef

define Package/ucode-mod-lvgl/description
Binds LVGL to ucode, so a user interface for a small DRM display can be written
in ucode rather than in C. Carries no fonts or images: type and artwork are
loaded at run time from files the application ships, with lv.font_load() and
lv.image_load().
endef

define Package/ucode-mod-lvgl/install
	$(INSTALL_DIR) $(1)/usr/lib/ucode $(1)/usr/share/ucode $(1)/usr/share/lvgl
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/ucode/lv.so $(1)/usr/lib/ucode/
	$(CP) $(PKG_INSTALL_DIR)/usr/share/ucode/lvgl $(1)/usr/share/ucode/
	$(CP) $(PKG_INSTALL_DIR)/usr/share/lvgl/. $(1)/usr/share/lvgl/
endef

$(eval $(call BuildPackage,ucode-mod-lvgl))

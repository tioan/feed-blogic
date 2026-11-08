include $(TOPDIR)/rules.mk

PKG_NAME:=glinet-panel-ui
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/tioan/glinet-panel-ui.git
PKG_MIRROR_HASH:=skip
PKG_SOURCE_DATE:=2026-11-08
PKG_SOURCE_VERSION:=b81a3a63e1a806859818ebfefc60722a1e4dbc21

PKG_LICENSE:=GPL-2.0-only OFL-1.1
PKG_LICENSE_FILES:=LICENSE.txt assets/fonts/OFL.txt
PKG_MAINTAINER:=John Crispin <john@phrozen.org>

include $(INCLUDE_DIR)/package.mk

define Package/glinet-panel-ui
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=GL.iNet TFT panel UI
  DEPENDS:=+ucode-mod-lvgl +ucode +ucode-mod-ubus +ucode-mod-uloop \
	+ucode-mod-uci +ucode-mod-fs +ucode-mod-math +ucode-mod-nl80211
endef

define Package/glinet-panel-ui/description
A lvgl based UI for TFT displays on the GL.iNet BE10000 and BE14000
endef

define Build/Compile
endef

define Package/glinet-panel-ui/conffiles
/etc/config/glinet_panel
endef

define Package/glinet-panel-ui/install
	$(INSTALL_DIR) $(1)/usr/share/ucode/glinet-panel-ui/templates $(1)/usr/share/glinet-panel-ui
	$(CP) $(PKG_BUILD_DIR)/ucode/. $(1)/usr/share/ucode/glinet-panel-ui/
	$(CP) $(PKG_BUILD_DIR)/assets/. $(1)/usr/share/glinet-panel-ui/
	$(CP) ./files/. $(1)/
endef

$(eval $(call BuildPackage,glinet-panel-ui))

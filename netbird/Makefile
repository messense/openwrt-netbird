include $(TOPDIR)/rules.mk

PKG_NAME:=netbird
PKG_VERSION:=0.8.2
PKG_RELEASE:=$(AUTORELEASE)

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/netbirdio/netbird/tar.gz/v$(PKG_VERSION)?
PKG_HASH:=6564038f293d1fc27f575deab5e4ce4ee98974542d9e4d59444356835af781a3

PKG_BUILD_DEPENDS:=golang/host
PKG_BUILD_PARALLEL:=1
PKG_USE_MIPS16:=0

GO_PKG:=github.com/netbirdio/netbird
GO_PKG_BUILD_PKG:=github.com/netbirdio/netbird/client
GO_PKG_LDFLAGS:=-s -w
GO_PKG_LDFLAGS_X:=main.Version=v$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/golang/golang-package.mk

define Package/netbird
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=VPN
  TITLE:=Connect your devices into a single secure private WireGuard®-based mesh network
  URL:=https://github.com/netbirdio/netbird
  DEPENDS:=$(GO_ARCH_DEPENDS)
endef

define Package/netbird/install
	$(call GoPackage/Package/Install/Bin,$(PKG_INSTALL_DIR))

	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/client $(1)/usr/bin/netbird

	$(INSTALL_DIR) $(1)/etc/init.d/
	$(INSTALL_BIN) $(CURDIR)/files/netbird.init $(1)/etc/init.d/netbird
endef

$(eval $(call GoBinPackage,netbird))
$(eval $(call BuildPackage,netbird))

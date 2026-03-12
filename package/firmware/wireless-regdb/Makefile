include $(TOPDIR)/rules.mk

PKG_NAME:=wireless-regdb
PKG_VERSION:=2026-03-13
PKG_RELEASE:=1
PKG_LICENSE:=ISC
PKG_LICENSE_FILES:=LICENSE

PKG_SOURCE_URL:=https://github.com/aon3ko/wireless-regdb
PKG_SOURCE_PROTO:=git
PKG_SOURCE_DATE:=2026-03-13
PKG_SOURCE_VERSION:=986cca1314262424933e5e454b59895b83f0acdc
PKG_MIRROR_HASH:=skip

PKG_MAINTAINER:=Felix Fietkau <nbd@nbd.name>

include $(INCLUDE_DIR)/package.mk

define Package/wireless-regdb
  PKGARCH:=all
  SECTION:=firmware
  CATEGORY:=Firmware
  URL:=https://github.com/aon3ko/wireless-regdb
  TITLE:=Wireless Regulatory Database
endef

define Build/Compile
	true
endef

define Package/wireless-regdb/install
	$(INSTALL_DIR) $(1)/lib/firmware
	$(INSTALL_DATA) $(PKG_BUILD_DIR)/regulatory.db $(1)/lib/firmware/
	[ -f $(PKG_BUILD_DIR)/regulatory.db.p7s ] && $(INSTALL_DATA) $(PKG_BUILD_DIR)/regulatory.db.p7s $(1)/lib/firmware/ || true
	[ -f $(PKG_BUILD_DIR)/regulatory.bin ] && $(INSTALL_DATA) $(PKG_BUILD_DIR)/regulatory.bin $(1)/lib/firmware/ || true
endef

$(eval $(call BuildPackage,wireless-regdb))

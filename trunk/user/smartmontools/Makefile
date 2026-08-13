include $(ROOTDIR)/rules.mk

PKG_NAME:=smartmontools
PKG_VERSION:=7.4

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/smartmontools/smartmontools/releases/download/RELEASE_7_4/

include $(INCLUDE_DIR)/package.mk

CONFIGURE_ARGS += \
	--without-libcap-ng \
	--without-selinux \
	--without-libsystemd \
	--without-gnupg \
	--without-update-smart-drivedb

$(eval $(call BuildPackage,smartmontools))

romfs:
	$(INSTALL_DIR) $(ROMFSDIR)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/smartctl $(ROMFSDIR)/usr/sbin/smartctl

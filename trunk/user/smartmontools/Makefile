include $(ROOTDIR)/rules.mk

PKG_NAME:=smartmontools
PKG_VERSION:=7.4

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/smartmontools/smartmontools/releases/download/RELEASE_7_4/
PKG_HASH:=e9a61f641ff96ca95319edfb17948cd297d0cd3342736b2c49c99d4716fb993d

include $(INCLUDE_DIR)/package.mk

TARGET_LDFLAGS += -static-libstdc++

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

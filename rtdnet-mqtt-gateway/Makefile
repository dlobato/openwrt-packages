#
# Copyright (C) 2011-2013 OpenWrt.org
# Copyright (C) 2010 Jo-Philipp Wich <xm@subsignal.org>
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=rtdnet-mqtt-gateway
PKG_VERSION:=0.0.1
PKG_RELEASE:=1
PKG_SOURCE_VERSION:=master


PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_RELEASE).tar.xz
PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/dlobato/rtdnet-mqtt-gateway.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_RELEASE)
PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)-$(PKG_RELEASE)

include $(INCLUDE_DIR)/package.mk

define Package/rtdnet-mqtt-gateway
    SECTION:=net
    CATEGORY:=Network
    TITLE:= RTD-NET <-> MQTT Gateway
    DEPENDS+=+libmosquitto-ssl +libmodbus +libjson-c
endef

define Package/rtdnet-mqtt-gateway/description
    RTD-NET <-> MQTT Gateway
endef

define Package/rtdnet-mqtt-gateway/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/rtdnet-mqtt-gateway $(1)/usr/bin/rtdnet-mqtt-gateway
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/rtdnet-status $(1)/usr/bin/rtdnet-status
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/src/rtdnet-set-temp $(1)/usr/bin/rtdnet-set-temp
endef

MAKE_FLAGS += UNAME=Linux

$(eval $(call BuildPackage,rtdnet-mqtt-gateway))

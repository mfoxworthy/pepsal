# 
# Copyright (C) 2006-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=pepsal
PKG_VERSION:=v2.0.1-pre
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/mfoxworthy/pepsal/archive/refs/tags/
PKG_MD5SUM:=skip
PKG_MAINTAINER:=Michael Foxworthy <mike.foxworthy@viasat.com>

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/pepsal
	TITLE:=Performance Enhancing Proxy
	SECTION:=net
	CATEGORY:=Network
	URL:=https://github.com/mfoxworthy/pepsal
	DEPENDS:=+libmnl +libnfnetlink +libnetfilter-queue
endef

define Package/pepsal/description
	PEPsal is an integrated, multi-layer, transparent TCP Performance Enhancing 
	Proxy which splits the connection into two parts, making use of Linux TCP 
	enhancements when sending data, and largely improving performance in 
	links with different characteristics 
endef

define Build/Configure
	( cd $(PKG_BUILD_DIR); ./autogen.sh )
	$(call Build/Configure/Default)
endef

define Package/pepsal/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/pepsal $(1)/usr/bin/
endef

$(eval $(call BuildPackage,pepsal))

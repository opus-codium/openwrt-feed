#
# Copyright (C) 2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=lua-struct
PKG_VERSION:=0.2
PKG_RELEASE:=1
PKG_MAINTAINER:=Romuald Conty <romuald@opus-codium.fr>

PKG_SOURCE_NAME:=struct
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_SOURCE_NAME)-$(PKG_VERSION)

PKG_SOURCE:=$(PKG_SOURCE_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://www.inf.puc-rio.br/~roberto/$(PKG_SOURCE_NAME)
PKG_MD5SUM:=99384bf1f54457ec9f796ad0b539d19c

include $(INCLUDE_DIR)/package.mk

define Package/lua-struct
  SUBMENU:=Lua
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=Lua struct library
  URL:=http://www.inf.puc-rio.br/~roberto/struct/
  DEPENDS:=+liblua
  MAINTAINER:=roberto
endef

define Build/Prepare
	$(TAR) -xvf $(DL_DIR)/$(PKG_SOURCE) -C $(PKG_BUILD_DIR)
endef

define Package/lua-struct/description
	Library for Converting Data to and from C Structs for Lua 5.1/5.2
endef

define Package/lua-struct/install
	$(INSTALL_DIR) $(1)/usr/lib/lua
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/struct.so $(1)/usr/lib/lua
endef

$(eval $(call BuildPackage,lua-struct))

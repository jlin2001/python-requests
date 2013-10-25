include $(TOPDIR)/rules.mk

PKG_NAME:=python-requests
PKG_VERSION:=master

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=git://github.com/kennethreitz/requests.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE:=$(PKG_NAME).tar.gz

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)
PKG_BUILD_DEPENDS:=python

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-requests
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:=python-requests
  URL:=http://www.python-requests.org
  DEPENDS:=+python
endef

define Package/python-requests/description
  Requests is an elegant and simple HTTP library for Python, built for human beings.
endef

define Build/Compile
	$(call Build/Compile/PyMod,., \
		install --prefix="/usr" --root="$(PKG_INSTALL_DIR)" \
	)
endef

define Package/python-requests/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,python-requests))

PKG_CONFIG_DEPENDS:= \
	CONFIG_TARGET_ramips

include $(INCLUDE_DIR)/package.mk

define Package/automount
  TITLE:=Mount autoconfig hotplug script.
  MAINTAINER:=Lean
  DEPENDS:= \
    +kmod-usb3 \
    +kmod-usb2 \
    +luci-app-diskman \
    +luci-app-partexp \
    +block-mount \
    +e2fsprogs \
    +kmod-usb-storage \
    +kmod-usb-storage-extras \
    +!TARGET_ramips:kmod-usb-storage-uas \
    +kmod-fs-ext4 \
    +kmod-fs-exfat \
    +kmod-fs-vfat \
    +ntfs3-mount
  PKGARCH:=all
endef

define Package/ntfs3-mount
  SECTION:=utils
  CATEGORY:=Utilities
  SUBMENU:=Filesystem
  TITLE:=NTFS mount script for Paragon NTFS3 driver
  DEPENDS:=+kmod-fs-ntfs3
  CONFLICTS:=ntfs-3g
  VARIANT:=ntfs3-mount
  PKGARCH:=all
endef

define Build/Compile
endef

define Package/automount/install
endef

define Package/ntfs3-mount/install
	$(INSTALL_DIR) $(1)/sbin
	$(INSTALL_BIN) ./files/mount.ntfs $(1)/sbin
endef

$(eval $(call BuildPackage,automount))

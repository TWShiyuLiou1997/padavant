include $(ROOTDIR)/rules.mk

PKG_NAME:=scripts

include $(INCLUDE_DIR)/package.mk

define Build/Prepare
	$(CP) ./files $(PKG_BUILD_DIR)/
    
    # 🌟 新增：移除不需要的腳本
    # 這些腳本已經被複製到臨時構建目錄 (PKG_BUILD_DIR)，現在將其刪除。
    rm -f $(PKG_BUILD_DIR)/files/usr/bin/autostart.sh
    rm -f $(PKG_BUILD_DIR)/files/usr/bin/copyscripts.sh
    
	mkdir -p $(PKG_BUILD_DIR)/files/usr/share/terminfo
	tar -xzf ./terminfo.tar.gz -C $(PKG_BUILD_DIR)/files/usr/share
endef

define Build/Configure
endef

define Build/Compile
endef

$(eval $(call BuildPackage,scripts))

romfs:
	fakeroot ./makedevlinks $(ROMFSDIR)
	$(CP) $(PKG_BUILD_DIR)/files/* $(ROMFSDIR)/
ifneq ($(STORAGE_ENABLED),y)
	rm -f $(ROMFSDIR)/sbin/automount.sh
endif
ifndef CONFIG_BLK_DEV_SD
	rm -f $(ROMFSDIR)/sbin/hddtune.sh
	rm -f $(ROMFSDIR)/sbin/spindown.sh
endif
ifndef CONFIG_MTD_UBI
	rm -f $(ROMFSDIR)/sbin/rwfs2ubi.sh
endif

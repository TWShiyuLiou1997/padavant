include $(ROOTDIR)/rules.mk

PKG_NAME:=ralinkiappd

include $(INCLUDE_DIR)/package.mk

# 🌟 步驟 1: 註釋掉 BuildPackage 呼叫。
# 這是最關鍵的一步，它會從根本上阻止編譯系統處理 ralinkiappd 的所有編譯和安裝定義。
# $(eval $(call BuildPackage,ralinkiappd))

romfs:
# 🌟 步驟 2: 註釋掉 romfs 目標下的所有安裝指令。
# 這是一個防禦性步驟，確保即使 BuildPackage 步驟被跳過，也沒有任何檔案會被安裝。
#	$(INSTALL_DIR) $(ROMFSDIR)/sbin
#	$(INSTALL_BIN) $(PKG_BUILD_DIR)/ralinkiappd $(ROMFSDIR)/sbin/ralinkiappd
#	$(INSTALL_DIR) $(ROMFSDIR)/usr/bin
#	$(INSTALL_BIN) ./iappd.sh $(ROMFSDIR)/usr/bin/iappd.sh

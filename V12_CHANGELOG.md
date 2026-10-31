# CleanYourTV V12 修改紀錄

本版以使用者上傳的 `cleanyourtv-main` 原始碼為基礎，保留既有 Launcher 架構與操作流程。

## 已整合

1. **A+ 圓角啟動器圖標**
   - 新增 Android 8.0 以上 Adaptive Icon。
   - 新增不同 DPI 的 PNG 備援圖標。
   - 圖標採圓角外觀，並在 Manifest 設定 `icon` 與 `roundIcon`。
2. **桌面顯示／隱藏 APP**
   - 設定選單名稱改為「桌面顯示」。
   - 取消勾選的 APP 會從桌面隱藏。
   - 隱藏狀態同步套用到「系統」及一般資料夾內容。
   - 資料夾封面縮圖也不再顯示已隱藏 APP。
3. **桌面顯示視窗**
   - 加寬 APP 勾選清單，並保留螢幕邊界。
4. **新增資料夾欄位**
   - 輸入欄位外側增加左右留白，不再貼齊視窗邊緣。
5. **資料夾展開視窗與格子**
   - 「系統」及一般資料夾展開視窗加寬。
   - APP 格子調整為正方形，焦點放大比例一致。
   - 一般資料夾與「系統」資料夾都提供「＋」新增 APP。
6. **無 TV Banner APP 背景色**
   - 桌面無 Banner APP 沿用該 APP 最後設定的背景色。
   - 資料夾內無 Banner APP 與資料夾封面縮圖也沿用該 APP 背景色。
   - 沒有自訂顏色時使用預設深色底。
   - 有 TV Banner 的 APP 仍顯示 Banner。

## 驗證狀態

- XML：110 個檔案完成 XML 格式解析，未發現格式錯誤。
- Java：修改檔案完成括號結構檢查；`javac` 未回報語法型錯誤。
- **APK 尚未完成建置**：目前執行環境沒有 Android SDK，Gradle Wrapper 需要下載 Gradle 8.9，但環境無法連線至 `services.gradle.org`。因此本 ZIP 是已修改的原始碼專案，不是已編譯 APK，也未宣稱完成實機測試。

## 建置方式

使用 Android Studio 開啟 `launcher` 資料夾，安裝專案要求的 Android SDK 後，執行 `:app:assembleRelease` 建置 Release APK。

\n## 追加修正（資料夾 APP 長按一致化）\n\n7. **資料夾內 APP 長按選單**\n   - 系統／一般資料夾內長按 APP，改用與桌面 APP 相同風格的設定選單。\n   - 支援修改名稱、全域名稱顯示、更換圖標、調整圖標大小、自訂背景色、還原 APP 設定及開啟 APP 資訊。\n   - 另保留資料夾專用的「移出資料夾／移出系統資料夾」操作。\n   - 在資料夾內修改圖標、大小或背景色後，會重新開啟資料夾並更新顯示。\n8. **資料夾圖標呈現一致化**\n   - 資料夾內 APP 支援自訂圖標與明確圖標尺寸設定。\n   - 無 TV Banner APP 的預設背景改為與桌面一致的白色；已自訂背景色則沿用最後設定。\n   - 資料夾 APP 與「＋」卡片採相同焦點縮放比例，X/Y 同步縮放並維持正方形。\n   - 資料夾展開視窗最大寬度由 640dp 調整為 760dp，並增加卡片間距。\n   - 「桌面顯示」清單最大寬度同步調整為 760dp。\n\n## 本次追加檢查\n\n- MainActivity.java 與 AppAdapter.java 括號／括號層級結構檢查通過。\n- launcher/app/src/main 下 110 個 XML 檔案皆可正常解析。\n- **尚未執行 Android Gradle 編譯**：目前容器沒有 Android SDK、ADB、Gradle，亦沒有可用的 Gradle 8.9 快取；因此本次交付仍是更新後的原始碼 ZIP，不是 APK。\n
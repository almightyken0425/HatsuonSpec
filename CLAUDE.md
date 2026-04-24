# CLAUDE.md

本 repo 為 Hatsuon 產品的 **Module Spec git**，module_id 為 `no1_pronunciation_app`，承載日文發音練習 App 的行為規格。

## 三層 git 配對

- **頂層 Product git：**
    - 位於 `../../`
- **本 Module Spec git：**
    - 即本 repo
    - 位於 Product git 的 `no3_product_specs/no1_pronunciation_app/`
- **對側 Module Impl git：**
    - 位於 Product git 的 `no5_product_development/no1_pronunciation_app/`
    - React Native Expo 發音練習 App

完整路徑與配對表由 `decision_framework_router` skill 的 `products_registry.md` 維護。

---

## 產品機制

Hatsuon 是日文五十音刷題工具，支援平假名與片假名兩條獨立主線，核心機制為自適應出題的無限刷題模式。App 採底部導航列，含字元總覽與平假名、片假名練習三個 tab。

---

## Spec 分層

Spec 按決策框架 Model / View / Logic 分三層。

- **Model 層：** `no1_data_models/`
    - `no1_kana_data.md` — 完整五十音字元表，含清音、濁音、半濁音、拗音、促音、長音符
    - `no2_component_spec.md` — 構成元素規格，定義識別碼與字元分解規則
    - `no3_set_map.md` — 逐行解鎖題組定義，每個題組對應的字元集合
- **View 層：** `no2_screens/`
    - `no1_character_reference_screen.md` — 字元總覽畫面，預設首頁
    - `no2_practice_screen.md` — 練習畫面，難度選擇
    - `no3_drill_screen.md` — 刷題畫面，含答題狀態機
    - `no4_lesson_list_screen.md` — 題組列表畫面
- **Logic 層：** `no3_logics/`
    - `no1_drill_engine.md` — 刷題引擎、自適應演算法、session 管理
    - `no2_audio_module.md` — 發音觸發規則
    - `no3_ad_module.md` — 廣告觸發條件與行為
    - `no4_progress_module.md` — 題組進度追蹤

---

## 撰寫規範

所有規格文件依循以下分層政策。

- Model 層套用 `spec_writer` 的 model 政策
- View 層套用 `spec_writer` 的 screen 政策
- Logic 層套用 `spec_writer` 的 logic 政策
- 所有 .md 額外套用 `universal_writing_linter` 通用政策

---

## 歷史

本 repo 由原 HatsuonSpec 的 `no2_content_spec/`、`no3_module_specs/`、`no4_screen_specs/` 三個目錄合併重組而來，對齊 SuSuGiGi 決策框架風格。

---

## 配對變動規則

Spec 變動時通常需要三層聯動檢查。

- 對側 Impl 需檢查對應實作
- 上游 Product Map 目前為 placeholder，待補
- 需求層目前為 placeholder，待補

配對 commit 使用相同 subject 與 body，branch 名稱逐字一致。

# Hatsuon 發音 App Spec 規則

- 本 repo 是 Module Spec git
- 產品為 Hatsuon
- module id 為 `no1_pronunciation_app`
- 本 repo 承載行為規格

## 多層配對

- Product git 承載上游決策
- Design git 尚未建立
- 本 repo 是 Spec 仲裁端
- Impl git 承載 React Native Expo App
- 配對以 `decision_framework_router` 的註冊表為準

---

## 產品機制

- 產品是日文五十音刷題工具
- 平假名與片假名各自獨立
- 核心為自適應無限刷題
- 導航含字元總覽與兩類練習

---

## Spec 分層

- `no1_data_models/`
  - 承載字元與題組資料
  - 套用 `spec_writer` Model 政策
- `no2_screens/`
  - 承載總覽與練習畫面
  - 套用 `spec_writer` Screen 政策
- `no3_logics/`
  - 承載刷題與進度行為
  - 套用 `spec_writer` Logic 政策

---

## 原生工作規則

- 任何改動先使用 `decision_framework_router`
- 所有 Spec 改動使用 `spec_writer`
- Markdown 改動使用 `universal_writing_linter`
- Spec 變動要檢查 Impl
- 上游需求與 Product Map 已建立
- Design 建立後要加入配對檢查
- 跨層 branch 名稱必須一致
- 配對 commit 內容必須一致

---

## 相容與漂移控制

- `AGENTS.md` 是本目錄的規則真相
- `CLAUDE.md` 只保留 Claude Code 入口
- 產品規則不得複製回相容入口
- 漂移檢查確認相容入口只含導向規則

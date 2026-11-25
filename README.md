# 世界模型（World Models）入門：LLM Wiki 與教學簡報

這個專案用「LLM Wiki」（一組互相連結的 Markdown 檔案）整理「AI 的世界模型」，再只用 Wiki 的內容產生一份給初學者的 HTML 簡報。

**世界模型**是什麼：AI 內部對「世界會怎麼運作、接下來會怎麼變」的模型，讓它可以先在腦中預測、規劃，不必每件事都真的試過。主要內容包括：定義、為什麼重要、核心概念（潛在表示、預測、規劃、在想像中學習）、代表模型，以及「生成式 vs 潛在（非生成式）」兩條技術路線的對比。

## 連結（請自行填寫）

| 項目 | 連結 |
|---|---|
| GitHub repo | [https://github.com/4b417052/world-model-wiki](https://github.com/4b417052/world-model-wiki) |
| Wiki 入口（wiki/index.md） | [https://github.com/4b417052/world-model-wiki/tree/main/wiki](https://github.com/4b417052/world-model-wiki/tree/main/wiki) |
| 簡報（GitHub Pages） | [https://4b417052.github.io/world-model-wiki/slides/](https://4b417052.github.io/world-model-wiki/slides/) |

## 資料夾結構

```
world-model-wiki/
├── README.md        本檔
├── raw/             原始材料
│   ├── links.md       9 篇來源的連結、取用日期、來源性質、閱讀狀態
│   └── notes/         每篇一份 raw 筆記（自己的話，每篇 ≤200 字）
├── wiki/
│   ├── index.md       目錄、證據標籤定義、建議閱讀順序
│   ├── sources/       9 個來源頁（S1–S9）
│   └── concepts/      12 個概念頁（每頁列出依據的來源頁）
├── slides/
│   └── index.html     單一檔案簡報（樣式與腳本內嵌，不需網路）
├── log.md           每個階段與每一輪檢查的紀錄（含簡報 v1 的問題）
└── workflow.md      工作流程圖與設計理由
```

## 怎麼讀

1. 想快速理解：開啟 `slides/index.html`（方向鍵或畫面按鈕換頁）。
2. 想看依據：從 `wiki/index.md` 進入，概念頁會列出它依據的來源頁，簡報每頁底部也標了出處。
3. 想看過程：`log.md`（每輪問題與修正）、`workflow.md`（流程設計）。

## 證據類型標籤

Wiki 與簡報都區分說法的證據強度，例如〔論文實證〕、〔公司宣稱〕、〔立場觀點〕等，完整定義見 `wiki/index.md`。看到標籤時請注意：公司宣稱和立場觀點不等於已被實驗證實。

## 已知限制

- 來源為 9 篇（論文、公司報告與部落格、一篇立場論文、一篇綜述）；S8 綜述與 S2 部分章節只讀了標題或摘要，詳見各來源頁。
- 簡報通過獨立審查（17 輪），但仍留有低嚴重度建議：少數名詞（如「感測器」「世界模擬器」）未就地解釋、部分徽章顏色對比略低、Wiki 內有數處用詞不一致。詳見 `log.md` 第 17 輪。

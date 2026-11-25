# S6｜Genie 3: A new frontier for world models（Google DeepMind, 2025）

> ⚠ **來源性質：公司部落格（公司宣稱）。**
> Genie 3 在發表時是研究預覽，沒有公開給大眾，也沒有附論文。文中的能力描述來自官方示範，無法獨立驗證。

| 欄位 | 內容 |
|---|---|
| 作者／機構 | Jack Parker-Holder、Shlomi Fruchter（Google DeepMind） |
| 年份 | 2025-08-05 |
| 連結 | https://deepmind.google/blog/genie-3-a-new-frontier-for-world-models/ |
| 來源性質 | **公司部落格** |
| 閱讀狀態 | 已讀原文 |
| raw 筆記 | [raw/notes/s6-deepmind-genie3-2025.md](../../raw/notes/s6-deepmind-genie3-2025.md) |
| 取用日期 | 2026-11-25 |

## 摘要
Genie 3 被定位為「通用世界模型」：輸入一段文字描述，就能產生使用者可以**即時操作、走進去探索**的動態世界。

## 重點
1. **規格（官方數據）**：每秒 24 格、720p，一致性可維持數分鐘。DeepMind 表示這是他們第一個能即時互動的世界模型，一致性和真實感也比 Genie 2 好。
2. **逐格生成與記憶**：畫面是一格一格「自迴歸」（auto-regressive）產生的，每一格都要參考之前生成、而且越來越長的整段軌跡。例如使用者一分鐘後回到某個地點，模型必須想起一分鐘前那裡的樣子。
3. **可提示的世界事件**（promptable world events）：除了移動操作，還可以用文字改變正在生成的世界。
4. **為什麼重要（DeepMind 的主張）**
   - 世界模型讓 AI 智慧體能在「無限多樣、豐富的模擬環境」中訓練，DeepMind 視之為通往 AGI 的墊腳石。
   - 智慧體能預測環境會怎麼變，以及自己的行動會怎麼改變環境。
   - 「如果……會怎樣」的情境，可以幫智慧體準備好面對意外。
5. **官方列出的限制**
   - 智慧體能直接做的動作範圍有限。
   - 多個獨立智慧體在同一環境中的複雜互動，仍是未解的研究問題。
   - 無法精確重現真實地點的地理。
   - 清楚的文字通常只有在輸入描述中寫明時才會出現。
   - 只能連續互動幾分鐘，不是幾小時。

## 被以下概念頁引用
- [interactive-world-model](../concepts/interactive-world-model.md)
- [generative-vs-latent](../concepts/generative-vs-latent.md)
- [video-world-simulator](../concepts/video-world-simulator.md)
- [learning-in-imagination](../concepts/learning-in-imagination.md)
- [prediction-dynamics](../concepts/prediction-dynamics.md)
- [applications](../concepts/applications.md)
- [limitations](../concepts/limitations.md)

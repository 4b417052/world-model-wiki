# S8｜Understanding World or Predicting Future? A Comprehensive Survey of World Models（Ding et al.）

| 欄位 | 內容 |
|---|---|
| 作者／機構 | Jingtao Ding、Yunke Zhang、Yu Shang、Jie Feng 等（清華大學 FIB Lab） |
| 年份 | 2024-11 v1；ACM Computing Surveys 接受；2025-12 v4 為擴充版 |
| 連結 | https://arxiv.org/abs/2411.14499 ・論文清單 https://github.com/tsinghua-fib-lab/World-Model |
| 來源性質 | **綜述論文（survey）**：整理他人研究，本身不做新實驗 |
| 閱讀狀態 | 已讀摘要與 HTML v4 前段；挑戰章節只讀到標題（內文過長被截斷） |
| raw 筆記 | [raw/notes/s8-ding-survey-2024.md](../../raw/notes/s8-ding-survey-2024.md) |
| 取用日期 | 2026-11-25 |

## 摘要
2024 年多模態大型語言模型和 Sora 等影片生成模型出現後，「世界模型」引起廣泛討論。這篇綜述把世界模型的功能分成兩大類：**理解現在**（建立內部表示）與**預測未來**（模擬世界演變），並整理各領域的應用與挑戰。

## 重點
1. **定義仍有爭議**：世界模型的定義大致分成「理解世界」與「預測未來」兩種觀點。
   - Ha 與 Schmidhuber 的早期工作偏向把外部世界抽象化，以理解其機制（[S1](s1-ha-schmidhuber-2018-world-models.md)）。
   - Sora 這類影片生成模型偏向「預測」（[S5](s5-openai-sora-2024.md)）。
   - LeCun 主張世界模型除了感知與建模真實世界，還要能想像可能的未來，以支援決策（[S2](s2-lecun-2022-path-towards-ami.md)）。
2. **兩大類別**
   - **外部世界的隱式表示**：有模型強化學習（例如 Dreamer、使用蒙地卡羅樹搜尋的規劃器）、以語言模型為骨幹的世界模型、模型中的世界知識。
   - **物理世界的未來預測**：影片世界模型（例如 Sora、Cosmos、Genie）、具身環境（給智慧體訓練用的模擬環境）。
3. **應用**
   - **自動駕駛**：即時感知路況，並預測交通會怎麼演變。
   - **機器人**：導航、物體偵測、任務規劃。
   - **社會模擬**：模擬社會互動與人類決策。
4. **對影片模型的保留**：這類模型展現了部分世界知識（例如 Sora 的影片看起來符合物理），但它們是否真的算得上完整的世界模型，仍有疑問。
5. **待解挑戰（章節標題）**：物理規則與反事實模擬、社會面向、評測基準、以具身智慧銜接模擬與現實、模擬效率、倫理與安全。

## 被以下概念頁引用
- [world-model](../concepts/world-model.md)
- [generative-vs-latent](../concepts/generative-vs-latent.md)
- [video-world-simulator](../concepts/video-world-simulator.md)
- [applications](../concepts/applications.md)
- [limitations](../concepts/limitations.md)

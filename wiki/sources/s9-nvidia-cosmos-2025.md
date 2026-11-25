# S9｜Cosmos World Foundation Model Platform for Physical AI（NVIDIA, 2025）

> ⚠ **來源性質：公司技術報告。**
> 發表在 arXiv，附有實驗並開放模型權重，可驗證程度比 S5、S6 高。但文中「物理準確」這類整體評價仍屬公司宣稱，本 Wiki 會區分標示。

| 欄位 | 內容 |
|---|---|
| 作者／機構 | NVIDIA（Niket Agarwal 等 77 位作者） |
| 年份 | 2025-01-07 v1；2025-07-09 v3 |
| 連結 | https://arxiv.org/abs/2501.03575 ・https://research.nvidia.com/publication/2025-01_cosmos-world-foundation-model-platform-physical-ai |
| 來源性質 | **公司技術報告**（開源程式與開放權重） |
| 閱讀狀態 | 已讀 arXiv 摘要與 HTML 前段 |
| raw 筆記 | [raw/notes/s9-nvidia-cosmos-2025.md](../../raw/notes/s9-nvidia-cosmos-2025.md) |
| 取用日期 | 2026-11-25 |

## 摘要
NVIDIA 認為，**實體 AI 要先在數位世界裡訓練**：它需要自己的數位分身（策略模型），也需要世界的數位分身（世界模型）。Cosmos 是一個平台，幫開發者建立適合自己實體 AI 場景的客製化世界模型。

## 重點
1. **實體 AI（Physical AI）是什麼**：配有感測器和致動器的 AI 系統。感測器用來觀察世界，致動器用來和世界互動、改變世界，例如機器人和自駕車。
2. **為什麼需要世界模型**：實體 AI 進步很慢，主要是訓練資料難以擴大。資料必須是「觀察與行動交錯」的序列，而在真實世界裡做動作，可能弄壞系統或環境。世界模型就像一個可以安全互動的世界數位分身。
3. **先預訓練、再後訓練**
   - **預訓練**：用大規模、多樣的影片，讓「世界基礎模型」（World Foundation Model, WFM）成為通才。資料管線從 2,000 萬小時的影片中切出約 1 億段 2–60 秒的片段。
   - **後訓練**：用目標場景收集的小量資料，把通才模型調整成專用模型。提示可以是動作指令、軌跡或文字指示。
4. **兩種模型**：Transformer 擴散模型（用連續的向量 token）和 Transformer 自迴歸模型（用離散的整數 token）。兩者都要先用「影片分詞器」（tokenizer）把影片轉成 token。
5. **應用範例**：機器人操作、自動駕駛場景等。
6. **公司宣稱**：報告稱預訓練模型能產生「3D 一致、物理準確」的高品質影片。這是 NVIDIA 的自我評價。
7. **開放**：平台開源，模型以寬鬆授權開放權重。

## 被以下概念頁引用
- [video-world-simulator](../concepts/video-world-simulator.md)
- [generative-vs-latent](../concepts/generative-vs-latent.md)
- [interactive-world-model](../concepts/interactive-world-model.md)
- [learning-in-imagination](../concepts/learning-in-imagination.md)
- [latent-representation](../concepts/latent-representation.md)
- [applications](../concepts/applications.md)
- [limitations](../concepts/limitations.md)

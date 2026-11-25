# S7｜V-JEPA 2: Self-Supervised Video Models Enable Understanding, Prediction and Planning（Meta, 2025）

| 欄位 | 內容 |
|---|---|
| 作者／機構 | Mido Assran 等 30 位作者（Meta FAIR、Mila） |
| 年份 | 2025-06-11 |
| 連結 | https://arxiv.org/abs/2506.09985 ・部落格 https://ai.meta.com/blog/v-jepa-2-world-model-benchmarks/ ・程式碼 https://github.com/facebookresearch/vjepa2 |
| 來源性質 | **研究論文（arXiv 預印本，附實驗與開源模型）＋公司部落格**。實驗數據視為論文實證；部落格中的應用展望（例如穿戴式助理）視為公司宣稱 |
| 閱讀狀態 | 已讀 arXiv 摘要與 HTML 前段、官方部落格 |
| raw 筆記 | [raw/notes/s7-meta-vjepa2-2025.md](../../raw/notes/s7-meta-vjepa2-2025.md) |
| 取用日期 | 2026-11-25 |

## 摘要
這是 LeCun JEPA 構想（[S2](s2-lecun-2022-path-towards-ami.md)）的實作。研究結合網路規模的影片資料和**少量**機器人互動資料，訓練出能在物理世界中理解、預測和規劃的世界模型。

## 重點
1. **架構**：12 億參數。編碼器把影片轉成抽象的「嵌入」（embedding），預測器在這個抽象空間裡，用過去預測未來的嵌入，**不預測像素**。
2. **兩階段訓練**
   - **階段一（不含行動）**：用超過 100 萬小時的影片和 100 萬張圖片做自監督學習，學到人如何與物體互動、物體如何移動。
   - **階段二（加入行動）**：用不到 62 小時、沒有標註的機器人影片（Droid 資料集）後訓練出 V-JEPA 2-AC，讓預測器知道「做了什麼動作」。
3. **用目標圖片規劃**
   - 把目前狀態和目標圖片都編碼成嵌入。
   - 預測器想像多組候選動作序列的結果，依「離目標多近」排序。
   - 執行排第一的下一步動作，然後在每一步重新規劃，也就是模型預測控制（model-predictive control）。
   - 長任務則依序追求一連串的視覺子目標。
4. **成果（論文實證）**
   - 在兩個實驗室的 Franka 機械手臂上「零樣本」部署，也就是沒有在那些環境收集資料。
   - 用視覺子目標時，對新物體、新環境的抓放任務成功率為 65%–80%。
   - 接上大型語言模型後，在影片問答基準達到同規模最佳（PerceptionTest 84.0、TempCompass 76.9）。
5. **新物理推理基準與人類差距**
   - IntPhys 2：判斷影片是否違反物理。目前的影片模型表現接近亂猜。
   - MVPBench、CausalVQA：模型能回答「發生了什麼」，但對「本來可能發生什麼」「接下來會怎樣」表現差。
   - 人類在這三個基準上有 85%–95%，頂尖模型（包含 V-JEPA 2）仍明顯落後。
6. **限制與未來**：V-JEPA 2 只在**單一時間尺度**上學習和預測，但很多任務需要跨尺度規劃。未來方向是階層式 JEPA，以及結合視覺、聽覺、觸覺的多模態 JEPA。

## 被以下概念頁引用
- [latent-representation](../concepts/latent-representation.md)
- [prediction-dynamics](../concepts/prediction-dynamics.md)
- [planning](../concepts/planning.md)
- [generative-vs-latent](../concepts/generative-vs-latent.md)
- [video-world-simulator](../concepts/video-world-simulator.md)
- [interactive-world-model](../concepts/interactive-world-model.md)
- [applications](../concepts/applications.md)
- [limitations](../concepts/limitations.md)

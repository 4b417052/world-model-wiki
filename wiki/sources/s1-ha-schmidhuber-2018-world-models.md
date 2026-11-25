# S1｜World Models（Ha & Schmidhuber, 2018）

| 欄位 | 內容 |
|---|---|
| 作者／機構 | David Ha（Google Brain）、Jürgen Schmidhuber（IDSIA／NNAISENSE） |
| 年份 | 2018（arXiv 3 月；NeurIPS 2018 口頭報告版題為 *Recurrent World Models Facilitate Policy Evolution*） |
| 連結 | https://arxiv.org/abs/1803.10122 ・互動版 https://worldmodels.github.io/ |
| 來源性質 | **研究論文（論文實證）**：有可重現的實驗與數據 |
| 閱讀狀態 | 已讀原文（arXiv／ar5iv、互動版） |
| raw 筆記 | [raw/notes/s1-ha-schmidhuber-2018.md](../../raw/notes/s1-ha-schmidhuber-2018.md) |
| 取用日期 | 2026-11-25 |

## 摘要
這篇論文讓「世界模型」這個詞在深度學習界流行起來。作者先用非監督方式訓練一個生成式神經網路，讓它學會遊戲環境在空間和時間上的**壓縮表示**。再把這些特徵交給一個非常小的控制器做決策。他們還讓智慧體完全在模型自己產生的「夢」中訓練，再把學到的策略搬回真實遊戲。

## 重點
1. **V–M–C 三元件**
   - **V（Vision，視覺）**：變分自編碼器（Variational Autoencoder, VAE），把 64×64 的畫面壓成小向量 z（賽車任務 32 維，VizDoom 64 維）。
   - **M（Memory，記憶）**：LSTM 搭配混合密度網路（Mixture Density Network），預測下一個 z 的**機率分布**。它的隱藏狀態 h 帶有「對未來的預測」。
   - **C（Controller，控制器）**：單層線性層，只有 867 個（賽車）或 1,088 個（VizDoom）參數，用演化策略 CMA-ES 訓練。
2. **賽車（CarRacing）結果**：完整模型在 100 條賽道上平均 906 ± 21 分，超過「解題」門檻 900 分，也高於當時排行榜最佳的 838 分和傳統深度強化學習的 591–652 分。只給 C 看 z、不給 h，只有 632 ± 251 分。可見「對未來的預測」讓駕駛穩定得多。
3. **在夢中訓練（VizDoom Take Cover）**：這個任務要躲開怪物射來的火球，以存活時間為獎勵，分數就是存活的步數（互動版原文：獎勵是存活時間，平均 750 步算解題）。下文溫度實驗的「分」也是存活步數。（2026-11-25 補：依互動版 worldmodels.github.io 中「躲火球」「怪物發射」的描述加入。）智慧體完全在 M 產生的夢裡訓練，夢中平均存活約 900 步，搬回真實環境後約 1,100 步。解題門檻是 750 步。
4. **模型漏洞會被利用**：M 只是近似，C 會找到「鑽漏洞」的策略。用低溫度 τ = 0.10 訓練時，夢中拿到 2,086 分，真實環境只有 193 分；調到 τ = 1.15，夢中 918 分、真實 1,092 分，是最好的真實成績。溫度越高，夢越不確定，越難被鑽漏洞，但太高又學不起來。
5. **動機**：作者以人腦的心智模型（mental model）為類比。例如打擊者在球飛來時，是依內部的預測反射性揮棒。

## 被以下概念頁引用
- [world-model](../concepts/world-model.md)
- [latent-representation](../concepts/latent-representation.md)
- [prediction-dynamics](../concepts/prediction-dynamics.md)
- [learning-in-imagination](../concepts/learning-in-imagination.md)
- [generative-vs-latent](../concepts/generative-vs-latent.md)
- [reinforcement-learning](../concepts/reinforcement-learning.md)
- [agent-environment](../concepts/agent-environment.md)
- [limitations](../concepts/limitations.md)
- [applications](../concepts/applications.md)

# S3｜MuZero：Mastering Atari, Go, Chess and Shogi by Planning with a Learned Model（DeepMind, 2020）

| 欄位 | 內容 |
|---|---|
| 作者／機構 | Julian Schrittwieser、Ioannis Antonoglou、Thomas Hubert、……、David Silver（DeepMind） |
| 年份 | 2019 arXiv 預印本；2020-12 刊於 *Nature* 588 |
| 連結 | https://arxiv.org/abs/1911.08265 ・https://doi.org/10.1038/s41586-020-03051-4 ・部落格 https://deepmind.google/blog/muzero-mastering-go-chess-shogi-and-atari-without-rules/ |
| 來源性質 | **同儕審查論文（論文實證）**＋官方部落格說明 |
| 閱讀狀態 | 已讀 arXiv 摘要、Nature 摘要、官方部落格（未逐頁讀全文）。本 Wiki 標為〔論文實證〕的 S3 內容，只限於論文摘要中有的內容（不需規則、Atari 當時最佳、追平 AlphaZero、需要規則的 AlphaZero 對照，以及方法本身：把樹狀搜尋和學到的模型結合，模型只預測策略、價值、獎勵這三個和規劃有關的量）；部落格的背景描述與展望另外標示 |
| raw 筆記 | [raw/notes/s3-muzero-2020.md](../../raw/notes/s3-muzero-2020.md) |
| 取用日期 | 2026-11-25 |

## 摘要
樹狀規劃方法在西洋棋、圍棋這類「有完美模擬器」的領域很成功，但真實世界的運作規則往往複雜又未知。MuZero 把「學出來的模型」和 AlphaZero 的樹狀搜尋結合，**不需要知道規則**，就在多個領域達到超越人類的表現。

## 重點
1. **只模擬對決策有用的部分**：MuZero 不嘗試模擬整個環境，只學三樣東西：
   - **價值（value）**：目前局面有多好？
   - **策略（policy）**：哪個行動最好？
   - **獎勵（reward）**：上一個行動有多好？
   官方比喻：知道雨傘能讓你不淋濕，比模擬雨滴在空中的軌跡更有用。
2. **與前身、與無模型方法的差別**：AlphaZero 必須知道環境的運作規則（例如棋規或精確模擬器）。無模型（model-free）方法如 DQN、R2D2、Agent57，則不使用學到的模型，而是直接估計最好的下一步。官方部落格指出，在 MuZero 之前，Atari 上最好的成績都來自這類無模型系統。（2026-11-25 補：依 DeepMind 部落格原文加入。）
3. **成果**：在 57 款 Atari 遊戲上達到當時最佳成績。Atari 是有模型規劃方法過去一直表現不好的領域。在圍棋、西洋棋、將棋上則追平 AlphaZero。
4. **未來應用（官方部落格的展望，非已實現成果）**：官方認為 MuZero 的想法可能有助於機器人、工業系統等規則未知的真實場景。

## 被以下概念頁引用
- [world-model](../concepts/world-model.md)
- [reinforcement-learning](../concepts/reinforcement-learning.md)
- [planning](../concepts/planning.md)
- [prediction-dynamics](../concepts/prediction-dynamics.md)
- [generative-vs-latent](../concepts/generative-vs-latent.md)
- [agent-environment](../concepts/agent-environment.md)
- [applications](../concepts/applications.md)

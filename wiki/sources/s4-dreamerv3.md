# S4｜DreamerV3：Mastering Diverse Domains through World Models（Hafner et al.）

| 欄位 | 內容 |
|---|---|
| 作者／機構 | Danijar Hafner、Jurgis Pasukonis、Jimmy Ba、Timothy Lillicrap（DeepMind／多倫多大學） |
| 年份 | 2023-01 arXiv（v2 2024-04）；2025 刊於 *Nature*，期刊版題為 *Mastering diverse control tasks through world models* |
| 連結 | https://arxiv.org/abs/2301.04104 ・程式碼 https://github.com/danijar/dreamerv3 |
| 來源性質 | **研究論文（論文實證）**，期刊版經同儕審查 |
| 閱讀狀態 | 已讀 arXiv 摘要與全文前段 |
| raw 筆記 | [raw/notes/s4-dreamerv3.md](../../raw/notes/s4-dreamerv3.md) |
| 取用日期 | 2026-11-25 |

## 摘要
現有的強化學習演算法要用到新領域時，需要大量專業知識和實驗來調整。DreamerV3 是一個以世界模型為基礎的通用演算法：它學一個環境模型，再靠「想像未來情境」來改進行為。只用**一組固定設定**，就在 150 多個不同任務中勝過專門設計的方法。

## 重點
1. **運作方式**
   - 世界模型把感官輸入（例如畫面）編碼成**離散表示** z。
   - 序列模型（帶有循環狀態 h）根據行動，預測未來的表示和獎勵。訓練時也會把表示**解碼還原**成輸入（論文圖 3 的 enc／dec）。
   - 世界模型預測可能行動的結果，**評論者（critic）**判斷每個結果的價值，**行動者（actor）**據此選擇行動。行動者與評論者都在「想像出來的軌跡」中訓練。
2. **通用性**：同一組超參數橫跨連續與離散動作、畫面與低維輸入、2D 與 3D 世界、不同資料量與獎勵頻率。涵蓋的領域從機器人運動、操作，到 Atari、ProcGen、DMLab、Minecraft。
3. **Minecraft 挖鑽石**：DreamerV3 是第一個不靠人類資料或預先設計的課程，就在 Minecraft 從零開始挖到鑽石的演算法。這需要在開放世界中，只憑畫面和稀少的獎勵規劃長遠策略。
4. **擴展性**：模型越大，資料效率和最終表現都越好，提供了一種可預期的提升方式。
5. **作者展望**：未來方向包括從網路影片教智慧體世界知識，以及跨領域學習單一世界模型。

## 被以下概念頁引用
- [world-model](../concepts/world-model.md)
- [reinforcement-learning](../concepts/reinforcement-learning.md)
- [latent-representation](../concepts/latent-representation.md)
- [prediction-dynamics](../concepts/prediction-dynamics.md)
- [learning-in-imagination](../concepts/learning-in-imagination.md)
- [generative-vs-latent](../concepts/generative-vs-latent.md)
- [agent-environment](../concepts/agent-environment.md)
- [applications](../concepts/applications.md)
- [limitations](../concepts/limitations.md)

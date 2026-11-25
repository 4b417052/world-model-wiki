# S5｜Video generation models as world simulators（OpenAI, 2024）

> ⚠ **來源性質：公司報告（OpenAI 自稱 technical report，但不含模型細節；本 Wiki 一律視為公司宣稱，不使用〔公司技術報告〕標籤）。**
> 報告未經同儕審查，並且明言「不包含模型與實作細節」，所以外界無法重現或驗證。報告中的能力描述多屬**質性觀察**（展示影片），沒有量化評測。

| 欄位 | 內容 |
|---|---|
| 作者／機構 | OpenAI |
| 年份 | 2024-02-15 |
| 連結 | https://openai.com/index/video-generation-models-as-world-simulators/ |
| 來源性質 | **公司報告（公司宣稱）** |
| 閱讀狀態 | 已讀原文 |
| raw 筆記 | [raw/notes/s5-openai-sora-2024.md](../../raw/notes/s5-openai-sora-2024.md) |
| 取用日期 | 2026-11-25 |

## 摘要
OpenAI 用大量影片訓練生成模型 Sora。他們主張，**持續放大影片生成模型，是打造通用物理世界模擬器的一條有希望的路**。

## 重點
1. **方法（報告揭露的部分）**：以文字為條件的擴散模型（diffusion model），在不同長度、解析度與長寬比的影片和圖片上聯合訓練。Transformer 架構處理的是影片與圖片的「時空區塊」（spacetime patches），就像語言模型處理文字 token 一樣。最大的模型能產生一分鐘的高品質影片。
2. **報告觀察到的「模擬能力」（公司宣稱）**
   - **3D 一致性**：鏡頭移動時，人物和場景在三維空間中一致地移動。
   - **物體恆存**：人和物被遮住或離開畫面後仍然存在。報告自己說這是「經常但不總是」做到。
   - **與世界互動**：有時能呈現簡單動作改變世界狀態，例如畫筆的筆觸留在畫布上、漢堡被咬一口後留下咬痕。
   - **模擬數位世界**：只要提示中提到 Minecraft，就能一邊以基本策略（簡單的行動規則）控制玩家角色，一邊畫出遊戲世界。
3. **報告自承的限制**
   - 很多基本互動的物理模擬不準確，例如玻璃碎裂。
   - 吃東西之類的互動，不一定會讓物體狀態正確改變。
   - 長影片會不連貫，物體會憑空出現。

## 本 Wiki 的使用注意
「世界模擬器」是 OpenAI 自己的定位。[S8](s8-ding-survey-2024.md) 綜述也質疑這類模型是否真的算得上完整的世界模型。概念頁引用本來源時，一律標為「公司宣稱」。

## 被以下概念頁引用
- [video-world-simulator](../concepts/video-world-simulator.md)
- [generative-vs-latent](../concepts/generative-vs-latent.md)
- [interactive-world-model](../concepts/interactive-world-model.md)
- [limitations](../concepts/limitations.md)
- [world-model](../concepts/world-model.md)

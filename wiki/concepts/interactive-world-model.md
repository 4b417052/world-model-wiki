# 可互動的世界模型（Interactive / Action-conditioned World Model）

> **依據來源**：[S5](../sources/s5-openai-sora-2024.md)・[S6](../sources/s6-deepmind-genie3-2025.md)・[S7](../sources/s7-meta-vjepa2-2025.md)・[S9](../sources/s9-nvidia-cosmos-2025.md)

## 一句話定義
**可互動的世界模型**會根據「你做了什麼動作」來改變預測結果，不只是自己播放一段固定的未來。

## 白話解釋
- 看電影：劇情早就決定好，你只能看。
- 玩電動：你按左，角色就往左，世界跟著你的操作改變。

一般的影片生成比較像前者，可互動的世界模型則像後者。對 AI 智慧體來說，後者才能用來練習「我這樣做會怎樣」。〔比喻為通用解釋〕

## 細節
1. **Genie 3：即時互動**〔公司宣稱，S6〕
   - 用文字生成世界後，使用者可以即時操作移動：每秒 24 格、720p，一致性維持數分鐘。
   - 還能用文字觸發「世界事件」，改變正在生成的世界。
   - 難處在**記憶**：畫面是逐格生成的，使用者回到舊地點時，模型必須記得那裡原本的樣子。
   - 限制〔公司自承，S6〕：智慧體能做的動作有限、多智慧體互動未解、只能連續互動數分鐘。
2. **Sora：有限的互動跡象**〔公司宣稱，S5〕
   - Sora 主要是根據文字生成影片。
   - 報告提到它能在 Minecraft 中以基本策略控制玩家，也能呈現簡單動作改變世界狀態（例如漢堡上的咬痕）。
3. **Cosmos：用動作當提示**〔公司技術報告，S9〕：後訓練時，提示可以是動作指令、軌跡或文字指示，讓模型學會「這個動作會導致什麼畫面」。
4. **V-JEPA 2：以行動為條件的潛在預測**〔論文實證，S7〕：第二階段用不到 62 小時的機器人資料，讓預測器知道執行了什麼動作，因此能用來規劃機械手臂的動作。

## 重點
「能不能根據行動做預測」，是區分一般影片生成和**可用來決策的**世界模型的關鍵之一。〔本 Wiki 整理，依 S5–S7、S9 並排比較〕

## 相關概念
[prediction-dynamics](prediction-dynamics.md)・[video-world-simulator](video-world-simulator.md)・[generative-vs-latent](generative-vs-latent.md)

## 依據來源
- S5 `wiki/sources/s5-openai-sora-2024.md`：Minecraft 控制與咬痕例子
- S6 `wiki/sources/s6-deepmind-genie3-2025.md`：即時互動、記憶、世界事件、限制
- S7 `wiki/sources/s7-meta-vjepa2-2025.md`：以行動為條件的預測器
- S9 `wiki/sources/s9-nvidia-cosmos-2025.md`：動作指令與軌跡作為提示

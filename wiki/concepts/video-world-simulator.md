# 影片生成模型當作世界模擬器（Video Generation as World Simulation）

> **依據來源**：[S5](../sources/s5-openai-sora-2024.md)・[S6](../sources/s6-deepmind-genie3-2025.md)・[S7](../sources/s7-meta-vjepa2-2025.md)・[S8](../sources/s8-ding-survey-2024.md)・[S9](../sources/s9-nvidia-cosmos-2025.md)

## 一句話定義
這種想法認為：用大量影片訓練一個能「產生影片」的模型，它為了畫得像真的，就得學會世界的規律，因此可以當作**世界模擬器**。

## 白話解釋
如果一個人能把「球從桌上滾落、彈跳、慢慢停下」畫得很逼真，他多少懂一些物理。影片生成模型背後的期待也是這樣。但「畫得像」和「真的懂」不一定是同一回事。〔比喻為通用解釋〕

術語：
- **擴散模型**（diffusion model）：一種常用來生成圖片和影片的 AI 技術。〔通用解釋〕
- **自迴歸**（auto-regressive）：一次產生一小段，再根據已產生的內容接著產生下一段。〔通用解釋；S6、S9 使用此方法〕

## 細節
1. **Sora（OpenAI）**〔公司宣稱，S5〕
   - 主張持續放大影片模型，是通往通用物理世界模擬器的一條有希望的路。
   - 觀察到的能力：3D 一致性、物體被遮住後仍存在（「經常但不總是」）、筆觸留在畫布上、能模擬 Minecraft。
   - （本 Wiki 註記）報告不提供模型與實作細節，所以以上能力無法獨立驗證。〔本 Wiki 整理〕
2. **Cosmos（NVIDIA）**〔公司技術報告，S9〕
   - 稱為「世界基礎模型」：先用約 1 億段影片預訓練成通才，再用小量目標資料（可含動作指令）後訓練成專用模型。
   - 有擴散與自迴歸兩種模型，平台開源、權重開放。
   - 報告稱模型能產生「物理準確」的影片，這是公司的自我評價。〔公司宣稱〕
3. **Genie 3（DeepMind）**〔公司宣稱，S6〕：影片式生成，但能即時回應使用者的操作。→ [interactive-world-model](interactive-world-model.md)
4. **S8 的分類與保留**〔綜述整理〕
   - S8 把 Sora、Cosmos、Genie 歸為「影片世界模型」，屬於「預測物理世界的未來」這一類。
   - 同時指出，它們是否真的算得上完整的世界模型，仍有疑問。
5. **另一個研究團隊的物理測試**〔論文實證，S7〕：IntPhys 2 基準測試影片是否違反物理，目前的影片模型表現接近亂猜。
   - 注意：做這個測試的 Meta 本身屬於非生成式路線，並非中立的第三方。〔本 Wiki 整理〕

## 證據性質提醒
本頁的正面描述**大多來自公司本身**（S5、S6、S9），保留意見則來自綜述（S8）和其他研究機構的基準測試（S7）。使用時請一併呈現。

## 相關概念
[generative-vs-latent](generative-vs-latent.md)・[interactive-world-model](interactive-world-model.md)・[limitations](limitations.md)

## 依據來源
- S5 `wiki/sources/s5-openai-sora-2024.md`：Sora 的主張、能力與限制
- S6 `wiki/sources/s6-deepmind-genie3-2025.md`：影片式互動世界
- S7 `wiki/sources/s7-meta-vjepa2-2025.md`：IntPhys 2 物理測試結果
- S8 `wiki/sources/s8-ding-survey-2024.md`：分類與保留意見
- S9 `wiki/sources/s9-nvidia-cosmos-2025.md`：世界基礎模型與預訓練／後訓練

# 限制與爭議（Limitations and Open Questions）

> **依據來源**：[S1](../sources/s1-ha-schmidhuber-2018-world-models.md)・[S2](../sources/s2-lecun-2022-path-towards-ami.md)・[S4](../sources/s4-dreamerv3.md)・[S5](../sources/s5-openai-sora-2024.md)・[S6](../sources/s6-deepmind-genie3-2025.md)・[S7](../sources/s7-meta-vjepa2-2025.md)・[S8](../sources/s8-ding-survey-2024.md)・[S9](../sources/s9-nvidia-cosmos-2025.md)

## 一句話定義
世界模型仍是發展中的研究方向：預測常出錯、只能維持短時間，連「什麼才算世界模型」都還沒有共識。

## 細節

### 1. 模型不完美，而且會被鑽漏洞〔論文實證，S1〕
世界模型只是真實世界的近似。智慧體會學到「在模型裡有效、在現實中無效」的策略。在 VizDoom 實驗中，夢中 2,086 分的策略，在現實只拿到 193 分。

### 2. 物理常常不對〔公司自承，S5；論文實證，S7〕
- Sora 的報告承認：玻璃碎裂等基本物理不準、吃東西不一定改變物體狀態、長影片不連貫、物體會憑空出現。
- 在判斷影片是否違反物理的 IntPhys 2 基準上，影片模型表現接近亂猜。

### 3. 只能維持短時間、時間尺度有限〔公司自承，S6；論文實證，S7〕
- Genie 3 只能連續互動數分鐘，不是數小時。
- V-JEPA 2 只在單一時間尺度上預測，但很多任務需要跨尺度的規劃。

### 4. 互動能力有限〔公司自承，S6〕
- 智慧體能做的動作有限。
- 多個智慧體之間的複雜互動仍未解決。
- 無法精確重現真實地理；畫面中清楚的文字只有在輸入描述中寫明時才會出現。

### 5. 和人類仍有差距〔論文實證，S7〕
- 在三個物理推理基準上，人類得分 85%–95%，頂尖模型明顯落後。
- 模型能回答「發生了什麼」，但難以回答「本來可能發生什麼」「接下來會怎樣」。

### 6. 資料難取得〔公司技術報告，S9〕
實體 AI 需要「觀察與行動交錯」的資料，而在真實世界收集這種資料既困難又有風險。

### 7. 強化學習本身難調〔論文實證，S4〕
傳統強化學習換到新領域，需要大量專業知識和實驗來調參。DreamerV3 嘗試用固定設定解決這個問題。

### 8. 定義沒有共識〔綜述整理，S8〕
- 世界模型的定義分成「理解世界」與「預測未來」兩種觀點。
- 影片模型是否算得上完整的世界模型仍有疑問。
- S8 列出的待解挑戰：物理規則與反事實模擬、社會面向、評測基準、以具身智慧銜接模擬與現實、模擬效率、倫理與安全。

### 9. 路線之爭與尚未實現的藍圖〔立場觀點，S2 原文〕
- LeCun 主張不應該逐像素預測，並明確反對生成式架構（p.27、p.30）。這和 S5、S6、S9 的生成式路線正好相反。→ [generative-vs-latent](generative-vs-latent.md)
- 他也坦承自己的藍圖還有很多空白（§8.1，p.43–44）：
  - 階層式 JEPA 能否從影片訓練起來，仍未知。
  - 行動者如何找出最佳行動沒有規定。
  - 短期記憶的設計「有些模糊」。
  - 設定器是「最神秘」的部分。

### 10. 證據品質不一〔本 Wiki 整理〕
- S5（Sora）不提供模型細節，S6（Genie 3）未公開，外界無法驗證。
- S2 是立場論文，沒有實驗結果，只提出主張。
- 引用這些來源時，應區分「論文實證」與「公司宣稱」。

## 相關概念
[generative-vs-latent](generative-vs-latent.md)・[video-world-simulator](video-world-simulator.md)・[learning-in-imagination](learning-in-imagination.md)

## 依據來源
- S1 `wiki/sources/s1-ha-schmidhuber-2018-world-models.md`：模型漏洞被利用
- S2 `wiki/sources/s2-lecun-2022-path-towards-ami.md`：路線之爭、作者自承的未解問題（原文）
- S4 `wiki/sources/s4-dreamerv3.md`：強化學習調參困難
- S5 `wiki/sources/s5-openai-sora-2024.md`：物理錯誤（公司自承）
- S6 `wiki/sources/s6-deepmind-genie3-2025.md`：時間與互動限制（公司自承）
- S7 `wiki/sources/s7-meta-vjepa2-2025.md`：物理基準與人類差距、單一時間尺度
- S8 `wiki/sources/s8-ding-survey-2024.md`：定義爭議與挑戰清單
- S9 `wiki/sources/s9-nvidia-cosmos-2025.md`：實體 AI 資料難題

# 世界模型（World Model）

> **依據來源**：[S1](../sources/s1-ha-schmidhuber-2018-world-models.md)・[S2](../sources/s2-lecun-2022-path-towards-ami.md)・[S3](../sources/s3-muzero-2020.md)・[S4](../sources/s4-dreamerv3.md)・[S5](../sources/s5-openai-sora-2024.md)・[S8](../sources/s8-ding-survey-2024.md)

## 一句話定義
世界模型是 AI 系統內部的一套「世界如何運作」的模型。它用來**理解目前的狀態**，並**預測接下來會發生什麼**，特別是「如果我這樣做，會怎樣」。

## 白話解釋
你在腦中想「把杯子推到桌邊，它會掉下去摔破」，這時你就在用自己的世界模型：不必真的推，就能預先知道結果。〔通用解釋〕

S1 的作者也用人來類比：棒球打者沒有時間仔細思考，是靠腦中對球路的預測，反射性地在正確的時間點揮棒。〔來源比喻，S1〕

AI 的世界模型想做的是同一件事：讓機器在採取行動之前，先在「腦中」模擬結果。〔通用解釋〕

## 細節

### 1. 定義仍有爭議：兩種觀點，加上「兩者兼具」的主張〔綜述整理，S8〕
| 觀點 | 重點 | 代表 |
|---|---|---|
| 理解世界 | 把外部世界抽象化、壓縮成內部表示，掌握它的運作機制 | Ha & Schmidhuber（S1） |
| 預測未來 | 模擬世界接下來會怎麼演變，常以影片呈現 | Sora 等影片生成模型（S5） |
| 兩者兼具＋支援決策 | 除了感知與建模，還要能想像可能的未來，用來做決定 | LeCun（S2） |

### 2. 一個世界模型通常做三件事〔本 Wiki 整理，依 S1、S3、S4 歸納〕
- **壓縮**：把大量感官資料（例如畫面）變成精簡的內部表示。→ [latent-representation](latent-representation.md)
- **預測**：給定目前狀態（和行動），預測下一步。→ [prediction-dynamics](prediction-dynamics.md)
- **被用來做決策**：拿來規劃，或在想像中練習。→ [planning](planning.md)、[learning-in-imagination](learning-in-imagination.md)

### 3. 在 LeCun 架構中的位置〔立場觀點，S2 原文 §3，p.7〕
- 世界模型是六個模組中最複雜的一個，有兩個角色：①補足感知沒有提供的資訊 ②預測可能的未來狀態，包括「照某個行動序列做下去會怎樣」。
- LeCun 稱它為世界中「**相關面向**」的模擬器：哪些面向算相關，由當下的任務決定。
- 他也把**常識**看成一組世界模型，能告訴智慧體什麼可能發生、什麼合理、什麼不可能（S2 §2.1，p.3）。

### 4. 不同研究對「要模擬多少」看法不同
- S1：壓縮並預測整個畫面的變化。〔論文實證〕
- S3（MuZero）：只模擬對決策有用的三樣東西：價值、策略、獎勵。〔論文實證〕
- 詳細對比見 → [generative-vs-latent](generative-vs-latent.md)

## 相關概念
[agent-environment](agent-environment.md)・[reinforcement-learning](reinforcement-learning.md)・[generative-vs-latent](generative-vs-latent.md)・[limitations](limitations.md)

## 依據來源
- S1 `wiki/sources/s1-ha-schmidhuber-2018-world-models.md`：打者類比、壓縮與預測
- S2 `wiki/sources/s2-lecun-2022-path-towards-ami.md`：世界模型在自主智慧架構中的兩個角色、常識（原文）
- S3 `wiki/sources/s3-muzero-2020.md`：只模擬決策相關部分
- S4 `wiki/sources/s4-dreamerv3.md`：用世界模型想像未來來改進行為
- S5 `wiki/sources/s5-openai-sora-2024.md`：預測取向的代表
- S8 `wiki/sources/s8-ding-survey-2024.md`：定義爭議與兩類分法

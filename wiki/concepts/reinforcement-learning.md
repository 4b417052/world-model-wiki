# 強化學習與「有模型 vs 無模型」（Reinforcement Learning; Model-based vs Model-free）

> **依據來源**：[S1](../sources/s1-ha-schmidhuber-2018-world-models.md)・[S2](../sources/s2-lecun-2022-path-towards-ami.md)・[S3](../sources/s3-muzero-2020.md)・[S4](../sources/s4-dreamerv3.md)

## 一句話定義
**強化學習**是讓智慧體透過「嘗試 → 得到獎勵 → 調整」來學會做決策的方法。依照有沒有學一個世界模型來輔助，可以分成**有模型**和**無模型**兩類。

## 白話解釋
學騎腳踏車有兩種方式：
- **無模型**：一直騎、一直摔，慢慢記住「這種情況要往左」，但不去理解為什麼。
- **有模型**：先在腦中建立「重心偏右，車就會往右倒」的理解，再用這個理解推想該怎麼做。

世界模型就是「有模型」方法裡的那個「模型」。〔比喻為通用解釋〕

## 細節
1. **兩類方法**（基本定義，依 S3 摘要與官方部落格的分類；DQN 等例子出自 S3 官方部落格。這是名詞定義，不是實驗結果，所以不標證據類型）
   - **有模型（model-based）**：先學一個環境運作方式的模型，再用它來規劃。
   - **無模型（model-free）**：不使用學到的模型，直接估計最好的下一步。例子有 DQN、R2D2、Agent57。
   - 〔公司宣稱，S3 官方部落格〕在 MuZero 之前，Atari 遊戲的最佳成績都來自無模型方法（這句是 DeepMind 部落格對研究背景的描述，不是 MuZero 論文的實驗結果，也不是名詞定義）。
2. **強化學習的難處**〔論文實證，S4〕：現有演算法要用到新領域時，需要大量專業知識和實驗來調參。DreamerV3 想用世界模型配一組固定設定，解決這個問題。
3. **把世界模型和決策分開**〔論文實證，S1〕：S1 把智慧體分成「大的世界模型」和「小的控制器」。世界模型負責理解與預測，控制器只要用很少參數（867 個）就能把賽車開好。
4. **LeCun 的批評：只靠獎勵不夠**〔立場觀點，S2 原文 §8.3.2，p.46–47〕
   - 無模型強化學習的樣本效率極差：一個純量獎勵給的資訊很少，所以要試非常多次才學得會。
   - 有模型方法有潛力提高效率。
   - 他主張世界模型的大部分參數應該靠「預測世界」來訓練，獎勵的角色相對次要。
   - 他認為自己的提案比較接近最佳控制，而不是強化學習。

## 相關概念
[agent-environment](agent-environment.md)・[planning](planning.md)・[learning-in-imagination](learning-in-imagination.md)・[world-model](world-model.md)

## 依據來源
- S1 `wiki/sources/s1-ha-schmidhuber-2018-world-models.md`：世界模型＋小控制器的分工
- S2 `wiki/sources/s2-lecun-2022-path-towards-ami.md`：「只靠獎勵不夠」的批評（原文，立場觀點）
- S3 `wiki/sources/s3-muzero-2020.md`：有模型／無模型的區分與例子
- S4 `wiki/sources/s4-dreamerv3.md`：強化學習調參困難的問題

# 在想像中學習（Learning in Imagination / Training in a Dream）

> **依據來源**：[S1](../sources/s1-ha-schmidhuber-2018-world-models.md)・[S4](../sources/s4-dreamerv3.md)・[S6](../sources/s6-deepmind-genie3-2025.md)・[S9](../sources/s9-nvidia-cosmos-2025.md)

## 一句話定義
**在想像中學習**是讓智慧體在世界模型產生的「模擬經驗」裡練習，而不是每一次都在真實環境中嘗試。

## 白話解釋
飛行員先用飛行模擬器練習，再上真的飛機。模擬器出錯沒有代價，可以練很多次。世界模型就是 AI 自己學出來的「模擬器」。〔比喻為通用解釋〕

## 細節
1. **S1：在夢中訓練，搬回現實**〔論文實證〕
   - VizDoom 任務中，智慧體**完全**在記憶模組 M 產生的「夢」裡訓練。
   - 搬回真實遊戲後平均存活約 1,100 步，超過解題門檻的 750 步。
2. **S1：夢的漏洞會被鑽**〔論文實證〕
   - 夢只是近似，智慧體會找到「在夢裡有效、在現實無效」的策略。
   - 溫度 τ = 0.10：夢中 2,086 分，現實只有 193 分。
   - 溫度 τ = 1.15：夢中 918 分，現實 1,092 分，是最好的真實成績。
   - 調高溫度讓夢變得更不確定，智慧體反而學到更穩健的策略。
3. **S4：DreamerV3 在想像的軌跡中訓練**〔論文實證〕
   - 行動者與評論者都在世界模型想像出來的軌跡中訓練。
   - 用一組固定設定解 150 多個任務，並在 Minecraft 從零挖到鑽石。
4. **S9：為什麼實體 AI 需要模擬**〔公司技術報告〕：在真實世界中做動作可能弄壞系統或環境，所以需要一個可以安全互動的「世界數位分身」。
5. **S6：無限的訓練環境**〔公司宣稱〕：DeepMind 認為世界模型能提供「無限多樣」的模擬環境來訓練智慧體，並視之為通往 AGI（通用人工智慧，Artificial General Intelligence）的墊腳石。

## 相關概念
[planning](planning.md)・[prediction-dynamics](prediction-dynamics.md)・[limitations](limitations.md)

## 依據來源
- S1 `wiki/sources/s1-ha-schmidhuber-2018-world-models.md`：夢中訓練與溫度實驗數據
- S4 `wiki/sources/s4-dreamerv3.md`：想像軌跡訓練與 Minecraft 成果
- S6 `wiki/sources/s6-deepmind-genie3-2025.md`：模擬環境訓練智慧體（公司宣稱）
- S9 `wiki/sources/s9-nvidia-cosmos-2025.md`：實體 AI 需要數位分身的理由

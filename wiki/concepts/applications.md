# 世界模型的應用（Applications）

> **依據來源**：[S1](../sources/s1-ha-schmidhuber-2018-world-models.md)・[S3](../sources/s3-muzero-2020.md)・[S4](../sources/s4-dreamerv3.md)・[S6](../sources/s6-deepmind-genie3-2025.md)・[S7](../sources/s7-meta-vjepa2-2025.md)・[S8](../sources/s8-ding-survey-2024.md)・[S9](../sources/s9-nvidia-cosmos-2025.md)

## 一句話定義
世界模型可以用在任何需要「先預測、再行動」的地方：從玩遊戲，到控制機器人和自動駕駛。

## 細節

### 1. 遊戲與智慧體訓練（已有實驗成果）〔論文實證〕
- 賽車與 VizDoom 遊戲。〔S1〕
- 圍棋、西洋棋、將棋與 57 款 Atari 遊戲。〔S3〕
- 150 多個任務，包括從零在 Minecraft 挖到鑽石。〔S4〕

### 2. 機器人（Robotics）
- V-JEPA 2 在機械手臂上零樣本完成抓放任務，新物體、新環境的成功率 65%–80%。〔論文實證，S7〕
- 世界模型可用於機器人的導航、物體偵測、任務規劃。〔綜述整理，S8〕
- Cosmos 以機器人操作為應用範例。〔公司技術報告，S9〕
- DeepMind 認為 Genie 3 這類世界模型可以用來訓練 AI 智慧體。〔公司宣稱，S6〕（第一版原寫「訓練機器人」，S6 原文沒有提到機器人，2026-11-25 修正）

### 3. 自動駕駛（Autonomous Driving）
- 世界模型要即時感知路況，並預測交通會怎麼演變。〔綜述整理，S8〕
- Cosmos 以自動駕駛場景為應用範例。〔公司技術報告，S9〕

### 4. 實體 AI 的安全訓練場〔公司技術報告，S9〕
實體 AI（帶有感測器與致動器的 AI）在現實中試錯可能造成損壞。世界模型可以當作「世界的數位分身」，讓它先在數位世界裡練習。

### 5. 其他
- 社會模擬：模擬社會互動與人類決策。〔綜述整理，S8〕
- MuZero 的想法未來可能用於工業系統等規則未知的真實場景。〔公司宣稱，S3 官方部落格的展望，非已實現成果〕

## 證據性質提醒〔本 Wiki 整理〕
目前**有實驗數據支持**的應用，主要是遊戲與機器人操作（S1、S3、S4、S7）。自動駕駛的用途來自綜述的整理，加上 NVIDIA 的應用範例（公司技術報告，不是實際上路的實驗）；社會模擬只來自綜述的整理；「在模擬環境中訓練智慧體，是通往 AGI 的墊腳石」等說法屬於公司願景。

## 相關概念
[learning-in-imagination](learning-in-imagination.md)・[planning](planning.md)・[limitations](limitations.md)

## 依據來源
- S1 `wiki/sources/s1-ha-schmidhuber-2018-world-models.md`：賽車與 VizDoom
- S3 `wiki/sources/s3-muzero-2020.md`：棋類與 Atari、未來展望
- S4 `wiki/sources/s4-dreamerv3.md`：150+ 任務與 Minecraft
- S6 `wiki/sources/s6-deepmind-genie3-2025.md`：訓練智慧體（公司宣稱）
- S7 `wiki/sources/s7-meta-vjepa2-2025.md`：機械手臂抓放
- S8 `wiki/sources/s8-ding-survey-2024.md`：自駕、機器人、社會模擬
- S9 `wiki/sources/s9-nvidia-cosmos-2025.md`：實體 AI、機器人、自駕

# 世界模型（World Models in AI）Wiki ── 目錄

這份 Wiki 是給**完全不熟悉 AI 世界模型的初學者**的知識庫。共 9 篇來源頁、12 篇概念頁。
每個概念頁開頭都有「依據來源」，結尾都有「依據來源」清單，可以一路追溯到 `sources/` 頁，再追到 `raw/` 的原始連結與筆記。

## 證據標籤說明
概念頁中的論點大多標有證據類型；沒有標籤的句子是白話說明、舉例或來源的基本描述：

| 標籤 | 意思 |
|---|---|
| 〔論文實證〕 | 來自有實驗數據的研究論文 |
| 〔公司宣稱〕／〔公司自承〕 | 來自公司部落格、公司報告，或公司對自家成果的自我評價（包括 S9 這類開放權重報告中的整體評價），外界難以獨立驗證；「自承」指公司自己承認的限制 |
| 〔公司技術報告〕 | 公司發表、但附實驗並開放模型（**只用於 S9**）。注意：S5 雖然自稱 technical report，但不含模型細節，本 Wiki 一律標為〔公司宣稱〕 |
| 〔立場觀點〕 | 立場論文的主張，不是實驗結果（S2） |
| 〔綜述整理〕 | 來自綜述論文 S8 對他人研究的整理 |
| 〔通用解釋〕 | 本 Wiki 為初學者寫的一般性說明或比喻，不是來自特定來源 |
| 〔來源比喻〕 | 來源作者自己用的比喻或類比（例如 S1 的棒球打者、S3 的雨傘、S2 的樹葉與漣漪），用來說明想法，**不是實驗證據**（2026-11-25 簡報第 1 輪檢查後新增） |
| 〔本 Wiki 整理〕 | 本 Wiki 自己的歸納或註記：包括把多個來源並排比較後的結論，以及對某個來源性質的註記（例如「報告不含模型細節」「模型未公開」） |

## 建議閱讀順序（新手）
1. [world-model](concepts/world-model.md) →
2. [agent-environment](concepts/agent-environment.md) →
3. [reinforcement-learning](concepts/reinforcement-learning.md) →
4. [latent-representation](concepts/latent-representation.md) →
5. [prediction-dynamics](concepts/prediction-dynamics.md) →
6. [planning](concepts/planning.md) →
7. [learning-in-imagination](concepts/learning-in-imagination.md) →
8. ★ [generative-vs-latent](concepts/generative-vs-latent.md) →
9. [video-world-simulator](concepts/video-world-simulator.md) →
10. [interactive-world-model](concepts/interactive-world-model.md) →
11. [applications](concepts/applications.md) →
12. [limitations](concepts/limitations.md)

---

## 概念頁（concepts/）

| 分類 | 頁面 | 簡介 | 依據來源 |
|---|---|---|---|
| 定義 | [world-model.md](concepts/world-model.md) | 什麼是世界模型、兩派定義、做哪三件事 | S1 S2 S3 S4 S5 S8 |
| 基礎術語 | [agent-environment.md](concepts/agent-environment.md) | 智慧體、環境、行動、獎勵、策略、價值等新手術語表 | S1 S3 S4 |
| 基礎術語 | [reinforcement-learning.md](concepts/reinforcement-learning.md) | 強化學習，以及有模型 vs 無模型 | S1 S2 S3 S4 |
| 核心機制 | [latent-representation.md](concepts/latent-representation.md) | 把畫面壓縮成精簡的向量 | S1 S2 S4 S7 S9 |
| 核心機制 | [prediction-dynamics.md](concepts/prediction-dynamics.md) | 根據狀態與行動預測下一步 | S1 S2 S3 S4 S6 S7 |
| 核心機制 | [planning.md](concepts/planning.md) | 用世界模型先想好幾步再行動 | S2 S3 S7 |
| 核心機制 | [learning-in-imagination.md](concepts/learning-in-imagination.md) | 在模型產生的「夢」中練習 | S1 S4 S6 S9 |
| ★ 技術路線 | [generative-vs-latent.md](concepts/generative-vs-latent.md) | 生成式（畫出畫面）vs 潛在預測式（只預測抽象表示）的完整對比 | S1–S9 全部 |
| 技術路線 | [video-world-simulator.md](concepts/video-world-simulator.md) | 影片生成模型能否當世界模擬器 | S5 S6 S7 S8 S9 |
| 技術路線 | [interactive-world-model.md](concepts/interactive-world-model.md) | 會根據行動改變的世界模型 | S5 S6 S7 S9 |
| 應用 | [applications.md](concepts/applications.md) | 遊戲、機器人、自動駕駛、實體 AI | S1 S3 S4 S6 S7 S8 S9 |
| 限制 | [limitations.md](concepts/limitations.md) | 物理錯誤、時間短、定義爭議、證據品質 | S1 S2 S4 S5 S6 S7 S8 S9 |

## 來源頁（sources/）

| ID | 頁面 | 性質 | 簡介 |
|---|---|---|---|
| S1 | [s1-ha-schmidhuber-2018-world-models.md](sources/s1-ha-schmidhuber-2018-world-models.md) | 研究論文 | V–M–C 架構、在夢中訓練 |
| S2 | [s2-lecun-2022-path-towards-ami.md](sources/s2-lecun-2022-path-towards-ami.md) | 立場論文（已讀原文） | 六模組架構、模式一／二、JEPA、反對生成式的理由 |
| S3 | [s3-muzero-2020.md](sources/s3-muzero-2020.md) | 同儕審查論文（Nature） | 不知規則也能規劃，只模擬決策量 |
| S4 | [s4-dreamerv3.md](sources/s4-dreamerv3.md) | 研究論文（Nature 2025） | 在想像中學習，150+ 任務，Minecraft 鑽石 |
| S5 | [s5-openai-sora-2024.md](sources/s5-openai-sora-2024.md) | 公司報告（不含模型細節）⚠ | 影片生成即世界模擬器的主張與限制 |
| S6 | [s6-deepmind-genie3-2025.md](sources/s6-deepmind-genie3-2025.md) | 公司部落格 ⚠ | 即時可互動的生成世界 |
| S7 | [s7-meta-vjepa2-2025.md](sources/s7-meta-vjepa2-2025.md) | 研究論文＋公司部落格 | JEPA 實作、機器人零樣本規劃、物理基準 |
| S8 | [s8-ding-survey-2024.md](sources/s8-ding-survey-2024.md) | 綜述論文 | 理解 vs 預測兩大類、應用與挑戰 |
| S9 | [s9-nvidia-cosmos-2025.md](sources/s9-nvidia-cosmos-2025.md) | 公司技術報告（開放權重） | 實體 AI 的世界基礎模型 |

## 其他
- 原始連結清單：[../raw/links.md](../raw/links.md)
- raw 筆記：`../raw/notes/`
- 操作紀錄：[../log.md](../log.md)

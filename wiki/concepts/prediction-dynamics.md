# 預測未來／動態模型（Prediction, Dynamics Model）

> **依據來源**：[S1](../sources/s1-ha-schmidhuber-2018-world-models.md)・[S2](../sources/s2-lecun-2022-path-towards-ami.md)・[S3](../sources/s3-muzero-2020.md)・[S4](../sources/s4-dreamerv3.md)・[S6](../sources/s6-deepmind-genie3-2025.md)・[S7](../sources/s7-meta-vjepa2-2025.md)

## 一句話定義
**動態模型**是世界模型中負責「預測下一步」的部分：根據**現在的狀態**和**要採取的行動**，預測**接下來的狀態**（有時也預測獎勵）。

## 白話解釋
就像下棋時心裡想「我走這步，對手大概會那樣回」。這種預測要看你打算怎麼走，所以叫「以行動為條件」的預測（action-conditioned prediction）。〔比喻為通用解釋〕

## 細節
1. **S1：預測機率分布**〔論文實證〕
   - 記憶模組 M（LSTM）預測下一個壓縮向量的**機率分布**，而不是單一答案，因為未來本來就不確定。
   - 它的隱藏狀態 h 帶有對未來的預測。控制器少了 h，賽車分數從 906 掉到 632，駕駛也變得很不穩定。
2. **S4：預測表示與獎勵**〔論文實證〕：DreamerV3 的序列模型根據行動，預測未來的表示和獎勵。
3. **S3：只預測決策需要的量**〔論文實證〕：MuZero 的模型反覆展開後，預測的是獎勵、策略、價值，而不是畫面本身。
4. **S7：先學觀察、再學行動**〔論文實證〕：V-JEPA 2 先從影片學會「世界通常怎麼變」，再用不到 62 小時機器人資料學「做了某個動作後會怎麼變」。
5. **S6：逐格自迴歸預測**〔公司宣稱〕：Genie 3 一格一格地生成畫面，每一格都要參考之前生成的整段軌跡。軌跡越長，要記住的東西越多。
6. **S2：預測的時間長度與不確定性**〔立場觀點，S2 原文〕
   - 低層、細節多的表示只適合短期預測；高層、抽象的表示才能做長期預測，代價是丟掉很多細節（p.30）。
   - 開車的例子：接下來幾秒的車子軌跡可以準確預測；更長時間的細節受其他車、紅綠燈、行人影響而難以預測，但「大概幾點會到目的地」仍可預測（p.31）。
   - 世界不是完全可預測的，所以世界模型要能表示**多種**可能的未來（p.7、p.16）。

## 相關概念
[latent-representation](latent-representation.md)・[planning](planning.md)・[interactive-world-model](interactive-world-model.md)

## 依據來源
- S1 `wiki/sources/s1-ha-schmidhuber-2018-world-models.md`：M 模組與分數對照
- S2 `wiki/sources/s2-lecun-2022-path-towards-ami.md`：抽象層次與預測長度、多種可能的未來（原文）
- S3 `wiki/sources/s3-muzero-2020.md`：預測價值、策略、獎勵
- S4 `wiki/sources/s4-dreamerv3.md`：預測表示與獎勵
- S6 `wiki/sources/s6-deepmind-genie3-2025.md`：逐格生成與記憶
- S7 `wiki/sources/s7-meta-vjepa2-2025.md`：兩階段學習「行動→結果」

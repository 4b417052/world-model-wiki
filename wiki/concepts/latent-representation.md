# 潛在表示／壓縮表示（Latent Representation, Embedding）

> **依據來源**：[S1](../sources/s1-ha-schmidhuber-2018-world-models.md)・[S2](../sources/s2-lecun-2022-path-towards-ami.md)・[S4](../sources/s4-dreamerv3.md)・[S7](../sources/s7-meta-vjepa2-2025.md)・[S9](../sources/s9-nvidia-cosmos-2025.md)

## 一句話定義
**潛在表示**是把畫面這類龐大的原始資料，壓縮成一小串數字（向量），只保留重要資訊。這串數字所在的抽象空間叫做**潛在空間**（latent space）。

## 白話解釋
描述朋友長相時，你不會一顆一顆念出照片的像素，而是說「短髮、戴眼鏡、高個子」。這幾個重點就是一種「壓縮表示」：資料量少很多，但重要的資訊都在。

世界模型在這個精簡的空間裡做預測，比直接處理整張畫面省力得多。〔比喻為通用解釋〕

## 細節
1. **S1：VAE 壓縮畫面**〔論文實證〕：變分自編碼器把 64×64 的遊戲畫面壓成 32 維（賽車）或 64 維（VizDoom）的向量 z。後面的記憶模組和控制器都以這個 z 為輸入（控制器另外還會拿到記憶模組的隱藏狀態 h，見 S1 來源頁）。
2. **S4：離散表示**〔論文實證〕：DreamerV3 把感官輸入編碼成離散（類別式）的表示，再在這個空間中預測未來。
3. **S2：為什麼要抽象**〔立場觀點，S2 原文 p.24–25〕：在表示空間預測，就不必預測每個細節，編碼器可以把無關細節去掉。例如一輛車開到岔路口，表示只需要記車的位置、方向、速度，可以忽略路邊的樹和人行道的紋理。
4. **S7：嵌入**〔論文實證〕：V-JEPA 2 的編碼器把影片轉成「嵌入」（embedding，也是一種潛在表示），預測器直接在嵌入空間裡預測未來，不還原成像素。
5. **S9：Token**〔公司技術報告〕：Cosmos 先用「影片分詞器」把影片轉成 token。擴散模型用連續的向量 token，自迴歸模型用離散的整數 token。

## ⚠ 易混淆：「潛在表示」vs LeCun 的「潛在變數」
兩個詞都有「潛在」（latent），但意思不同：
- **潛在表示**（本頁）：把觀察壓縮後得到的向量。S1 的 z、S7 的嵌入都是。在 LeCun 的論文中，這類東西寫作 **s**（表示）。
- **潛在變數**（latent variable）：LeCun 論文中的 z，代表**無法從現有觀察預測的不確定性**。例子是：車到了岔路口，會往左還是往右？（S2 §4.2，p.19）〔立場觀點，S2 原文〕

注意：S1 也用 z 這個符號，但 S1 的 z 指的是壓縮後的向量，所以屬於第一種。

## 相關概念
[prediction-dynamics](prediction-dynamics.md)・[generative-vs-latent](generative-vs-latent.md)

## 依據來源
- S1 `wiki/sources/s1-ha-schmidhuber-2018-world-models.md`：VAE 與向量維度
- S2 `wiki/sources/s2-lecun-2022-path-towards-ami.md`：抽象表示的理由、潛在變數的定義（原文）
- S4 `wiki/sources/s4-dreamerv3.md`：離散表示
- S7 `wiki/sources/s7-meta-vjepa2-2025.md`：嵌入空間預測
- S9 `wiki/sources/s9-nvidia-cosmos-2025.md`：影片 token

# 新手必備術語：智慧體、環境、行動、獎勵（Agent, Environment, Action, Reward）

> **依據來源**：[S1](../sources/s1-ha-schmidhuber-2018-world-models.md)・[S3](../sources/s3-muzero-2020.md)・[S4](../sources/s4-dreamerv3.md)
>
> 說明：這些是 AI 領域的基本術語。來源論文都直接使用、但沒有另外定義。下面的白話說明標為〔通用解釋〕，是本 Wiki 為初學者寫的；「在來源中的例子」則有標出處。

## 一句話定義
**智慧體**在**環境**中觀察、採取**行動**，環境回饋**獎勵**；智慧體的目標是學會拿到更多獎勵。

## 術語表

| 術語 | 英文 | 白話說明〔通用解釋〕 | 在來源中的例子 |
|---|---|---|---|
| 智慧體 | Agent | 會自己做決定的 AI 程式，像玩遊戲的「玩家」 | S1 的賽車駕駛程式；S4 在 Minecraft 挖鑽石的程式 |
| 環境 | Environment | 智慧體所在的世界，例如一款遊戲或一個房間 | S1 的 CarRacing、VizDoom；S3 的圍棋與 Atari |
| 觀察 | Observation | 智慧體從環境「看到」的資訊，例如遊戲畫面 | S1 的 64×64 畫面；S4 的感官輸入 |
| 行動 | Action | 智慧體可以做的事，例如轉方向盤、下一步棋 | S3 的落子；S4 的連續與離散動作 |
| 獎勵 | Reward | 環境給的分數，告訴智慧體剛才做得好不好 | S3：「上一個行動有多好？」；S1 VizDoom 以存活時間為獎勵 |
| 策略 | Policy | 智慧體「看到什麼就做什麼」的規則 | S3：「哪個行動最好？」；S1 的控制器 C |
| 價值 | Value | 從目前狀態出發，未來預期能拿到多少獎勵 | S3：「目前局面有多好？」；S4 的評論者負責判斷價值 |
| 行動者／評論者 | Actor / Critic | 行動者負責選動作，評論者負責評估好壞 | S4 DreamerV3 |

## 其他會在簡報中出現的基本詞〔通用解釋〕
| 術語 | 英文 | 白話說明 |
|---|---|---|
| 神經網路 | Neural network | 一種從資料中學習規律的數學模型，是現代 AI 的基本工具 |
| 參數 | Parameter | 神經網路裡可調整的數字；參數越多，模型通常越大。例如 S7 的 V-JEPA 2 有 12 億個參數 |
| 訓練 | Training | 用資料反覆調整參數，讓模型表現變好的過程 |
| 零樣本 | Zero-shot | 沒有針對某個新環境或新任務特別收集資料或訓練，就直接使用 |
| 影格 | Frame | 影片中的一張畫面 |
| 像素 | Pixel | 組成畫面的最小色點。「64×64」指寬 64、高 64 個像素的小畫面 |
| AI | Artificial Intelligence | 人工智慧，讓電腦做出看似有智慧的判斷或行為的技術 |
| 狀態 | State | 某一個時刻，世界（或遊戲）是什麼樣子 |
| 步 | Step | 遊戲或模擬每往前推進一次，就是一「步」；常用來計算存活了多久 |
| 控制器 | Controller | 負責根據看到的資訊選擇行動的部分 |
| 時間尺度 | Time scale | 預測或規劃涵蓋的時間長短，例如「接下來幾秒」和「接下來幾小時」是不同的時間尺度 |
| 最佳控制 | Optimal control | 研究「怎麼控制機器才能得到最好結果」的工程領域，歷史比現代 AI 更久 |
| 開放權重 | Open weights | 公開模型訓練好的參數，任何人都可以下載使用 |
| AGI | Artificial General Intelligence | 通用人工智慧：像人一樣，各種任務都能學會的 AI；目前還不存在 |
| 解題門檻 | Solving threshold | 遊戲環境規定的分數：平均達到這個分數，就算「解決」了這個任務（S1 的賽車是 900 分，VizDoom 是存活 750 步） |
| 一致性 | Consistency | 生成的世界前後保持一致、不自相矛盾。S6 提到的例子：使用者回到舊地點時，模型必須記得那裡原本的樣子 |
| 抓放任務 | Pick-and-place | 讓機械手臂抓取物體、再放到指定位置的任務（S7 的機器人實驗） |
| 綜述論文 | Survey | 整理、比較某個領域大量研究的文章，本身不做新實驗 |

## 簡報會提到的遊戲與研究機構〔通用解釋〕
| 名稱 | 白話說明 | 在來源中的角色 |
|---|---|---|
| Atari 遊戲 | 1970–80 年代的一系列經典電子遊戲，AI 研究常拿來當標準測驗 | S3 MuZero 的 57 款遊戲測驗 |
| Minecraft | 一款開放世界的方塊建造遊戲，世界很大、目標很遠，對 AI 很難 | S4 DreamerV3 挖鑽石；S5 Sora 模擬 Minecraft 畫面 |
| VizDoom | 研究用的 3D 遊戲環境；S1 用的任務是躲開怪物射來的火球、盡量活久一點 | S1 在夢中訓練的實驗 |
| OpenAI | 美國 AI 公司，開發了 Sora | S5 |
| Google DeepMind（DeepMind） | Google 旗下的 AI 研究實驗室 | S3、S4、S6 |
| Google Brain | Google 過去的 AI 研究團隊（現已併入 Google DeepMind） | S1 作者 Ha 的所屬單位 |
| Meta | 美國科技公司（Facebook 母公司），LeCun 任職於此 | S2、S7 |
| NVIDIA | 美國晶片與 AI 公司 | S9 |

## 相關概念
[reinforcement-learning](reinforcement-learning.md)・[world-model](world-model.md)

## 依據來源
- S1 `wiki/sources/s1-ha-schmidhuber-2018-world-models.md`：遊戲環境、控制器、存活獎勵
- S3 `wiki/sources/s3-muzero-2020.md`：價值、策略、獎勵三要素的白話問句
- S4 `wiki/sources/s4-dreamerv3.md`：行動者／評論者、不同類型的輸入與動作

# Prompting and Exclude

## 目標

把音樂意圖拆成 Suno 可理解的正向描述與獨立排除條件，避免格式互相污染。

## Styles 的寫法

Styles 可使用完整自然語句，也可使用逗號分隔短語。優先包含 5–8 個高資訊元素：

1. 主曲風與次曲風
2. 年代或場景
3. 節奏與 groove
4. 主要樂器
5. 主唱質地與配置
6. 情緒與能量弧線
7. 製作質感

範例：

    Mandarin alternative pop with warm electric guitar, restrained verses, a rising emotional chorus, intimate solo lead vocal, organic drums, clear studio production

不要：

- 用方括號包住整串 Styles。
- 把「不要 choir」等負向要求混在正向描述中。
- 使用藝人姓名代替可觀察的音樂特徵。
- 同時要求互斥特徵，例如 intimate whisper 與 constant stadium belting。

## 把藝人參考翻成音樂特徵

使用者提供藝人或歌曲作為方向時，保留需求但轉譯：

| 使用者想要 | 轉譯方向 |
|---|---|
| 青春樂團式大副歌 | guitar-driven Mandarin pop-rock, narrative verses, rising chorus, earnest solo lead vocal |
| 節奏精準的流行 R&B | syncopated pop-R&B groove, tight bass, clipped rhythm guitar, expressive solo vocal, dynamic ad-libs |
| 臥室 Lo-fi 親密感 | muted drums, warm Rhodes, close-mic vocal, vinyl texture, low dynamic range |

最終 Suno-ready 欄位不保留藝人姓名。

## Exclude 的寫法

Exclude 是獨立欄位，使用短而具體的名詞或聲音事件：

    choir, crowd vocals, audience noise, applause, spoken intro, trap hi-hats

優先排除可聽見的元素，不寫抽象評價：

- 好：choir, heavy distortion, long instrumental intro
- 差：bad vocals, boring, low quality

若介面沒有 Exclude 欄位，可提供相容備案：

    Styles: intimate Mandarin pop, solo lead vocal, warm guitar, clear studio production. Avoid: choir, crowd vocals, applause.

## Lyrics 中的結構標記

方括號保留給歌詞結構或演唱指示：

    [Intro]
    [Verse 1]
    [Pre-Chorus]
    [Chorus]
    [Verse 2]
    [Bridge]
    [Outro]

對唱可用簡潔標記：

    [Verse 1: Vocal A]
    [Verse 2: Vocal B]
    [Chorus: Duet]

不要在每行塞入複雜控制語法；標記越多不代表控制越準。

## 經驗性副作用警示

以下是生成經驗，不是保證：

- anthemic、arena、stadium 或 live feel 可能增加群唱、觀眾感或大型空間感。
- powerful vocals 可能帶來更多和聲層疊。
- 想保留飽滿但避免群唱時，可改為 emotional rising chorus, powerful solo lead vocal, studio production，並在 Exclude 加 choir, crowd vocals, audience noise。

每次只調整 1–2 個元素做 A/B 測試；不要把一次結果寫成必然規律。

## 官方查核來源

- [Detailed Style Instructions](https://help.suno.com/en/articles/5782849)：Styles 可使用較完整、對話式的描述。
- [How do I exclude elements of a song?](https://help.suno.com/en/articles/3161921)：Exclude 位於 Custom Mode 的 Advanced Options。
- [Does Suno moderate songs?](https://help.suno.com/en/articles/3198209)：知名藝人或人物名稱、受著作權或商標保護的詞可能阻止生成。
產品介面與規則會改版；回答「現在」或「最新」問題時重新查官方頁面。

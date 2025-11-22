---
date: '2025-11-22T10:47:13+08:00'
draft: false
title: '其實 PTT 跟 YouTube 都支援 RSS 訂閱'
---

在這個[社群媒體演算法主宰]({{< ref "posts/returning-to-rss-reader.md" >}})的時代，很多人可能忘記了一個更直接、更純粹的內容訂閱方式:RSS。其實許多平台都保留了這個功能，只是沒有大張旗鼓地宣傳而已。

## YouTube 的隱藏訂閱功能

YouTube 雖然沒有明說，但其實一直都支援 RSS 訂閱。如果你想訂閱某個頻道，不需要登入 YouTube 帳號，也不會被推薦演算法干擾，只要取得頻道 ID 就可以了。

操作步驟很簡單:

1. 打開你想訂閱的頻道頁面
2. 找到「分享頻道」按鈕
3. 點選「複製頻道 ID」
4. 將頻道 ID 加到這個網址後面:`https://www.youtube.com/feeds/videos.xml?channel_id=`

舉例來說,[財經搖滾 林茂昌](https://www.youtube.com/@財經搖滾林茂昌)的 RSS 訂閱連結就是:

```
https://www.youtube.com/feeds/videos.xml?channel_id=UCNd3EYfxOJ5h2ksY0hyMS7Q
```

把這個網址貼到你的 RSS 閱讀器，就能收到該頻道的最新影片更新。

## PTT 也有 RSS 訂閱

PTT 同樣支援 RSS 訂閱，不過使用的是 Atom 格式(稍後會解釋和 RSS 的差異)。只要知道看板的英文名稱，就能組出訂閱連結。

格式是:`https://www.ptt.cc/atom/看板名稱.xml`

例如 book 版的訂閱連結就是:

```
https://www.ptt.cc/atom/book.xml
```

## Atom 與 RSS 的關係(由 AI 根據網路資料整理生成)

你可能注意到，上面提到 YouTube 使用 RSS，而 PTT 使用 Atom。這兩者其實都是「網路訂閱格式」，功能相似，但有些技術上的差異。

RSS(Really Simple Syndication)發展較早，在 1999 年就出現了，而 Atom 則是 2005 年才誕生的標準。Atom 的出現，某程度上是為了解決 RSS 格式的一些問題和模糊地帶。

### 主要差異

**標準化程度**
- RSS 2.0 由 Harvard 大學管理,標準相對寬鬆
- Atom 是 IETF 標準(RFC 4287),規格更嚴謹

**內容格式**
- RSS 只支援純文字或跳脫的 HTML
- Atom 可以在同一個欄位中提供多種內容類型，甚至直接嵌入 XHTML

**國際化支援**
- RSS 只能在 feed 層級指定語言
- Atom 可以在每個元素層級指定語言，對多語言內容更友善

**日期格式**
- RSS 使用較複雜的 RFC 822 格式
- Atom 使用更簡潔的 RFC 3339 格式(ISO 8601 的子集)

**必要欄位**
- RSS 對於每個項目的欄位要求較寬鬆
- Atom 要求每個 entry 都要有 title、id 和 updated 欄位

從技術角度來看,Atom 格式更嚴謹、更現代，也更容易擴充。Google 的許多服務(如 Blogger、Google News)都偏好使用 Atom。不過 RSS 因為出現較早，仍然有廣泛的使用基礎，特別是在 Podcast 領域，RSS 2.0 幾乎是唯一標準。

### 實務上的選擇

對一般使用者來說，不用太在意用的是 RSS 還是 Atom——現代的 RSS 閱讀器兩種格式都支援。只要把訂閱連結加到你的閱讀器中，就能開始追蹤內容更新。

這種訂閱方式的好處是:你完全掌控自己看到的內容，不會被演算法操縱，也不需要擔心平台改變政策。內容創作者直接推送更新給你，中間沒有第三方干預。

[資料來源](https://en.wikipedia.org/wiki/Atom_(web_standard)) [^1] [^2] [^3] [^4]

[^1]: https://www.tutorialspoint.com/difference-between-rss-and-atom
[^2]: https://ittavern.com/difference-between-rss-and-atom/
[^3]: https://danielmiessler.com/blog/atom-rss-why-we-should-just-call-them-feeds-instead-of-rss-feeds
[^4]: https://courses.ischool.berkeley.edu/i290-14/s05/lecture-23/allslides.html


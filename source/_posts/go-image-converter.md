---
title: 圖片格式轉換
date: 2020-04-26 22:42:43
banner: /2020/04/26/go-image-converter/thomas-tucker-unsplash.jpg
thumbnail: /2020/04/26/go-image-converter/thomas-tucker-unsplash.jpg
category:
- Coding
- Docker
tags:
- Golang
- imagemagick
- 圖片格式轉換
- HEIC to JPG
---
# 前言
圖片格式轉換一直是大多數人會遇到的問題，雖然幫忙轉換的網站很多，也都能免費使用。
但如果想用程式處理就不是這麼方便了，尤其網路品質也會影響處理的速度，檔案大的時候慢起來也是花上不少時間。
雖然本機安裝 <a href="https://imagemagick.org/index.php" target="_blanck">imagemagick</a> 就能解決，
但包成 docker 能避免本機環境越來越胖也可以藉由仲介層慢慢加入一些邏輯進去，就決定這樣做了。

# 簡介
<a href="https://github.com/KJ-Chiu/go-image-converter" target="_blanck">Github Repo - go-image-converter</a>
目前能做的事情很單純，把檔案丟進去後就會回傳指定的格式。 Github 裡面有更詳細的說明

## 回傳範例
{% asset_img "postman.jpg" "Postman 回傳範例" %}

# 小結
golang 雖然不是目前的主力開發語言，但它滿適合應用在微服務的架構內。
* 效能不錯
* 自身就能夠啟動伺服器，不需要 Apache 或 Nginx 在前面做代理
* 編譯後執行檔不會太大

# 備註
* 範例圖檔使用 <a style="background-color:black;color:white;text-decoration:none;padding:4px 6px;font-family:-apple-system, BlinkMacSystemFont, &quot;San Francisco&quot;, &quot;Helvetica Neue&quot;, Helvetica, Ubuntu, Roboto, Noto, &quot;Segoe UI&quot;, Arial, sans-serif;font-size:12px;font-weight:bold;line-height:1.2;display:inline-block;border-radius:3px" href="https://unsplash.com/@tents_and_tread?utm_medium=referral&amp;utm_campaign=photographer-credit&amp;utm_content=creditBadge" target="_blank" rel="noopener noreferrer" title="Download free do whatever you want high-resolution photos from Thomas Tucker"><span style="display:inline-block;padding:2px 3px"><svg xmlns="http://www.w3.org/2000/svg" style="height:12px;width:auto;position:relative;vertical-align:middle;top:-2px;fill:white" viewBox="0 0 32 32"><title>unsplash-logo</title><path d="M10 9V0h12v9H10zm12 5h10v18H0V14h10v9h12v-9z"></path></svg></span><span style="display:inline-block;padding:2px 3px">Thomas Tucker</span></a>

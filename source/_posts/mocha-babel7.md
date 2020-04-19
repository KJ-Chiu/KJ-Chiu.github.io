---
title: Mocha 與 Babel7 搭配執行 Unit Test
date: 2020-04-19 22:49:44
category:
- Coding
- Node
tags:
- UnitTest
- Mocha
- Babel7
---
# 前言
許多專案不論前後端都開始使用 ES6 的語法，但是 Mocha 在平常情況下還是不支援 Module 的。
如果要讓單元測試可以順利在專案內運行，需要搭配 Babel 一起使用。

# 安裝步驟
```
yarn add --dev mocha chai
yarn add --dev @babel/register
```

# 使用方式
在 package.json 內的 scripts 加入
```
"scripts": {
  "test": "./node_modules/.bin/mocha --require @babel/register --recursive ./tests/"
}
```

# 採雷
官網說明如果用 Node13 以下的版本，又希望可以套用 Module 時可以增加參數 `--experimental-modules`
但經過實測有點問題：Mocha 會自行嘗試安裝一些套件，但以我的專案為例裝到一半就噴錯了，也看不出所以然。
而且 package.json 還要加入 type module 說明專案性質，應該是還在實驗階段。

## 說明
* 之前的做法 `--compilers js:@babel/register` 已經被 Deprecated，要改用 `--require`
* 需要這樣做主要是要用 babel 協助轉譯。如果本來的寫法就是用如 `require()` 等 ES6 以前的寫法就不需要額外增加參數

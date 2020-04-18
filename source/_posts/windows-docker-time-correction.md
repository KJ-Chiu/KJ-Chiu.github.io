---
title: Windows 10 Docker Container 時間校正
date: 2020-04-16 01:08:54
banner: /2020/04/16/window-docker-time-correction/Hyper-V-Banner.jpg
tags:
- Windows10
- Docker
- TimeCorrection
---
## 前言
由於在 Container 的環境內開發、測試，常常一開機就啟動一個工作站 Docker Image，放到下次電腦重新開機才會需要再次啟動 Image。
通常都不會有問題，但遇到需要驗證時間的需求時（如 JWT Token 驗證），就會比較麻煩了。

## 發生原因
Container 在啟動時不會有時間不同步的問題。問題發生在 Windows 休眠喚醒之後，Windows 會自動校正時間，但 Container 會從休眠當下的時間繼續往下走。
如果電腦來回休眠個幾次，時間就會差到好幾小時甚至好幾天了。

## 解法
1. Windows 10 有 `Hyper-V 管理員` ，可以從左下角搜尋中找到

{% asset_img "Hyper-V-Search.jpg" "Hyper-V Search" %}

2. 進去後選擇 DockerVM ，點選右邊的 `設定`

{% asset_img "VM-Setting.jpg" "VM Setting" %}

3. 裡面的整合服務，如果原本 `時間同步化` 沒有勾選，勾選後套用
> 如果本來就勾選了，先取消套用後，勾選再套用

{% asset_img "Re-Sync.jpg" "Re Sync" %}

4. 不需要重新啟動 Container 在裡面重新驗證一次時間就會恢復正常

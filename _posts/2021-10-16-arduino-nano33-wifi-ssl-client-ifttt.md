---
title:  "使用 WiFiNINA + IFTTT 傳送訊息"
permalink: /arduino nano33 iot/wifi-ssl-client-ifttt/
excerpt: "當 NINO33 可以連上網路時，傳送信件或是 LINE 訊息可以這麼簡單。"
header:
  teaser: assets/images/nano33iot/WiFiNINA_Firmware_Updater.png
search: false
categories: 
  - Arduino NANO33 IoT
tags:
  - Arduino
  - nano33iot
  - 物聯網
  - IFTTT
  - WiFiNINA
last_modified_at: 2021-10-16T09:00-16:30
toc: true
sidebar:
  nav: "arduino nano33 iot"
author_profile: false
---


今日課程上，老師卻遇到了一個奇怪的情況，上述的範例，同學們都成功了，但只有少部份的人失敗，在 `client.connect(server,443)` 後，能夠成功連線到 server，但在呼叫 API 時，卻沒有回應，連線卻斷了。經過一番的研究與查找，終於解決這個問題，方法是在 WiFiNINA Firmware Updater 把呼叫的 Server 加入即可，例如下圖在 3. Update SSL root certificates 加入 `maker.ifttt.com`，這時候再次上傳程式到 NINO33，就可以正常呼叫 IFTTT 的 API 了。

<figure class="align-center">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/images/nano33iot/WiFiNINA_Firmware_Updater.png" alt="">
</figure> 



## 參考文章
1. 

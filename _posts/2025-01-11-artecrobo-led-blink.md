---
title:  "Artecrobo - LED與直流馬達"
permalink: /aiot camp/artecrobo-led-dc-motor/
excerpt: "利用聲音感測器控制LED的燈熄與燈滅，並且利用聲音的大小控制直流馬達驅動的速度。"
header:
  teaser: assets/images/aiot_camp/20250111_led_dc_motor.png
search: false
categories: 
  - 機器人體驗營
tags:
  - AIOT
  - Python
  - 物聯網
  - 直流馬達
  - LED
sidebar:
  nav: "aiot camp"
author_profile: false
last_modified_at: 2025-01-12T10:00-00:00
toc: true
---

<figure class="align-center">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/images/aiot_camp/20250111_led_dc_motor.png" alt="">
</figure> 

這是我們第一次全家去科教館參加機器人程式體驗營，此次使用的是 Artecrobo 教具與 Studuino Software 來開發，二個小時的時間，我們學習到如何用聲音感測器控制 LED 的燈熄與燈滅，並結合直流馬達組裝一台小車，也是利用聲音感測器來驅動小車的前進。

## 教具準備
* Artec 的積木
* Artecrobo 主機板
* 聲音感測器 x 1
* LED x 3

<figure class="align-center">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/images/aiot_camp/20250111_led_dc_motor_1.png" alt="">
</figure> 


## 安裝 Studuino

Studuino 的介面就跟 Scratch 一樣都是可以使用積木來編寫程式，對於還不會使用文字編程的人算是很友善的環境，它支援了 Windows、Mac、Raspberry Pi、iPad、Android、Chromebook等系統。可以依照你的作業系統環境至下面下載。

Studuino 下載連結：[https://www.artec-kk.co.jp/studuino/zh/select.php](https://www.artec-kk.co.jp/studuino/zh/select.php)

## 聲音控制LED的燈熄燈滅

目標：利用聲音感測器控制 LED 的燈熄燈滅，依聲音大小分「小、中、大」三個等級。
  * 小：亮一顆燈
  * 中：亮二顆燈
  * 大：亮三顆燈

程式邏輯：主要是使用 `if ~ else` 來判斷，邏輯說明如下：

```python
while True:
  value = A01聲音感測器的值

  if value > 4:
    A02 的 LED 燈熄
  else:  
    A02 的 LED 燈滅

  if value > 20:
    A03 的 LED 燈熄
  else:  
    A03 的 LED 燈滅

  if value > 39:
    A04 的 LED 燈熄
  else:  
    A04 的 LED 燈滅
```

## 聲音控制直流馬達前進
目標：利用聲音感測器控制 LED 的燈熄燈滅，依聲音大小分「小、中、大」三個等級。
  * 小：亮一顆燈
  * 中：亮二顆燈
  * 大：亮三顆燈

程式邏輯：主要是使用 `if ~ else` 來判斷，邏輯說明如下：

```python
while True:
  value = A01聲音感測器的值

  if value > 4:
    A02 的 LED 燈熄
  else:  
    A02 的 LED 燈滅

  if value > 20:
    A03 的 LED 燈熄
  else:  
    A03 的 LED 燈滅

  if value > 39:
    A04 的 LED 燈熄
  else:  
    A04 的 LED 燈滅
```

{% include video id="W09unS0kWqY" provider="youtube" %}

## 參考文章
1. [樂益文創股份有限公司](https://www.tigergroup.com.tw/)
2. [Studuino](https://www.artec-kk.co.jp/studuino/zh/)
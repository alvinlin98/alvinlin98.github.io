---
title:  "輸出與輸入"
permalink: /python_basic/3-3-print-input/
excerpt: "Python 的輸入與輸出功能是程式與使用者互動的重要基礎，主要透過內建函式 input() 和 print() 來實現。"
header:
  teaser: assets/images/python_basic/3-3-print-input.png
search: false
categories: 
  - Python零基礎入門班
tags:
  - Python
  - 數值
  - DataType
sidebar:
  nav: "python_basic"
author_profile: false
last_modified_at: 2024-12-05T21:00-00:00
toc: true
---

<figure class="align-center">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/images/python_basic/3-3-print-input.png" alt="">
</figure> 

# print 輸出

print() 函式用於將資料輸出到螢幕，語法為：

print(value,..., sep=" ", end="\n", file=sys.stdout, flush=False)

主要參數：
* `value,...`：要輸出的內容，可以是多個項目，項目之間以「,」分隔。
* `sep`：輸出項目之間的分隔符號，預設為空格 " "。
* `end`：輸出結束後的字元，預設為換行符號 "\n"。
* `file`：輸出目標，預設為標準輸出 sys.stdout，也就是螢幕，也可以使用此設定輸出到檔案或設備。
* `flush`：是否立即將輸出刷新到螢幕，預設為 False，也就是不清除。

```python
print("Hello, World!")  # 輸出字串
print("Python", "輸出", "範例", sep=" - ")  # 使用自訂分隔符號
print("這是第一行", end=" ")  # 不換行，將結尾字元改為空格
print("這是同一行的內容")
```

# 字串格式化

Python 提供多種方法進行格式化輸出，以下介紹三種常用的方式：

* 「%」字串格式化（舊式格式化）

使用 % 運算符進行字串格式化，語法為：

`print(項目 % (參數列))`

常用的參數有：

|---|---|
|參數|意義|
|`%d`|以整數資料型態輸出。|
|`%s`|以字串資料型態輸出。|
|`%f`|以浮點數資料型態輸出。|
|`%%`|以字串中顯示「%」。|
|`%e` 或 `%E`|以科學記號方式輸出。|

例如以字串格式化方式列印字串及整數：

```python
name = "林小宇"
score = 98
print("%s 的成績為 %d" % (name, score))  # 林小宇 的成績為 98
```

即以「%s」代表字串、「%d」代表整數、「%f」代表浮點數，字串格式化方式**可以精確控制列印位置**，例如：

  * %5d：固定列印 5 個字元，若少於 5 位數，會在數字左方填入空白字元，若大於 5 位數則會全部列印，輸出內容會靠右對齊。
  * %5s：固定列印 5 個字元，若字串少於 5 字元，會在字串左方填入空白字元，若大於 5 個字元則會全部列印，輸出內容會靠右對齊。
  * %8.2f：固定列印 8 個字元(含小數點)，小數固定列印 2 位數。若整數少於 5 位數（8-3=5），會在數字左方填入空白字元，若小數小於 2 位數，會在數字右方填入「0」的字元。

例如：

```python
height = 152.5
# 在 height 前有二個空白
print("身高為%8.2f公分" % height)  # 身高為  152.50公分
``` 

前述格式化的數值若使用「負數」，表示如果需要填入空白字元，則空白字元會填在右方，例如：

```python
height = 152.5
# 在 height 後方二個空白
print("身高為%-8.2f公分" % height)  # 身高為152.50  公分
``` 

* 「format」字串格式化

使用 `{}` 作為佔位符，並透過 `format()` 進行替換，此為新版的使用方式，建議採用此法進行字串格式化，語法為：

`print(字串.format(參數列))`

例如以字串的 `format()` 方式列印字串及整數：

```python
name = "林小宇"
score = 98
print("{}的成績為{}".format(name,score))  # 林小宇的成績為98
```

第一對大括號代表第一個參數，第二對大括號代表第二個參數，不用考慮資料格式。
若有多個參數時，可以在括號中放入參數的順序索引（從 0 開始），例如：

```python
print("{1}的成績為{0}".format(98,"林小宇"))  # 林小宇的成績為98
```

如果想要精確控制字串格式，可以在字串中的大括號內設定「`參數順序：格式設定`」，其中的格式設定同「%」字串格式化的參數格式設定。
特別注意的是字串會預設靠左對齊，數字會靠右對齊，例如：

```python
print("{0}的成績為{1}".format("林小宇",98)) # 林小宇的成績為98
print("{0:5s}的成績為{1:3d}".format("林小宇",98))  # 林小宇  的成績為 98
print("{0:5}的成績為{1:3}".format("林小宇",98))
print("{:5}的成績為{:3}".format("林小宇",98))
```

## 範例實作：格式化列印成續單

| 姓名   | 名次 | 國文 | 數學 | 英文 |
|:-------|:----:|-----:|-----:|-----:|
| 林小宇 |   1  |   98 |  100 |   98 |
| 江士源 |   2  |  100 |   98 |   98 |
| 王聰明 |   3  |   96 |   96 |   96 |

```python
print("姓名   名次  國文  數學  英文")
print("%3s  %2d   %3d   %3d   %3d" % ("林小宇", 1, 98, 100, 98))
print("%3s  %2d   %3d   %3d   %3d" % ("江士源", 2, 100, 98, 98))
print("%3s  %2d   %3d   %3d   %3d" % ("王聰明", 3, 96, 96, 96))
```

# input 輸入

input() 函式用於接收使用者的輸入，語法為：

變數 = input([提示字串])

在程式執行時，會顯示提示字串並等待使用者輸入。輸入的內容會以 `字串 (string)` 的形式返回。

* 輸入字串

```python
name = input("請輸入你的名字: ")  # 提示使用者輸入
print("你好,", name)  # 輸出使用者輸入的內容
```

* 輸入數值

若需要將輸入的內容轉為數值，可以使用 `int()` 或 `float()` 進行型別轉換：

```python
age = int(input("請輸入你的年齡: "))  # 轉換為整數
print("你的年齡是:", age)
```

## 範例實作：計算成績總分

林小宇剛考完期中考，他設計子小程式給老師輸入語文、英文、數學成績後會自動合計總分。

```python
name = input("請輸入學生姓名： ")
chinese = int(input("請輸入語文成績： "))
english = int(input("請輸入英文成績： "))
math = int(input("請輸入數學成績： "))
total = chinese + english + math
print("學生「{0}」的總成續是：{1:3d}".format(name,total))
```

# 常用函數

| 函數 | 說明 | 範例 |
| --- | --- | --- |
| eval() | 去掉參數最外側引號並執行餘下語句再返回其結果 | a = eval("1") <br> print(a) <br> b = eval("1+2") <br> print(b)| 

```python
print("'1+2'") # '1+2'
eval('print("Hello")') # Hello

english = input("請輸入英文成績： ")  # '98'，型別是字串 
math = eval(input("請輸入數學成績：")) # 100，型別是數值
```

# 實作練習

## Lab 1：溫度轉換

請輸入帶有攝氏(C)或華氏(F)溫度符號的溫度值，例如輸入攝氏的 `30C` 則回傳華氏的 `86.0F`，若輸入格式不是上述的則回傳 `輸入格式錯誤`。

```python
TempStr = input("請輸入帶有符號的溫度值：")
if TempStr[-1] in ['F','f']:
    C = (eval(TempStr[:-1]) - 32) / 1.8
    print("轉換後的溫度是{:.2f}C".format(C))
elif TempStr[-1] in ['C','c']:
    F = 1.8 * eval(TempStr[:-1]) + 32
    print("轉換後的溫度是{:.2f}F".format(F))
else:
    print("輸入格式錯誤")
```

----- 

# 隨堂測驗

<iframe src="https://docs.google.com/forms/d/e/1FAIpQLScP4Y8q1t_bIM6MMNkJodSj0VfNdKXlEVXJ52-DLg6SAOe1vg/viewform?embedded=true" width="640" height="1900" frameborder="0" marginheight="0" marginwidth="0">載入中…</iframe>
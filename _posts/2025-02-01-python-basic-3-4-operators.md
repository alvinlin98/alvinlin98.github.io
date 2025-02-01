---
title:  "運算式"
permalink: /python_basic/3-4-operators/
excerpt: "運算子是對運算元執行某些操作並傳回結果的特殊符號，在數值章節已知道算術運算子，本章繼續探討其它的。"
header:
  teaser: assets/images/python_basic/3-4-operators.png
search: false
categories: 
  - Python零基礎入門班
tags:
  - Python
  - 運算子
  - Operator
sidebar:
  nav: "python_basic"
author_profile: false
last_modified_at: 2025-02-01T19:00-21:00
toc: true
---

<figure class="align-center">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/images/python_basic/3-4-operators.png" alt="">
</figure> 

運算子是對運算元執行某些運算並傳回結果的特殊符號。例如，`5 + 6` 是一個表達式，其中是一個運算符，它對數值左側運算元和右側運算元執行算術加法運算，並傳回兩個運算子的總和作為結果。

# 算術運算子 (Arithmetic Operator)

用於執行一般數學運算的運算子稱為「算術運算子」，算術運算子傳回結果的類型取決於運算元的類型，如下所示：

1. 如果任一操作數是複數，則結果將轉換為複數；
1. 如果任一操作數是浮點數，則結果將轉換為浮點數；
1. 如果兩個操作數都是整數，則結果也是整數，不需要轉換。

| 運算子 | 說明 | 範例 |
|:-----:|:-----|:-----|
| + | 兩運算元相加 | x, y = 5, 6 <br> print(x + y) # 11 |
| - | 兩運算元相減 | x, y = 5, 6 <br> print(x - y) # -1 |
| * | 兩運算元相乘 | x, y = 5, 6 <br> print(x * y) # 30 |
| / | 兩運算元相除 | x, y = 6, 3 <br> print(x / y) # 2.0 |
| % | 取得餘數 | x, y =11, 3 <br> print(x % y) # 2 |
| // | 取得整除的商數 | x, y = 6, 5 <br> print(x // y) # 1 |
| ** | 運算元1的運算元2的次方 | x, y = 2, 3 <br> print(x ** y) # 8 |


**注意：** 「/」、「%」與「//」三個運算子與除法有關，第二個運算元不能為零，否則會出現「ZeroDivisionError」的錯誤。
{: .notice--info} 

## 賦值運算子 (Assignment Operators)

賦值運算子用於給變數賦值。下表列出了 Python 中的所有算術運算子：

| 運算子 | 說明 | 範例 |
|:-----:|:-----|:-----|
| = |  等號，賦值給變數 | x = 5； |
| += | 相加後再賦值給原變數  | x = 5 <br> x += 5 <br> print(x) # 10 |
| -= | 相減後再賦值給原變數  | x = 5 <br> x -= 2 <br> print(x) # 3 |
| *= | 相乘後再賦值給原變數  | x = 2 <br> x *= 3 <br> print(x) # 6 |
| /= | 相除後再賦值給原變數  | x = 6 <br> x /= 3 <br> print(x) # 2 |
| //= | 相除得到整除商數後再賦值給原變數  | x = 6 <br> x //= 5 <br> print(x) # 1 |
| %= | 相除得到餘數後再賦值給原變數 | x = 11 <br> x %= 3 <br> print(x) # 2 |
| **= | 做指數運算後再賦值給原變數  | x = 10 <br> x **= 3 <br> print(x) # 1000 |


## 比較運算子 (Comparision Operators)

比較運算子是比較兩個運算元並傳回布林值 `True` 或 `False`。下表列出了 Python 中的比較運算子。

| 運算子 | 說明 | 範例 |
|:-----:|:-----|:-----|
| > | 如果左運算元大於右運算元，則為 True  | x, y = 5, 6 <br> print(x > y) # False |
| < | 如果左運算元小於右運算元，則為 True  | x, y = 5, 6 <br> print(x < y) # True |
| == | 如果運算元相等則為 True  | x, y = 5, 6 <br> print(x == y) # False |
| != | 如果運算元不相等則為 True  | x, y = 5, 6 <br> print(x != y) # True |
| >= | 如果左運算元大於或等於右運算元，則為 True  | x, y = 5, 6 <br> print(x >= y) # False |
| <= | 如果左運算元大於或等於右運算元，則為 True  | x, y = 5, 6 <br> print(x <= y) # True |

## 邏輯運算子(Logical Operators)

邏輯運算子通常是結合多個比較運算式來綜合得到最終比較結果。

| 運算子 | 說明 | 範例 |
|:-----:|:-----|:-----|
| and | 若兩者均為 True，則為 True  | x, y = 5, 6 <br> print(x > 1 and y < 10) # True |
| or | 如果至少有一個為 True，則為 True | x, y = 5, 6 <br> print(x > 6 or y < 10) # True |
| not | 如果表達式計算結果為 False，則傳回 True，反之亦然 | x = 5 <br> print(not x > 1) # False |

## 恆等運算子 (Identity Operators)

恆等運算子檢查兩個物件是否具有相同的 id 值。

| 運算子 | 說明 | 範例 |
|:-----:|:-----|:-----|
| is | 若兩者物件值相同時，則為 True | x, y = 5, 6 <br> print(x is y) # Fasle |
| is not | 若兩者物件值不相同時，則為 True | x, y = 5, 6 <br> print(x is not y) # True |

## 成員運算子 (Membership Test Operators)

在 Python 中， `in` 和 `not in` 是成員運算子，它們適用於測試是否在序列 (List、String、Tuple、Set、Dictionary) 中找到值或變數。

| 運算子 | 說明 | 範例 |
|:-----:|:-----|:-----|
| in | 如果序列包含指定項，則傳回 True，否則傳回 False。 | nums = [1,2,3,4,5] <br> print(1 in nums) # True <br> print(10 in nums) # False <br> print('str' in 'string') # True |
| not in | 如果序列不包含指定項，則傳回 True，否則傳回 False。 | nums = [1,2,3,4,5] <br> print(1 not in nums) # False <br> print(10 not in nums) # True <br> print('str' not in 'string') # False  |


## 位元運算子(Bitwise Operators)

位元運算子對二進位操作數執行運算。

| 運算子 | 說明 | 範例 |
|:-----:|:-----|:-----|
| & | 如果兩個位元都是 1，則將每個位元設為 1，詳如下文程式解說。 | x, y = 13, 11 <br> print(x & y) # 9 |
| \| | 如果兩個位元中有一位為 1，則將每個位元設為 1。 | x, y = 13, 11 <br> print(x \| y) # 15 |
| ^ | 如果兩個位元中只有一個為 1，則將每個位元設為 1。 | x, y = 13, 11 <br> print(x ^ y) # 6 |
| ~ | 反轉所有位元，x 的按位取反結果為-(x+1)。 | x = 5 <br> print(~x) # -6 |
| \<\< | 透過從右側推入零來進行左移，並讓最左邊的位掉落。 | x = 5 <br> print(x\<\<2) # 20 |
| \>\> | 透過從左側推入最左邊位的副本來向右移動，並讓最右邊位脫落。 | x = 13 <br> print(x\>\>2) # 3 |

在實務上，常利用 & 來設計權限。
{: .notice--info}

```python
a = 0b1101  # 二进制表示，等于 13
b = 0b1011  # 二进制表示，等于 11

result = a & b  # 按位与
print(result) # 9
print(bin(result))  # 输出：0b1001
```

```yaml
   1101  # a
&  1011  # b
--------
   1001  # result
```

# 實作練習

## Lab 1：權限設計

| id | 姓名\功能 | 刪除(8) | 更新(4) | 新增(2) | 檢視(1) |
|:---:|:-----|:-----:|:-----:|:-----:|:-----:|
| A01 | Owen爸 | V | V | V | V |
| A02 | 林小宇 | X | V | V | V |
| A03 | 江士源 | X | X | X | V |
| A04 | 王聰明 | V | X | X | V |

將上表轉成二進位如下
```python
A01 = 0b1111 # 15
A02 = 0b0111 # 7
A03 = 0b0001 # 1
A04 = 0b1001 # 9

# 檢查誰有刪除權限
AA = [A01, A02, A03, A04]
for A in AA:
  if A & 8 > 0:
    print(A)

# 檢查林小宇是否有更新權限
if A02 & 4 > 0:
  print("yes")
else:
  print("no")

# 檢查江士源是否有刪除權限
if A03 & 8 > 0:
  print("yes")
else:
  print("no") 
```



----- 

# 隨堂測驗


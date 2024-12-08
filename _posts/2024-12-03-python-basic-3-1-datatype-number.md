---
title:  "資料型別-數值"
permalink: /python_basic/3-1-datatype-number/
excerpt: "Python 的數值型別包括整數 (int)、浮點數 (float)、布林值 (boolean)，支援數學運算與大範圍數值表示，精度靈活。"
header:
  teaser: assets/images/python_basic/3-1-datatype-number.png
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
last_modified_at: 2024-12-03T21:00-00:00
toc: true
---

<figure class="align-center">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/images/python_basic/3-1-datatype-number.png" alt="">
</figure> 

# 資料型別 (Data Types)

Python 提供了幾種不同類型的資料型別，有簡單的資料型別如數值型別與字串型別，也有較複雜的資料型別如串列、集合與字典等，這裡先來了解簡單的資料型別。

## 數值型別 (Number)

- `int`：整數，正整數或負整數（沒有小數部分），例如 -10、10、456、4654654。
    
    ```python
    num1 = 10      # 正整數 
    print(num1)
    
    num2 = -10     # 負整數
    print(num2)
    print(type(num2)) # <class 'int'>
    
    x=1234567890
    print(type(x))
    
    y=5000000000000000000000000000000000000000000000000000000
    print(type(y))
    ```
    
    注意：Python 中不允許非零整數的前導零，例如 000123 是無效數字，0000 變成 0。
    
    ```python
    x=001234567890    
    # SyntaxError: leading zeros in decimal integer literals are not permitted; use an 0o prefix for octal integers
    z = 0000
    print(z) # 0
    ```
    
- `float`：浮點數，具有浮點表示形式的任何數值，其中小數部分由小數符號或科學記號 E 或 e 表示，例如 1.23、3.4556789e2。
    
    ```python
    num3 = 1.23    # 浮點數
    print(num3)
    print(type(num3)) # print(type(num3))
    
    f = 1e3
    print(f) # 1000.0
    
    f = 1e5
    print(f) # 100000.0
    
    f = 3.4556789e2
    print(f) # 345.56789
    print(type(f)) # <class 'float'>
    ```
    
    注意：浮點數間運算存在不確定尾數，不是 bug，這涉及到計算機對數字運算的內部原理，這裡就不深入討論，解決的方式就是用 `round()` 函式。
    
    ```python
    print(0.1 + 0.3)    # 0.4
    print(0.1 + 0.2)    # 0.30000000000000004
    
    print(0.1 + 0.2 == 0.3)            # False
    print(round(0.1 + 0.2,1))          # 0.3
    print(round(0.1 + 0.2,1) == 0.3)   # True
    ```
    
- `bool`：布林值，此資料型別只有二個值，分別是 `True` 與 `False` ，請注意，“T” 和 “F” 是大寫字母。`true`和`false`不是有效的布林值，Python 會為它們拋出錯誤。
布林值也具有數值 `True` 的數值是「1」，`False` 的數值是「0」，因此布林值也可以跟數值進行運算。
    
    ```python
    isNum = True   # 布林值
    print(isNum)
    print(type(isNum)) # <class 'bool'>
    
    num5 = num1 + isNum    # 值為 11
    print(num5)
    print(type(num5)) # <class 'int'>
    
    num6 = num3 + isNum    # 值為 2.23
    print(num6)
    print(type(num6)) # <class 'float'>
    ```
    
- `None` ：空型別，表示空物件。
    
    ```python
    num4 = None    # 空物件
    print(type(num4)) # <class 'NoneType'>
    num7 = num4 + num3 # TypeError
    ```
    
    空型別是無法拿來運算的，上述會得到下列錯誤。
    
    ```python
    TypeError: unsupported operand type(s) for +: 'NoneType' and 'float'
    ```
    

上述整數都是以「十進制」表示，整數也可以用「二進制」、「八進制」與「十六進制」表示。

- 二進制：以 `0b` 或 `0B` 開頭，如 0b010，-0B101。
    
    ```python
    b = 0b010   # 二進制
    print(b)    # 值為 2
    
    B = -0B101  # 二進制
    print(B)    # 值為 -5
    print(type(B)) # <class 'int'>
    ```
    
- 八進制：以 `0o` 或 `0O` 開頭，如 0o123，-0O45。
    
    ```python
    o = 0o123   # 八進制
    print(o)    # 值為 83
    
    O = -0O45   # 八進制
    print(O)    # 值為 -37
    print(type(O)) # <class 'int'>
    ```
    
- 十六進制：以 `0x` 或 `0X` 開頭，如 0x9a，-0X89。
    
    ```python
    h = 0x9a   # 十六進制
    print(o)    # 值為 83
    
    H = -0X89   # 十六進制
    print(O)    # 值為 -37
    print(type(H)) # <class 'int'>
    ```

## 算術運算子(Arithmetic Operator)

用於數學計算的運算子就稱為「算術運算子」，運算子依據運算元的個數分成下列二種：

- 單元運算子：只有一個運算元。如賦值給變數 a = 10，「+ a」就是 a 本身，「- a」就是 a 的負值。
- 二元運算子：具有左右兩方的運算元。如賦值給變數 a, b = 10, 20，「a + b」中的 + 位於兩運算元的中間就是二位運算子。

運算子如下表所列：

| 運算子 | 說明 | 範例 |
| --- | --- | --- |
| + | 加，兩運算元相加的程 | a, b = 10, 20 <br> print(a + b)  # 30 |
| - | 減，兩運算元相減的差 | a, b = 10, 20 <br> print(a - b)  # -10 |
| * | 乘，兩運算元相乘的積 | a, b = 10, 20 <br> print(a * b)  # 200 |
| / | 除，兩運算元相除的值 | a, b = 10, 20 <br> print(b / a)  # 2.0 |
| // | 整除數，取得兩運算元相除的商數 | a, b = 9, 2 <br> print(a // b)  # 4 |
| % | 餘數，取得兩運算元相除的餘數 | a, b = 10, 3 <br> print(a % b)  # 1 |
| ** | 次方，左運算元的右運算次方 | a, b = 3, 2 <br> print(a ** b)  # 9 |

當右運算元的值為小數時，例如次方運算 10 ** 0.5 結果是 $\sqrt{10}$

二元運算子也同時具有運算與指定的功能，例如下面程式將變數 x 值增加 1：

```python
x = x + 1 
```

這樣寫會發現變數名稱寫了 2 次，所以 Python 中可以簡化成下面：

```python
x += 1  # 就是 x = x + 1
```

因此這樣的複合運算子如下表所列：

設下列每一個運算 `x = 5` 

| 運算子 | 說明 | 範例 |
| --- | --- | --- |
| += | 相加後再指定給原變數 | x += 2 <br> print( x )  # 7 |
| -= | 相減後再指定給原變數 | x -= 2 <br> print( x )  # 3 |
| *= | 相乘後再指定給原變數 | x *= 2 <br> print( x )  # 10 |
| /= | 相除後再指定給原變數 | x /= 2 <br> print( x )  # 2.5 |
| //= | 相除得到整除商數後再指定給原變數 | x //= 2 <br> print( x )  # 2 |
| %= | 相除得到餘數後再指定給原變數 | x %= 2 <br> print( x )  # 1 |
| **= | 做指數運算後再指定給原變數 | x **= 2 <br> print( x )  # 25 |

## 數值函數

下列是常用的數值函數，提供數值型別之間的轉換與處理。

| 函數 | 說明 | 範例 |
| --- | --- | --- |
| int() | 整數，強制轉換數值為整數型別。 | x = 2.5  # 浮點數 <br> y = int(x)  # 整數 <br> print(y)  # 2 <br> Print(type(y))  # <class 'int'> | 
| float() | 浮點數，強制轉換數值為浮點數型別。 | x = “2.5”  # 字串 <br> print(float(x))  # 2.5 |
| abs() | 絕對值，返回 x 的絕對值。 | x = -10.01 <br> print(abs(x))  # 10.01  |
| round() | 四捨五入到指定的小數位數。 | x = round(3.14159,2) <br> print(x) |
| divmod() | 返回整除後的商數和餘數。 | x = divmod(7, 3) <br> print(x)  # (2, 1) |
| pow(x) | 返回 x 的 y 次方，等同於 x**y | x = pow(3, 7) <br> print(x)  # 2187 |
| bin() | 返回整數的二進位字串。 | x = bin(128) <br> print(x)  # '0b10000000’ |
| oct() | 返回整數的八進位字串。 | x = oct(128) <br> print(x)  # '0o200’ |
| hex() | 返回整數的十六進位字串。 | x = hex(128) <br> print(x)  # '0x80’ |
| min() | 返回參數中的最小值 | x = min(1, 3, 2) <br> print(x)  # 1 |
| max() | 返回參數中的最大值 | x = max(1, 3, 2) <br> print(x)  # 3 |

# 實作練習

## Lab 1：進步的力量

林小宇能保持第一名的技巧是每天都進步一點，一年 365 天， 他每天進步 1%，請問共累計進步多少呢？

解析：

這裡用數學解題即：

$1.01^{365}$ = 37.78343433288728

```python
dayup = 1.01 ** 365
print(dayup)  # 37.78343433288728
```

用 Python 的數學函數解題即：

```python
dayup = pow(1.01, 365)
print(dayup)  # 37.78343433288728
```

哇呜，我們看到持之以恆一年後居然進步了 37 倍有餘，是不是很驚人啊！

## Lab 2：退步的後果

反觀武技安每天都退步一點，一年 365 天，他每天都退步 1%，請問共累計退步多少呢？

這裡用數學解題即：

$0.99^{365}$ = 0.025517964452291125

```python
daydown = 0.99 ** 365
print(daydown)  # 0.025517964452291125
```

用 Python 的數值函數解題即：

```python
daydown = pow(0.99, 365)
print(daydown)  # 0.025517964452291125
```

哦喔~ 持續懈怠了一年後，僅剩不到 3%，與天天向上的林小宇比較起來已經是很可怕的差距了。

## Lab 3：1 加到 100

這裡也可以用數學的方式一個個相加，如下：

```python
ans = 1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 9 + 10 + 11 + 12 + 13 + 14 + 15 + 16 + 17 + 18 + 19 + 20 + 21 + 22 + 23 + 24 + 25 + 26 + 27 + 28 + 29 + 30 + 31 + 32 + 33 + 34 + 35 + 36 + 37 + 38 + 39 + 40 + 41 + 42 + 43 + 44 + 45 + 46 + 47 + 48 + 49 + 50 + 51 + 52 + 53 + 54 + 55 + 56 + 57 + 58 + 59 + 60 + 61 + 62 + 63 + 64 + 65 + 66 + 67 + 68 + 69 + 70 + 71 + 72 + 73 + 74 + 75 + 76 + 77 + 78 + 79 + 80 + 81 + 82 + 83 + 84 + 85 + 86 + 87 + 88 + 89 + 90 + 91 + 92 + 93 + 94 + 95 + 96 + 97 + 98 + 99 + 100
pring(ans)  # 5050
```
這樣進行 99 次相加一樣可以得到答案，但無論是用數學或 Python 一個個相加的速度就要花好幾分鐘。那麼想一想有沒有其它更有效率的方式？ 

接下來我們把 1 到 100 的數字進行分組，分解為最前的數字與最後的數字一組，如 1 與 100、2 與 99、3 與 98、...以此類推到 50 與 51 等兩兩一組，我們會發現每組合計是 101，共分了 50 組，所以 101 * 50 就可以得知 1 加到 100 的值為何了。

```python
ans = 101 * 50
print(ans)  # 5050
```

從這個案例可以讓我們看到為了解決問題而演化出更有效率的方式，這就是演算法，所以不要氣餒，沒有做不到，只有想不到。

----- 

# 隨堂測驗

<iframe data-tally-src="https://tally.so/embed/n0b28P?alignLeft=1&hideTitle=1&transparentBackground=1&dynamicHeight=1" loading="lazy" width="100%" height="1307" frameborder="0" marginheight="0" marginwidth="0" title="數值-隨堂測驗
"></iframe><script>var d=document,w="https://tally.so/widgets/embed.js",v=function(){"undefined"!=typeof Tally?Tally.loadEmbeds():d.querySelectorAll("iframe[data-tally-src]:not([src])").forEach((function(e){e.src=e.dataset.tallySrc}))};if("undefined"!=typeof Tally)v();else if(d.querySelector('script[src="'+w+'"]')==null){var s=d.createElement("script");s.src=w,s.onload=v,s.onerror=v,d.body.appendChild(s);}</script>

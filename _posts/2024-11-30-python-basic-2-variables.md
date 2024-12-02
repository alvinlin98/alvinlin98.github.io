---
title:  "變數"
permalink: /python_basic/2-variables/
excerpt: "Python 變數用於存儲數據，透過指派符號 = 賦值，名稱需符合規範，類型隨值自動決定，靈活簡單，易於操作。"
header:
  teaser: assets/images/python_basic/2-variables.png
search: false
categories: 
  - Python零基礎入門班
tags:
  - Python
  - 變數
sidebar:
  nav: "python_basic"
author_profile: false
last_modified_at: 2024-11-30T21:00-00:00
toc: true
---

<figure class="align-center">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/images/python_basic/2-variables.png" alt="">
</figure> 

# 註解

程式註解是讓註解符號之後的程式碼都不會被執行，就像程式碼的說明書，能大幅提升程式碼的可讀性與維護性。

在 Python 有二種註解方式，分別是「單行註解」與「多行註解」，說明如下：

## 單行註解

在程式碼中加入「#」做為註解單行，可以在程式列的起始處，也可以在程式列的最後方，例如：

```python
# 將 3 賦值給變數 A
A = 3
hero.say(A) # 命令英雄說出"變數A"的數值
```

## 多行註解

如果要註解的說明是連續多行，可以在註解的區塊前後加入三個單引號（’’’）或三個雙引號（”””）作為註解多行，例如。

```python
'''
向寶石進發。
小心撞牆！
在下面輸入你的代碼。
'''
```

## 註解的重要性

- 提升可讀性：解釋複雜邏輯、說明變數與函式的用途、提供上下文資訊。
- 增強可維護性：幫助開發人員快速定位問題，方便團隊合作與降低學習成本。
- 作為開發紀錄：記錄開發過程中所做的設計決策與修改的歷程，方便日後回顧和分析。

總結來說，程式註解是程式碼不可或缺的一部分。好的註解不僅能提高程式碼的可讀性和可維護性，還能促進團隊合作，提高程式碼的整體品質。

# 變數 **(Variables)**

Python 變數不需要宣告就可以使用，與 C#、Java 不同，語法為：

```python
變數名稱 = 變數值
```

## Python變數

在 CS1-4 時，我們就學過變數，「變數」是會變化的代數，是一個隨時可能改變內容的容器名稱。

回憶一下 CS1-4 ：

```python
# 將 3 賦值給變數 A
A = 3
hero.say(A) # 命令英雄說出"變數A"的數值
```

使用變數時，不必指定資料型別，Python 會根據變數值設定資料型別。例如上述的 A 變數，系統會設定其資料型別為整數(int)。以同樣的方式，下面宣告不同類型的變數：

```python
num = 10 #integer variable
amount = 78.50 #float variable
greet='Hello World' #string variable
isActive = True #boolean variable
```

## 變數是物件（Objects）

Python 中的變數是物件，變數是基於儲存的值而成為某型別的物件。使用 `type()` 函數取得變數的型別名稱。

```python
num = 10
print(type(num))  #<class 'int'>

amount = 78.50
print(type(amount))  #<class 'float'>

greet='Hello World'
print(type(greet))   #<class 'str'>

isActive = True
print(type(isActive))  #<class 'bool'>
```

Python 中的每個物件都有一個 id。它是物件在記憶體中的位址，以一個整數值表示。如下所示，  `id()` 函數會回傳指定物件存放位置的 id。

```python
x = 100
print(id(x))

greet='Hello'
print(id(greet))
```

## 多變數賦值

如果多個變數具有相同變數值，是可以一起指定變數值的。例如變數 A、B、C 的值皆為 3 ，其賦值的方式為：

```python
A = B = C = 3
```

也可以在同一列中指定多個變數，「變數名稱」之間以「,」分隔，「變數值」之間也以「,」分隔，如下所示。

```python
x, y, z = 10, 'Hello', True
print(x, y, z)  #10 Hello True
```

變數`x`儲存`10`、`y`儲存字串`'Hello'`和`z`儲存布林值`True`。變數的類型是基於指定值的類型。

為每個用逗號分隔的單獨變數賦值將引發語法錯誤，如下所示。

```python
x = 10, y = 'Hello', z = True  # SyntaxError: cannot assign to literal
```

## 刪除變數

變數如果不再使用，可以將變數刪除以節省記憶體。

```python
del 變數名稱
```

## 變數命名規則

1. 只能由大小寫英文字母、數字、底線(_)、中文組成。
2. 第一個字母不可以是數字。
3. 英文字母大小寫視為不同變數名稱。
4. 不能與 Python 系統保留字（也叫關鍵字）相同，如下表所示。
    
    
    | and | as | assert | break | class | continue |
    | --- | --- | --- | --- | --- | --- |
    | def | del | elif | else | except | finally |
    | for | from | False | global | if | import |
    | in | is | lambda | nonlocal | not | None |
    | or | pass | raise | return | try | True |
    | while | with | yield |  |  |  |

雖然可以用中文命名，但建議不要使用，會造成輸入的麻煩與降低程式的可攜性。

下表是錯誤的變數名稱範例：

```python
7eleven = 11  # 第一個字母不可以是數字
H&M = 1       # 不能有特殊字元
H M = 1       # 不能有空白
for = 1       # 不能是系統保留字
If = 1        # 可以，大寫的 If 不是系統保留字
```

# **隨堂測驗**

**Q1. 下列哪一個是定義 Python 的變數？(15分）**

    (A) var name = "Steve”

    (B) string name = "Steve”

    (C) name = "Steve”

    (D) 以上皆是

**Q2. 下列哪一個會出現錯誤？(15分）**
    (A) x, y, z = 10, 20, 30

    (B) x, y, z = 10, “Hello”, True 

    (C) x = 10, y = “Hello”, z = True

    (D) 以上都不會

Q3. 下列哪些敘述是正確的？**(25分）**

    (A) 變數名不能以數字開頭。

    (B)  Python 中的變數名稱有區分大小寫。

    (C) 變數名不能以下劃線「_」開頭。

    (D) 變數名可以是保留關鍵字。

Q4. 下列哪一個是 Python 的註解符號？**(15分）**

    (A) — 

    (B) // 

    (C) # 

    (D) $ 

Q5. 下列哪一個是錯誤的變數名稱？**(15分）**

    (A) For

    (B) break

    (C) str03

    (D) error_i

Q6. 如何取得下列變數的型別？**(15分）**

```python
num = 10
```

    (A) type(num)

    (B) print(num)

    (C) exec(num)

    (D) help(num)

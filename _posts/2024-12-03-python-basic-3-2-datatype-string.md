---
title:  "資料型別-字串"
permalink: /python_basic/3-2-datatype-string/
excerpt: "Python 的字串（str）是不可變的序列，用引號包住的文字，例如 'hello'，用來存放和操作文字資料，簡單易用。"
header:
  teaser: assets/images/python_basic/3-2-datatype-string.png
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
  <img src="{{ site.url }}{{ site.baseurl }}/assets/images/python_basic/3-2-datatype-string.png" alt="">
</figure> 

# 資料型別 (Data Types)

## 字串型別 (String)

Python 字串資料型別是變數值以一對單引號（’）、雙引號（”）或三引號（’’’）括起來。

```python
'This is a string in Python' # 單引號括起來的字串
"This is a string in Python" # 雙引號括起來的字串
'''This is a string in Python''' # 三個單引號括起來的字串
"""This is a string in Python""" # 三個雙引號括起來的字串
```

可以將字串文字指派給變數，如下所示。

```python
str1 = 'This is a string in Python' 
print(str1)

str2 = "This is a string in Python" 
print(str2)
```

由一對三個單引號或三個雙引號括起來的字串，可表示多行的字串。

```python
str1 = '''This is 
the first
Multi-line string.
'''
print(str1)

str2 = """This is
the second
Multi-line
string."""
print(str2)
```

到這裡你可能會發現這不就是前面介紹的註釋嗎？沒錯，在 Python 中其實並沒有真的提供多行註釋，三引號構成的就是字串，只是註釋並沒有賦值給變數。

另外你可能也會好奇，為何提供二種表示方式，不能只提供一種嗎？這是當單引號或雙引號也作為字串的一部份時，如文字需要嵌入雙引號作為字串的一部分，則應將其放入單引號中。同樣，如果字串包含單引號作為字串的一部分，則應將其寫在雙引號中。

```python
str1 = 'Welcome to "Python Tutorial" on TutorialsTeacher'
print(str1)

str2 = "Welcome to 'Python Tutorial' on TutorialsTeacher"
print(str2)
```

字串是字元有序的集合，可以用 `len()` 函數來檢索長度，也可以使用索引取得某個項目的值（字串或字元）。

- 正向遞增序號：從頭部開始向結尾遞增，由 0 向上遞增。
- 反向遞減序號：從結尾向頭部反向遞減，由 -1 開始遞減。

如下表格所示：

| --- | --- | --- | --- | --- | --- | --- | --- | --- | --- | --- |
| -11 | -10 | -9 | -8 | -7 | -6 | -5 | -4 | -3 | -2 | -1 |
| 零 | 壹 | 貳 | 叄 | 肆 | 伍 | 陸 | 柒 | 捌 | 玖 | 拾 |
| 0 | 1 | 2 | 3 | 4 | 5 | 6 | 7 | 8 | 9 | 10 |

取得一個字元：使用 `字串[索引]` 提取字串中指定索引的字元。

```python
str1 = "零壹貳叄"
# 提取索引 2 的字元。
print(str1[2])  # 貳

# 提取索引 -1 的字元。
print(str1[-1]) # 叄
```

取得多個字元：使用 `字串[起始索引:結束索引:間隔值]` 來提取字串裡的字元，表示提取字串從起始索引開始，到結束索引結束，但不含結束索引本身，每次間隔值後再提取字元，而間隔值預設為 1 ，可以不寫。

```python
str1 = "零壹貳叄"
# 提取索引 1 到 2 的字串，不含索引 3。
print(str1[1:3])     # 壹貳

# 提取索引 0 到 2 的字串。
print(str1[0:3])     # 零壹貳
# 若從第一個字元開始，則起始值可以省略不寫。
print(str1[:3])      # 零壹貳

# 提取索引 1 到最後的字串。
print(str1[1:4])     # 壹貳叄
print(str1[1:])      # 壹貳叄

str2 = "零壹貳叄肆伍陸柒捌玖拾"
# 提取索引 3 到 -3 的字串。
print(str2[3:-3])    # 叄肆伍陸柒

#提取索引 -5 到最後的字串。
print(str2[-5:])     # 陸柒捌玖拾

# 提取索引是偶數的字串。
print(str2[::2])     # 零貳肆陸捌拾
# 提取索引是奇數的字串。
print(str2[1::2])    # 壹叄伍柒玖

# 將字串倒過來
print(str2[::-1])    # 拾玖捌柒陸伍肆叄貳壹零

```

字串是一個不可變的物件。因此，無法對其進行修改。嘗試在某個索引處分配不同的字元會導致錯誤。

```python
str3 = "Hello"
str3[0] = "A"   # TypeError: 'str' object does not support item assignment
```

## 跳脫字元(**Escape Sequences**)

在 Python 中，反斜線 `\` 作為跳脫字元，若字串中需要含特殊字元如 Tab、換行等，就需要使用反斜線 `\` 開頭，後面跟著特殊字元的指定字元，例如下表：

| 跳脫字元 | 說明 | 範例 |
| --- | --- | --- |
| `\'` | 單引號「'」 | str1 = "這是\\'單引號" <br> print(str1) |
| `\"` | 雙引號「"」 | str1 = "這是\\"雙引號" <br> print(str1) |
| `\\` | 反斜線 | str1 = "這是\\\反斜線" <br> print(str1) |
| `\n` | 換行 | str1 = "這是\\n換行" <br> print(str1) |
| `\r` | 游標移到列首 | str1 = "這是\\r游標移到列首" <br> print(str1) |
| `\t` | Tab 鍵 | str1 = "這是\\tTab" <br> print(str1) |
| `\b` | 倒退鍵(BackSpace) | str1 = "這是\\b倒退鍵(BackSpace)" <br> print(str1) |
| `\x` | 以十六進位表示字元 | str1 = "\\x48\\x69" <br> print(str1) |
| `\o` | 以八進位表示字元 | str1 = "\110\151" <br> print(str1) |

## 字串前加r

如果在字串前加`r`，可以防止**跳脫字元**被轉譯，相當於取消跳脫字元的功能。

```python
str1 = "Hello,\nPython" 
print(str1)
str2 = r"Hello,\nPython" 
print(str2)
```

## 字串運算子(Operator)

算術運算子不能對字串進行運算處理，但是，有一些特別的運算子是可以用在字串運算處理的，如下所列：

| 運算子 | 說明 | 範例 |
| --- | --- | --- |
| + | 加，將右邊字串附加到左邊字串 | a = 'hello,' <br> b = 'python' <br> print(a + b) <br> |
| * | 乘，連接同一字串的多個副本 | a = 'python,' <br> print(a * 3)  # python,python,python, |
| [] | 傳回指定索引的字串 | a = 'Python' <br> print(a[2])  # t |
| [:] | 傳回由`:`分隔的兩個索引所指定範圍內的字串 | a = 'Python' <br> print(a[2:4])  # th |
| in | 比較左邊字串是否存在於右邊字串，存在則回傳 `True`，否則 `False` | a = 'Python' <br> print('x' in a)  # False <br> print('y' in a)  # True <br> print('p' in a)  # False |
| not in | 比較左邊字串是否不存在於右邊字串，不存在則回傳 `True`，否則 `False` | a = 'Python' <br> print('x' not in a)  # True <br> print('y' not in a)  # False |


## 字串函數

下列是常用的字串函數。

| 函數 | 說明 | 範例 |
| --- | --- | --- |
| str() | 強制轉換數值為字串型別 | a = 3.0 <br> b = "輸入的數值是：" <br> print(b + str(a)) # 輸入的數值是：3.0| 
| lower() | 傳回原始字串的副本，其中所有字元都轉換為小寫 | a = "PYTHON" <br> print(a.lower()) # python |
| upper() | 傳回大寫的字串。符號和數字不受影響 | a = "python" <br> print(a.upper()) # PYTHON |
| count() | 計算指定子字串在目標字串中出現的次數。 | a = "banana" <br> result = a.count("a") <br> print(result)  # 3 |
| capitalize() | 傳回字串的副本，其中第一個字元大寫，其餘字母小寫。 | a = "python" <br> print(a.capitalize())  # Python |
| find() | 傳回給定字串中第一次出現的子字串的索引（區分大小寫）。如果未找到子字串，則傳回 -1。 | a = "hello world" <br> print(a.find("world"))  # 6 |
| index(x) | 傳回給定字串中第一次出現的子字串的索引。 | a = "hello world" <br> print(a.index("o"))  # 4 |
| replace() | 傳回字串的副本，其中所有出現的子字串都替換為另一個子字串。 | a = "hello world" <br> print(a.replace("world", "Python"))  # hello Python |
| split() | 從指定分隔符號拆分字串並傳回包含字串元素的清單物件。 | a = "1,2,a,b" <br> b = a.split(",")  # ['1', '2', 'a', 'b'] |
| join() | 傳回一個字串，它是字串與指定可迭代的字串元素作為參數的串聯。 | a = [1, 2, 'a', 'b'] <br> print("-".join(b))  # 1-2-a-b |
| strip() | 透過刪除前導字元和尾隨字元來傳回字串的副本。 | a = "  hello  " <br> print(a.strip())  # hello |
| lstrip() | 透過刪除指定為參數的前導字元來傳回字串的副本。 | print(a.lstrip()) |
| rstrip() | 透過刪除指定為參數的尾隨字元來傳回字串的副本。 | print(a.rstrip()) |

## 字元的編碼

無論是數字、英文字母或是中文字元，在 Python 裡都有一個獨一無二的數字去對應它們，這個數字就是它們的「字元碼」。
要查看字元的字元碼，可以利用 Python 的 `ord()` 函數。 `ord` 是 ordinal 的縮寫，也就是序數的意思，此函數回傳的是十進位的整數。

```python
print(ord("A"))   # 65
print(ord("a"))   # 97
print(ord("林"))  # 26519
```

### ASCII 編碼

* 範圍: 0–127（7位元）。
* 特點: 最早的字元編碼之一，僅適用於英文及一些控制字元（如換行、空格）。
* 用途: 英文和基本符號的表達，廣泛用於早期計算機。

  ASCII 是 使用 7 個位元定義文字，2 的 7 次方等於 128，相當於定義了 128 個字元。在這 128 字元中有 33 個字元是無法顯示的控制字元，其它則是可以顯示的字元，例如：+、-、=、0 到 9、大寫 A 到 Z、小寫 a 到 z 等，可以利用 Python 的 `chr()` 函數，`chr` 是 character 的縮寫，此函數會回傳 ASCII 或 Unicode 的字元。

  ```python
  print(chr(65))    # A
  print(chr(97))    # a
  print(chr(26519)) # 林
  ```

### Unicode 編碼

* 範圍: 覆蓋幾乎所有已知文字（目前支援超過 143,000 個字元）。
* 特點: 提供全球文字的統一編碼，字元編碼以數值（碼點）表示（例如 U+0041 表示字母 A）。
* 用途: 解決不同文字編碼不兼容的問題，成為現代計算的基礎。

  從上面的範例中，你可以看到字元的編碼，Python 的字元是採 「Unicode」來編碼的。在 Unicode 編碼的前 128 個碼是保留給 「ASCII」碼使用，所以原先存在於 ASCII 碼中的英文大小寫、標點符號、...等，是可以正常在 Unicode 碼中使用。

  早期每種語系的編碼各自獨立，相同的字元可能對應到不同語言的文字，也就產生亂碼的問題，為了讓全球語系統使用者可以彼此用電腦溝通，Unicode 把所有語言都統一到一套編碼裡。

  另外，可以使用前面介紹過的跳脫字元「\」來列印 ASCII 字元或 Unicode 字元。

  |---|---|
  |`\ooo`| 列印以 8 進位表示的 ASCII 字元，其中ooo表示 3 個數字，各別從 0 到 7 的數字。|
  |`\xoo`| 列印以 16 進位表示的 ASCII 字元，其中oo表示 2 個 16 進位的值，即 0 ~ 9 與 a ~ f 的值。|
  |`\uoooo`| 列印一個 Unicode 字元，其中 oooo 表示 4 個 16 進位的值。|

  ```python
  # 8 進位
  print(oct(65))  # A
  print("\101")   # A

  # 16 進位
  print(hex(65))  # A
  print("\x41")   # A

  # Unicode
  print(hex(26519))  # 林
  print("\u6797")    # 林
  ```

### UTF-8 編碼

* 範圍: 支援 Unicode 的所有字元。
* 特點: 可變長度編碼（1 到 4 個位元組），與 ASCII 向後兼容。
* 用途: 全球最常用的文字編碼方式，適用於網頁和跨平台應用。

  UTF-8 是針對 Unicode 字符集的可變長度編碼方式，這是網際網路目前所遵循的編碼方式，UTF-8 使用 1 ~ 4 個 byte 表示一個字符，這種編碼方式會根據不同字符變化編碼長度。

### ANSI 編碼

* 範圍: 0–255（8位元）。
* 特點: 是非標準的術語，通常指早期的 Windows 系統使用的區域性編碼，如 Windows-1252。
* 用途: 在西方語系（如英語、法語）中表達額外的符號和語言。

  ANSI(American National Standards Institute，美國國家標準協會) 是一種字符編碼方案，主要用於表示美國英語字符。但現在提到的 ANSI 編碼是指擴展的 ANSI 編碼，即 Windows 的 code page 編碼。對於不同的地區和語言，擴展的 ANSI 編碼使用不同的 code page，像繁體中文是 cp950（cp 分別是 code 程 page 的縮寫）。

### Big5 編碼

* 範圍: 兩個位元組（1 個字元佔 2 個位元組）。
* 特點: 台灣和香港常用的繁體中文編碼，涵蓋常用的中文字。
* 用途: 適用於繁體中文的早期系統和文件。

### cp950 編碼

* 範圍: 與 Big5 相似（雙位元組編碼）。
* 特點: 微軟實現的 Big5 延伸版本，包含更多的繁體中文字。
* 用途: Windows 系統中的繁體中文支援。

### GB2312 編碼

* 範圍: 不常見的編碼頁，專門設計用於某些特殊需求。
* 特點: ISO 8859-15 的別名，涵蓋西歐語言並加入歐元符號。
* 用途: 西歐語系的擴展支持。

### 65001

* 範圍: 等同於 UTF-8。
* 特點: Windows 系統內部對 UTF-8 的代碼頁表示。
* 用途: 在 Windows 中設置 UTF-8 作為預設編碼。


------

# 實作練習

## Lab 1：字串型別與轉換

**題目：**

請將以下變數內容結合成一個完整的句子，並將數字轉換為字串後輸出：

```python
name = "Owen"
age = 9
hobby = "coding"
```

輸出應為：
Owen is 9 years old and loves coding.

**解答：**

```python
name = "Owen"
age = 9
hobby = "coding"

result = name + " is " + str(age) + " years old and loves " + hobby + "."
print(result)
```

## Lab 2：處理跳脫字元與子字串提取

**題目：**

字串 text = "\*\*\*Python\nis\tawesome!\*\*\*"，請完成以下操作：

1. 移除所有的跳脫字元，將其轉換為 "\*\*\*Python is awesome!\*\*\*"。
2. 不要取`***`，使用字串索引取得，將其轉換為 "Python is awesome!"。。
3. 提取單字 "awesome" 並輸出。

**解答：**

```python
text = "***Python\nis\tawesome!***"
print(text)
# 移除跳脫字元
clean_nt = text.replace("\n", " ").replace("\t", " ")
print(clean_nt)  # Python is awesome!

# 前後3碼不要取
clean_text = clean_nt[3:-3]
print(clean_text)

# 提取 "awesome"
wordlist = clean_text.split()
print(wordlist)
word = wordlist[-1]
print(word)  # awesome
```

## Lab 3：字串運算與方法應用

**題目：**

1. 給定字串 s = " Learn Python, Python is fun! "，去除前後空白並將所有文字轉為小寫。
2. 計算字串中 Python 出現的次數。
3. 將 Python 替換為 coding，並輸出結果。

**解答：**

```python
s = "  Learn Python, Python is fun!  "
# 去除前後空白並轉小寫
s_cleaned = s.strip().lower()
print(s_cleaned)  # learn python, python is fun!

# 計算 "Python" 的出現次數（不分大小寫）
count = s_cleaned.count("python")
print(count)  # 2

# 替換 "Python" 為 "coding"
s_replaced = s_cleaned.replace("python", "coding")
print(s_replaced)  # learn coding, coding is fun!

```

----- 

# 隨堂測驗

<iframe src="https://docs.google.com/forms/d/e/1FAIpQLScx68wYDh4Buo8ozKu6E64KWasBhfbSITyYQpxwHbYOMDu60g/viewform?embedded=true" width="640" height="2012" frameborder="0" marginheight="0" marginwidth="0">載入中…</iframe>
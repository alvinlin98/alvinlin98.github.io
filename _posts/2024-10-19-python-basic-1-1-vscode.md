---
title:  "VSCocde安裝與介紹"
permalink: /python_basic/1-1-vscode/
excerpt: "VS Code 是一款非常適合 Python 開發的編輯器，它兼具了強大的功能和良好的使用者體驗。"
header:
  teaser: assets/images/python_basic/1-1-vs-code.png
search: false
categories: 
  - Python零基礎入門班
tags:
  - Python
  - VSCode
  - 安裝
sidebar:
  nav: "python_basic"
author_profile: false
last_modified_at: 2024-10-19T21:00-00:00
toc: true
---

<figure class="align-center">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/images/python_basic/1-1-vs-code.png" alt="">
</figure> 

# VS Code 安裝與介紹

## Python 編輯器

我們常用的 Python 編輯器有很多種，簡述如下：

- Jupyter Notebook
    - 互動式筆記本，適合數據分析和機器學習。
    - 優點：可以直接在網頁中運行 Python 程式碼、可視化結果。
    - 缺點：不適合大型專案開發。
    
- **PyCharm**
    - 專為 Python 開發打造的 IDE，功能齊全。
    - 優點：專為 Python 設計、智慧化程式碼補全、強大的除錯功能。
    - 缺點：資源消耗較大、學習曲線較陡。
    
- **Visual Studio Code (VS Code)**
    - 微軟開發的免費、開源、跨平台編輯器，功能強大。
    - 優點：外掛生態系豐富、支援多種程式語言、可高度客製化、擁有強大的除錯功能。
    - 缺點：介面較為複雜，初學者可能需要花一些時間適應。

- **Colab (Google Colaboratory)**
    - 基於雲端的 Jupyter Notebook 環境，可以直接在瀏覽器中編寫、執行 Python 程式碼。
    - 免費提供 GPU 和 TPU，適合機器學習、深度學習等計算密集型的任務。
    - 容易分享和協作，適合團隊開發。

另外還有 Spyder、IDLE、Sublime Text、Atom、… 等等，在這就不多做說明，因為 `VS Code` 是我們這裡主要使用的編輯器。

## 選擇 VS Code 的理由

- **功能強大：**
    - **智慧程式碼補全：** 能夠根據上下文自動補全程式碼，提高開發效率。
    - **強大除錯功能：** 方便地設置斷點、檢視變數，快速定位錯誤。
    - **Git 版本控制整合：** 直接在編輯器中進行 Git 操作。
    - **豐富的外掛生態系：** 有海量的外掛可供選擇，擴展 VS Code 的功能。
- **客製化程度高：**
    - 可以根據個人喜好設定主題、鍵盤快捷鍵等。
    - 可以安裝各種外掛來擴展功能，打造專屬的開發環境。
- **跨平台：**
    - 支援 Windows、macOS 和 Linux，方便在不同系統上開發。
- **輕量且快速：**
    - 相較於其他 IDE，VS Code 起動速度快，占用資源少。
- **免費且開源：**
    - 可以自由地使用和修改。

總結來說， VS Code 是一款非常適合 Python 開發的編輯器，它兼具了強大的功能和良好的使用者體驗。無論你是初學者還是專業開發者，都可以從中受益。

## 安裝 VS Code

- 何安裝 VS Code？
    1. **前往 VS Code 官網：** [https://code.visualstudio.com/](https://code.visualstudio.com/)
    2. **下載安裝檔：** 依照您的作業系統（Windows、macOS 或 Linux）選擇對應的安裝檔並下載。
    3. **執行安裝程式：** 雙擊下載的安裝檔，按照提示進行安裝。
        - **建議：** 在安裝過程中，建議勾選「新增至 PATH」，這樣就可以在終端機中直接輸入 `code` 來啟動 VS Code。
- 安裝 Python 擴充功能
    1. **開啟 VS Code：** 安裝完成後，開啟 VS Code。
    2. **開啟擴充功能面板：** 點擊左側活動列上的擴充功能圖示（或使用快捷鍵 Ctrl+Shift+X），開啟擴充功能面板。
    3. **搜尋 Python：** 在搜尋框中輸入「Python」，找到並安裝「Python」擴充功能。
- 設定 Python 解譯器
    1. **開啟命令面板：** 點擊「檢視」->「命令面板」（或使用快捷鍵 Ctrl+Shift+P）。
    2. **輸入「Python: Select Interpreter」：** 在命令面板中輸入「Python: Select Interpreter」並選擇。
    3. **選擇 Python 解譯器：** 從列表中選擇你電腦上安裝的 Python 解譯器。
- 開始使用 VS Code 編寫 Python 程式
    1. **建立新檔案：** 點擊「檔案」->「新建檔案」，或使用快捷鍵 Ctrl+N。
    2. **儲存檔案：** 將檔案儲存為 `.py` 擴展名，例如 `hello.py`。
    3. **編寫程式碼：** 在檔案中輸入 Python 程式碼。
        
        ```bash
        print("Hello, Python")
        ```
        
    4. **執行程式：**
        - **在終端機中執行：** 在 VS Code 的終端機中，切換到檔案所在目錄，然後輸入 `python hello.py` 執行。
        - **使用 Code Runner 擴充功能：** 安裝 Code Runner 擴充功能後，可以在編輯器中右鍵點擊，選擇「Run Code」來執行程式。

## 常用快捷鍵

- **開啟命令面板：** Ctrl+Shift+P
- **尋找檔案：** Ctrl+P
- **跳轉到定義：** F12

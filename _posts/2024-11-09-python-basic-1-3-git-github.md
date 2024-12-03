---
title:  "Git與GitHub的使用"
permalink: /python_basic/1-3-git-github/
excerpt: "這篇讓我們清楚知道如何在 VS Code 中使用 Git 與 GitHub 來做版本控管。"
header:
  teaser: assets/images/python_basic/1-3-git-github.png
search: false
categories: 
  - Python零基礎入門班
tags:
  - Python
  - Git
  - GitHub
  - VSCode
sidebar:
  nav: "python_basic"
author_profile: false
last_modified_at: 2024-11-02T21:00-00:00
toc: true
---

<figure class="align-center">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/images/python_basic/1-3-git-github.png" alt="">
</figure> 

# Git基本操作

- 開啟 Git Bash：開始 > Git > Git Bash。

## 開啟終端機（Terminal）

## 基本工作流程

- 查看 Git 版本
    
    ```bash
    > git --version
    ```
    
- 設定 Git 使用者
    
    ```bash
    > git config --global user.name "你的使用者名稱"
    ```
    
- 設定使用者信箱
    
    ```bash
    > git config --global user.email "你的電子信箱"
    ```
    
    設定使用者與信箱，才能知道誰建立與變更。
    
- 切換至本機存放原始碼的資料夾
    
    ```bash
    > cd "C:\Source Code\Python零基礎入門班"
    ```
    
    新增 `README.md` ，為這個資料夾說明是做什麼，例如
    
    ```bash
    # Python 零基礎入門篇
    此書分成三大部分
    1. ch01 ~ ch04 探討 Python 基本語法與資料型別。
    1. ch05 ~ ch08 探討程式流程的控制、函數、物件導向技術及檔案與例外處理等。
    1. ch09 ~ ch14 介紹 Python 常用的套件。
    ```
    
- 初始化本地儲存庫(repository)
    
    ```bash
    > git init
    ```
    
    這指令在在該目錄下建立 `.git` 的隱藏目錄，這樣該資料夾就具有 Git 的版本控制的功能了，如果刪除此資料夾，則版本記錄也都會消失喔。
    
- 新增檔案
    - `git add [檔案名稱] [檔案名稱]...`：將檔案添加到暫存區，也可以同時加入多個檔案，只要檔案與檔案之間用空隔分隔，或是萬用字元 「*」，例如 `*.md`。
    - `git add .`：將所有修改過的檔案添加到暫存區。
    
    例如將上述的 `README.md` 加到暫存區。
    
    ```bash
    > git add README.md
    ```
    
    在 VS Code 可以看到該文件的狀態會從 U 變成 A。
    
- **查看狀態**
    - `git status`：查看目前的工作狀態，例如哪些檔案被修改、哪些檔案已暫存。
- **提交變更**
    - `git commit -m "提交訊息"`：將暫存區的變更提交到本地倉庫，這個提交訊息最好能簡述這次的修改，方便我們日後追查問題時可以知道本次提交的目的與內容變化。
    
    ```bash
    > git commit -m "新增 README 說明"
    ```
    
- 修改檔案
    
    重複新增檔案的程序，只是被修改的檔案狀態變成 U。
    
- **查看歷史**
    - `git log`：查看提交歷史。
    
    如果歷史記錄很長且又想離開，則按下 `q` 鍵即可離開。
    
    例如剛才前面的操作
    
    ```bash
    C:\Source Code\Python零基礎入門班>git log
    commit 3e9ec8d650bbab89e55dc310de67638399eb6550 (HEAD -> master)
    Author: Super3Home <alvinhome98@gmail.com>
    Date:   Thu Oct 31 20:50:55 2024 +0800
    
        修改ch09~ch14的說明
    
    commit 662752f53dbdaf76e93010a243b8b4d6c2784612
    Author: Super3Home <alvinhome98@gmail.com>
    Date:   Thu Oct 31 20:42:06 2024 +0800
    
        新增 README 說明
    ```
    
- 其它常用命令
    
    
    | 命令 | 說明 | 範例 |
    | --- | --- | --- |
    | `git diff` | 比較檔案差異 `git diff` [比較工作區與暫存區] | > git diff 662752f |
    | `git reset`  | 撤銷修改，有三個模式：soft、mixed、hard，分別對應不同的撤銷程度。 | 還原到指定的還原點，其結果是不可逆的 <br> > git reset —hard 662752f |

## Git 的 .gitignore 檔案簡介

`.gitignore` 是一個文本文件，用來告訴 Git 哪些檔案或目錄不需要添加到版本控制中。這意味著，當你執行 `git add .` 時，這些被忽略的文件將不會被添加到暫存區。

- **為什麼需要 `.gitignore`？**
    - **保持倉庫整潔:** 避免將無關的檔案（例如編譯產生的暫存文件、編輯器配置文件等）提交到版本庫中，保持倉庫的乾淨和高效。
    - **提高性能:** 減少提交的檔案數量，可以提高 Git 的性能。
    - **避免敏感資訊洩露:** 可以用來忽略包含敏感資訊的檔案，如密碼、API 金鑰等。

- **`.gitignore` 的寫法**
    - **行首不能有空格：**每行表示一個忽略模式。
    - **# 符號表示註釋：**可以用來添加註釋，解釋忽略規則。
    - **通配符：**
        - `*`：匹配任意多個字符。
        - `?`：匹配一個任意字符。
        - `[abc]`：匹配方括號中的任意一個字符。
        - `[^abc]`：匹配不在方括號中的任意一個字符。
        - `**`：匹配任意層次的目錄。
- 常見的 .gitignore 範例
    
    ```bash
    # 忽略所有 .png 圖檔
    *.png
    
    # 忽略目錄 build 和 dist
    build/
    dist/
    
    # 忽略所有以 .tmp 結尾的文件
    *.tmp
    ```
    

# GitHub 基本操作

在前面的章節已經知道如何註冊一個 GitHub 帳號了，如果不清楚可以回到 [GitHub 會員註冊](https://www.notion.so/GitHub-12b8bbf5d43880618107e7b870964d51?pvs=21) ，並請你登入 GitHub。

## 建立遠端儲存庫(Repository)

- **建立新 Repository**：登入後，點擊右上角的「+」號，然後選擇「New repository」。
- **填寫 Repository 資訊：**為你的 Repository 命名。名稱要簡潔、有意義，且最好能反映專案的內容。
- **Description：** (選填) 為 Repository 寫一個簡短的描述，說明這個專案是做什麼的。
- **Public or private：**
    - **Public：** 任何人都可以查看和複製你的 Repository。
    - **Private：** 只有你有權限查看和修改。
- **Initialize this repository with a README：**勾選這個選項會自動在 Repository 中建立一個 `README.md` 檔案，用來簡單介紹這個專案。在前面的教學已經有建立了 `README.md` ，因此這裡就選擇不用勾選。
- **Add .gitignore**：勾選這個選項會自動生成一個 `.gitignore` 檔案，用來指定哪些檔案不需要被 Git 追蹤。在前面的教學已經有建立了 `.gitignore` ，因此這裡就選擇 None。
- **Choose a license**：選擇一個開源授權，明確說明其他人如何使用你的程式碼。
- **建立 Repository：**完成上述步驟後，點擊「Create repository」按鈕，你的 Repository 就建立完成了。

## 推送到遠端儲存庫

建立完成後，在頁面的底下有提供指令可以將我們本地的檔案推送到遠端儲存庫，因為我們已經在本地初始化過儲存庫，所以我們只要執行畫面最底下的三行指令，就可以推送到遠端儲存庫。

- 連結儲存庫
    - `git remote add [遠端名稱] [遠端儲存庫連結]`：將本地與遠端儲存庫進行連結。
    
    ```bash
    > git remote add origin https://github.com/Super3Home/Python-basic.git
    ```
    
- 分支管理
    - `git branch -M [新分支名稱]`：將本地初始建立的分支名稱從 `master` 改為 `main` 。
        - `-M`：重新命名。
    
    ```bash
    > git branch -M main
    ```
    
- 推送修改
    - `git push -u [遠端名稱] [本地分支名稱]`：將本地分支推送到遠端儲存庫。
        - `-u`：建立關連。
    
    例如：將 main 分支推送到 origin 遠端倉庫
    
    ```bash
    > git push -u origin main
    ```
    
    執行完成後，再回到 GitHub 的儲存庫，就可以看到上傳的檔案，同時在 Commits 頁面也可以看到提交的版本記錄。
    

# Git 其它常用指令

- `git clone [遠端儲存庫連結]` ：複製一個遠端儲存庫到本地。
    
    ```bash
    > git clone https://github.com/Super3Home/Python-basic.git
    ```
    
- `git branch` ：列出所有本地分支。
- `git branch [分支名稱]` ：創建一個新的本地分支。
- `git branch -D [分支名稱]` ：刪除指定的分支，無法刪除本身所在的分支，必須得切換到其他分支，才能執行。
    
    例如：目前在 `main` 分支，想要刪除 `hotfixes` 分支。
    
    ```bash
    ../Python零基礎入門班(main) > git branck -d hotfixes
    ```
    
- `git checkout [分支名稱]` ：切換到指定的分支。
    
    ```bash
    > git checkout main
    ```
    
- `git checkout -b [分支名稱]` ：創建一個新的本地分支與同時切換分支。
    
    例如：建立分支名為 `hotfixes` 並同時切換到此分支。
    
    ```bash
    > git checkout -b hotfixes
    ```
    
- `git pull [遠端名稱] [遠端分支名稱]` ：從遠端儲存庫拉取指定分支的最新修改回來。
    
    例如：從 origin 遠端倉庫拉取 main 分支。
    
    ```bash
    > git pull origin main
    ```
    

# VS Code 中使用 GitHub (2)

當了解上述的 Git 介紹後，已經知道 Git 是如何做版本管理，接下來參考這支影片的介紹，讓我們清楚知道如何在 VS Code 中使用 Git 與 GitHub 來做版本控管。

{% include video id="FKXRiAiQFiY" provider="youtube" %}


# 作業系統其它常用指令

| Windows | Mac / Linux | 說明 |
| --- | --- | --- |
| cd | cd | 變更當前目錄 |
| cd | pwd | 取得當前目錄 |
| dir | ls | 顯示當前目錄裡的清單 |
| mkdir | mkdir | 新增資料夾 |
| 無 | touch | 建立新檔 |
| copy | cp | 複製檔案 |
| move | mv | 移動檔案 |
| del | rm | 刪除檔案 |
| cls | clear | 清除畫面 |
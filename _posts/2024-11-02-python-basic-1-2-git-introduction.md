---
title:  "Git安裝與註冊GitHub"
permalink: /python_basic/1-2-git-introduction/
excerpt: "Git 是一款分散式版本控制系統，廣泛用於軟體開發中。它能有效地追蹤檔案的修改歷史，並允許多人協同工作。"
header:
  teaser: assets/images/python_basic/1-2-git-introduction.png
search: false
categories: 
  - Python零基礎入門班
tags:
  - Python
  - Git
  - GitHub
  - 安裝
sidebar:
  nav: "python_basic"
author_profile: false
last_modified_at: 2024-11-02T21:00-00:00
toc: true
---

<figure class="align-center">
  <img src="{{ site.url }}{{ site.baseurl }}/assets/images/python_basic/1-2-git-introduction.png" alt="">
</figure> 

# Git安裝與操作

## 什麼是 Git？

Git 是一款分散式版本控制系統，廣泛用於軟體開發中。它能有效地追蹤檔案的修改歷史，並允許多人協同工作。

## 為何要安裝 Git？

- **版本控制：** 追蹤程式碼的變更，方便回溯或比較不同版本。
- **團隊協作：** 多人共同開發專案，確保程式碼的一致性。
- **備份：** 將程式碼儲存到遠端伺服器，避免資料遺失。

## Git 安裝

1. **下載安裝程式：** 從 Git 官方網站 ([https://git-scm.com/download/win](https://git-scm.com/downloads/win)) 下載適合你系統的安裝程式，我們的作業系統是 Windows 64位元，所以選擇 [**64-bit Git for Windows Setup**](https://github.com/git-for-windows/git/releases/download/v2.47.0.windows.1/Git-2.47.0-64-bit.exe)。
2. **執行安裝程式：**
    - **使用預設設定：** 大部分情況下，使用預設設定即可。
    - **調整設定：** 若有特殊需求，可調整以下選項：
        - **開始選單程式名稱：** 決定 Git 相關工具在開始選單中的位置。
        - **桌面捷徑：** 是否在桌面上建立 Git Bash 的捷徑。
        - **關聯 .git 和 .ignore 檔案：** 是否將 .git 和 .ignore 檔案與 Git 關聯。
        - **調整 PATH 環境變數：** 允許你在命令提示字元中直接輸入 git 命令。
3. **完成安裝：** 按照安裝程式的提示完成安裝，**安裝完即可在程式集看到 Git**

<figure>
    <img src="{{ '/assets/images/python_basic/1-2-1-gitbash.png' | relative_url }}" alt="gitbash">
</figure>

# VS Code 中使用 Git

Visual Studio Code (VS Code) 是一款功能強大的程式碼編輯器，內建了對 Git 的支援。這意味著你可以在 VS Code 中直接進行版本控制，而不需要切換到終端機。這大大提高了開發效率。

**前提：**

- **已安裝 Git：** 請確保你的電腦上已經安裝了 Git。如果你還沒有安裝，請參考上述[](https://www.notion.so/12b8bbf5d438806cbf15e292f2c65a27?pvs=21) 的詳細步驟。
- **已安裝 VS Code：** 確保你已經安裝了 VS Code。如果你還沒有安裝，請參考[1. VSCode 安裝與介紹](https://www.notion.so/1-VSCode-30ffccf29d004cccb61094fbc3b0a95f?pvs=21) 的詳細步驟。

VS Code 已整合原始檔控制管理 (SCM)，並內建 [Git](https://git.dev.org.tw/) 支援。許多其他原始檔控制提供者可透過 VS Code Marketplace 上的 [擴充功能](https://vscode.dev.org.tw/docs/editor/extension-marketplace) 取得。

# GitHub 會員註冊

**GitHub** 是全球最大的程式碼託管平台，也是程式開發者們分享、合作和管理專案的絕佳工具。以下將詳細說明如何註冊 GitHub 帳號：

## 前往 GitHub 官網

- 在瀏覽器網址列輸入 [https://github.com/](https://github.com/) 並按下 Enter 鍵。

## 填寫註冊資訊

- 點選 Sign Up
- **電子郵件地址：** 輸入你的有效電子郵件地址，GitHub 將會發送驗證郵件。
- **使用者名稱：** 選擇一個獨特的使用者名稱，這將是你在 GitHub 上的識別標籤。
- **密碼：** 設定一個強健的密碼，確保帳戶安全。
- **驗證碼：** 輸入畫面上的驗證碼。
- **其他選項：** 你可以選擇是否公開你的電子郵件地址，以及是否接受行銷郵件。

## 驗證電子郵件

- 檢查你的電子郵件收件匣，找到 GitHub 發送的驗證郵件。
- 點擊郵件中的驗證連結，完成帳戶驗證。

## 完成註冊

- 驗證完成後，你就可以開始使用你的 GitHub 帳號了。
- 登入 GitHub，選擇 Free 方案
<figure>
    <img src="{{ '/assets/images/python_basic/1-2-2-free.png' | relative_url }}" alt="免費方案">
</figure>

註冊過程中可能遇到的問題與解決方法：

- **使用者名稱已被使用：** 請嘗試其他使用者名稱。
- **驗證郵件未收到：** 檢查垃圾郵件夾，或重新發送驗證郵件。
- **忘記密碼：** 點擊登入頁面的「忘記密碼」連結，按照提示重置密碼。

祝你成功註冊 GitHub，開始你的程式開發之旅！

# VS Code 中使用 GitHub(1)

**VS Code** 和 **GitHub** 的結合，為程式開發者提供了一個強大而便捷的開發環境。這讓你可以直接在 VS Code 中管理你的 GitHub 倉庫，從建立新專案到參與開源專案，都變得更加方便。

## **前提條件**

- **安裝 VS Code：** 確保你已經在電腦上安裝了 VS Code。
- **安裝 Git：** VS Code 內建了對 Git 的支援，但你仍需要在系統上安裝 Git。
- **建立 GitHub 帳戶：** 如果還沒有 GitHub 帳戶，請先註冊一個。

## **連接 GitHub 帳戶**

- **開啟 VS Code：** 啟動 VS Code。
- **安裝 GitHub Pull Requests and Issues 擴充功能：** 在擴充功能面板中搜尋並安裝這個擴充功能，它能提供更豐富的 GitHub 功能。
- **授權：** 第一次使用時，VS Code 會提示你授權連接你的 GitHub 帳戶。按照提示在瀏覽器中使用 GitHub 進行驗證，然後返回 VS Code。

## **開始使用**

請參考[Git與GitHub的使用](/python_basic/1-3-git-github/) 此章節的說明。
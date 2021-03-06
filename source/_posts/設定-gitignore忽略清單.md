---
title: 設定.gitignore忽略清單
date: 2020-08-12 13:47:21
tags: git
categories: git
---

#### 在 Git 裡面，是透過 .gitignore 檔案來進行定義「忽略清單」，主要的目的是排除一些不需要加入版控的檔案，列在裡面的檔名或路徑 (可包含萬用字元)

#### 在軟件項目中，.gitignore 通常包含在構建過程中或在運行時生成的文件和/或目錄的列表 .gitignore 文件中的條目可能包含指向以下內容的名稱或路徑：

#### 1. 臨時資源，例如緩存，日誌文件，編譯代碼等
#### 2. 不應與其他開發人員共享的本地配置文件
#### 3. 包含機密信息的文件，例如登錄密碼，密鑰和憑據

<!-- more -->

#### 建立倉庫的時候可以在下方找到 Add .gitignore 新增或是自行創建

![ ](images/1.png)
![ ](images/2.png)
![ ](images/3.png)

#### .gitignore 範例

![ ](images/4.png)
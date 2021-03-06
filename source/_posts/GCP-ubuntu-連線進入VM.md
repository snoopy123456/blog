---
title: GCP-ubuntu-連線進入VM
date: 2018-06-21 14:47:21
tags: GCP
categories: GCP
---

### 連線進入 VM ( linux )

### 總共有 4 種方法可以進入 VM 本篇文章將依序作介紹

<!-- more -->

### SSH 連線會需要用到 tcp:22，一般專案開好會有預設防火牆 tcp:22 但是 VM 跟 IP 全開 ( 建好 VM 可以直接連就是因為這樣 )，需要再做設定防火牆文章可以到這裡看 [文章傳送門](https://snoopy30485.github.io/2018/06/20/GCP-%E9%98%B2%E7%81%AB%E7%89%86/)

### 一、 使用 GCP 開啟新視窗連線

### 創建好 VM 後直接點擊右邊 SSH 或是 ▼ 在瀏覽器視窗中開啟

![ ](images/1.png)

### 點擊完後會另外再開一個視窗，這時候 VM 連進去會幫你加金鑰

![ ](images/2.png)
![ ](images/3.png)

### 可以在 Compute Engine → 中繼資料 → SSH 金鑰，查看金鑰 

![ ](images/4.png)
![ ](images/5.png)

***

### 二、 使用 Cloud Shell 連線

### 打開 Cloud Shell

![ ](images/6.2.png)

### 使用指令連線進入

```
gcloud compute ssh (VM名稱) --zone (區域)
```

### ex：gcloud compute ssh test \--zone asia-east1-b

### 輸入 y 繼續

![ ](images/7.png)

### 生成公鑰/私鑰，會輸入密碼點 2下 Enter 使用空密碼 ( 第一次會有這些步驟，下次在下指令就不會有了 )

![ ](images/8.png)

### 原本是帳號加專案 ID

![ ](images/9.1.png)

### 看到變成帳號加 VM 名稱就是進去了，接下來就可以直接操作了

![ ](images/10.png)

***

### 三、 使用 Cloud SDK 連線

### Cloud SDK：Cloud SDK 是一套 Cloud Platform 工具，其中包含 gcloud、gsutil 和 bq，可讓您透過指令列存取 Google Compute Engine、Google Cloud Storage、Google BigQuery，以及其他產品和服務。您可以利用這些工具進行互動操作，也可以運用在您的自動化指令碼中。 ( Cloud Shell 使用的指令就是 SDK 的指令 )

### 安裝 SDK，下載：https://cloud.google.com/sdk/ 

### 啟動 SDK

![ ](images/11.1.png)

### 如果帳號不對要記得切換帳號

```
gcloud auth login 帳號
```

![ ](images/12.png)

### 切換帳號它會開個網頁讓你選目前想用的帳號

![ ](images/14.png)
![ ](images/15.png)

### 出現此畫面就是成功了，第一次會需要網頁點帳號再來就不用了

![ ](images/32.png)

### 可以下指令檢查一下，目前使用的帳號前面會有 \*

```
gcloud auth list
```

![ ](images/13.png)

### 接下來和 Cloud Shell 一樣步驟，輸入完指令會再開一個終端機就是成功了 ( y/n 不用輸入到這邊後就會跳出一個新視窗連進 VM )

![ ](images/17.1.png)
![ ](images/16.png)

***

### 四、 使用其他程式連線，本文章使用 Xshell 5 可以使用自己熟悉程式

### 首先創建金鑰

![ ](images/18.png)
![ ](images/19.1.png)

### 選擇 RSA 長度選 2048 目前 1024 已經不太安全

![ ](images/20.png)
![ ](images/21.png)

### 設定密碼和名稱

![ ](images/22.1.png)

### 複製金鑰或儲存

![ ](images/23.1.png)

### 到 GCP Compute Engine → 中繼資料 → SSH 金鑰，添加金鑰

![ ](images/4.png)
![ ](images/5.png)

### 點編輯把剛剛複製的金鑰貼上 ( 要按照格式不然會出現錯誤，空格輸入要命的名稱，輸入名稱將會在使用 Xshell 5 連線時用到 )

![ ](images/24.1.png)

### 接下來到 VPC 網路 → 防火牆規則

![ ](images/25.png)

### SSH 是使用 22 port，可以更改預設也可以自己建立一個

![ ](images/26.png)

### 點選防火牆名稱進入後點編輯，加入自己的 ip ( 外網 )，儲存

![ ](images/28.png)

### 回到 Xshell 5 點選新增工作

![ ](images/29.png)

### 連線：輸入名稱 ( 隨意 ) 和 ip

![ ](images/30.png)

### 使用者驗證：方法選 Public Key 使用者名稱輸入中繼資料輸入的名稱，選擇剛剛建立的金鑰使用者和輸入密碼

![ ](images/31.2.png)

### 第一次登入會出現 SSH 安全性警告，點選接受及存檔

![ ](images/33.png)

### 如果上面使用者驗證沒輸入到使用者名稱的話會問使用者名稱

![ ](images/34.1.png)

### 恭喜完成連線！

![ ](images/35.png)
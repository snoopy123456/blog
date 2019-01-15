---
title: Ubuntu的各種解壓縮指令
date: 2018-07-01 08:43:53
tags:
---

#### Ubuntu的各種解壓縮指令，作者自己做筆記用

### .tar

#### 打包：tar cvf FileName.tar DirName

#### 解包： tar xvf FileName.tar

***

### .gz

#### 壓縮：gzip FileName

#### 解壓1：gunzip FileName.gz

#### 解壓2：gzip -d FileName.gz

***

### .tar.gz

#### 壓縮：tar zcvf FileName.tar.gz DirName

#### 解壓：tar zxvf FileName.tar.gz

***

### .bz2

#### 壓縮： bzip2 -z FileName

#### 解壓1：bzip2 -d FileName.bz2

#### 解壓2：bunzip2 FileName.bz2

***

### .tar.bz2

#### 壓縮：tar jcvf FileName.tar.bz2 DirName

#### 解壓：tar jxvf FileName.tar.bz2

***

### .tgz

#### 壓縮：unkown

#### 解壓：tar zxvf FileName.tgz

***

### .tar.tgz

#### 壓縮：tar zcvf FileName.tar.tgz FileName

#### 解壓：tar zxvf FileName.tar.tgz

***

### .zip

#### 壓縮：zip FileName.zip DirName

#### 解壓：unzip FileName.zip

***

### .rar

#### 壓縮：rar a FileName.rar

#### 解壓：rar e FileName.rar

***

### .lha

#### 壓縮：lha -a FileName.lha FileName

#### 解壓：lha -e FileName.lha
---
layout:     post
title:      "SVN 基本指令懶人包"
subtitle:   "Useful SVN conmands"
date:       2017-08-03 12:00:00
author:     "Scoly"
tags:
    - SVN
---

## 碎碎念

沒想到胖胖筆記的第一篇文章居然是 SVN 指令，原本想先發個萌新建網頁的速成攻略呢...

因為寫網頁攻略預估要兩到三個小時，但卻一直沒有一個完整的空閒時間可以讓我寫。而工作上剛好要用到 SVN ，但是最近都在 Github 上打滾， 
SVN 指令什麼的早就忘光光了，每次都還要去查真的是很煩人呢，於是就決定自己寫一篇淺顯易懂的指令大全做記錄用。

不過這年頭應該也沒什麼新人在用 SVN 了，通常都是接手前人的工作時會用到（像是小的我），現在人都在用 Github 了啦方便多了老闆你聽到了沒！


## 一句話介紹 SVN


SVN 是 subversion 的簡寫，是一個開放原始碼的版本控制系統，在 Github 還沒出來之前大家都是用這個在做版本控制的。

-> 想更了解 SVN 請點[我](https://zh.wikipedia.org/wiki/Subversion)


## 正文


> 使用 Ubuntu 14.04

如果你的電腦還沒有 SVN 的話，`sudo apt-get install subversion`。

* Checkout

  * `$ svn co http://SVN_PATH/svn_project`
  
* Update

  * `$ svn up`

* Add

  * `$ svn add file or dir`
  
* Commit (Commit 完就結束了不用 push!)

  * `$ svn ci -m "message"`

* List (可以不用 checkout 回來就可以先查看)

  * `$ svn ls http://SVN_PATH/svn_project`
  
* Status

  * `$ svn st`
  * ?: 此檔案不存在 SVN 裡面
  * A: 此次新增的檔案
  * C: 此檔案已經有人改過, 合併不成功, 需要人工介入
  * D: 此次移除的檔案
  * M: 此檔案有修改過
  * U: 此檔案有被更新過

* MV

  * `$ svn mv filename new_filename`

* Import（將本地端的 project 資料夾 import 進 SVN 裡面）

  * `$ svn import project http://SVN_PATH/svn_project`
  
* Info

  * `$ svn info`
  
* Diff

  * `$ svn diff`
  * `$ svn diff -r xxxx:oooo`

* Revert (未 commit 前才能用!)

  * `$ svn revert file or dir`
  
我個人覺得這個指令超雞肋的！因為通常 add 完就會直接接 commit 了啊這根本是直覺反應了，感覺用到這個指令的機率很低。

那 commit 後把錯的資料傳上去怎麼辦？別擔心，這就是體現 SVN 價值的時候了。

* Merge

  * `$ svn merge -r 1234:1233 . .`

這樣就可以從版本1234回復成版本1233。

還有一種情況是，你現在的 working directory 或是 SVN 已經被你搞壞了， SVN 上的紀錄和你實際 working directory 的記錄已經完全不一樣，一堆 conflict 看到快吐血。（別笑，小的就發生過好幾次類似的經驗）

這時候建議直接在別處 checkout 你 SVN 上的東西， merge 回你要的版本後再進行修改。個人經驗是比解 conflict 快很多。（正確來說應該是，從來沒有成功把 conflict 都解完過就放棄轉而使用這個方法了...）

還有一些我自己沒用過的指令我就沒有列出來了。希望大家能愉快的使用萬惡的 SVN  ^^


  
  


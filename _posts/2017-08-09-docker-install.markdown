---
layout:     post
title:      "超高速安裝和使用 Docker 教程"
subtitle:   "Install Docker instantly"
date:       2017-08-09 12:00:00
author:     "Scoly"
tags:
    - Docker
---

## 碎碎念

近日在將之前做的專案搬遷到另一台主機上，但是因為那個專案需要裝最和我有仇的 OpenCV 和 FFmpeg (裝任何一個每次都要花掉我一天以上的時間)，實在是讓小女子我頭痛不已啊。
毫不意外地浪費了兩三天的時間之後，在 Hui-Po 的建議下，趁我還有力氣的時候在 Docker 上在重裝一次，之後如果老闆腦袋抽筋叫我再搬到另一台主機上時就不需要重裝啦（撒花


## 一句話了解 Docker

Docker 專案的目標是實作輕量級的作業系統虛擬化解決方案，可以理解為 VM 的輕量版。

-> 想更了解 Docker 請點[我](https://philipzheng.gitbooks.io/docker_practice/content/introduction/what.html)


## 正文

> 使用 Ubuntu 14.04


### 安裝

1. `$ uname-r` 檢查 Linux kernel 的版本 (需大於 3.10)

2. `$ which curl` 檢查有無安裝 curl (無 curl 請執行 `$ sudo apt-get install curl`)

3. `$ sudo apt-get update` 更新一下

4. `$ curl -fsSL https://get.docker.com/ | sh` 下載和安裝 Docker

5. `$ sudo usermod -aG docker USERNAME` 添加以後會使用的 user，記得要登出之後才會生效

6. `$ docker -v` 確認安裝成功


### 使用

1. `$ docker pull IMAGEFILE` 下載需要的映像檔，例如 `$ docker pull ubuntu:14.04`

2. `$ docker images` 顯示所有的映像檔

3. `$ docker run -i -t IMAGEFILE` 在映像欓上創建一個新的容器，例如 `$ docker run -i -t ubuntu:14.04`

4. `$ exit` 離開容器

5. `$ docker ps` 可以看到創建的所有容器

6. `$ docker exec -ti CONTAINER_NAME bash` 再次進入所創建的容器


以上就是超高速安裝和使用 Docker 的教程喔，等我之後和他深入培養感情後再來發一篇常用指令大全～







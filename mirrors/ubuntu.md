# Ubuntu 源使用幫助

## 地址

https://mirror.xtom.com.hk/ubuntu/

## 說明

Ubuntu 軟件源

## 收錄架構

AMD64 (x86_64), Intel x86

其他架構請參考 `ubuntu-ports`

## 收錄版本

所有 Ubuntu 當前支持的版本，包括開發版，具體版本見 https://wiki.ubuntu.com/Releases

對於 Ubuntu 不再支持的版本，請參考 `ubuntu-old-releases`

## 使用說明

### 圖形界面配置（新手推薦）

依次打開：系統設置，軟件和更新。在 `下載自` 中選擇 `其他站點` ，然後在香港的條目
下選擇 `mirror.xtom.com.hk`

### 手動更改配置文件

*操作前請做好相應備份*

一般情況下，將 `/etc/apt/sources.list` 文件中 Ubuntu 默認的源地址 `http://archive.ubuntu.com/`
替換為 `http://mirror.xtom.com.hk` 即可。

可以使用如下命令：

```bash
sudo sed -i 's/archive.ubuntu.com/mirror.xtom.com.hk/g' /etc/apt/sources.list
```

> 如果你在安裝時選擇的語言不是英語，默認的源地址通常不是 `http://archive.ubuntu.com/` ， 而是 `http://<country-code>.archive.ubuntu.com/ubuntu/` ，如 `http://hk.archive.ubuntu.com/ubuntu/` ，此時只需將上面的命令進行相應的替換即可，即 `sudo sed -i 's/hk.archive.ubuntu.com/mirror.xtom.com.hk/g' /etc/apt/sources.list` 

當然也可以直接編輯 `/etc/apt/sources.list` 文件（需要使用 sudo）

以下是 Ubuntu 16.04 參考配置內容：

```bash
deb https://mirror.xtom.com.hk/ubuntu/ xenial main restricted universe multiverse
deb-src https://mirror.xtom.com.hk/ubuntu/ xenial main restricted universe multiverse

deb https://mirror.xtom.com.hk/ubuntu/ xenial-updates main restricted universe multiverse
deb-src https://mirror.xtom.com.hk/ubuntu/ xenial-updates main restricted universe multiverse

deb https://mirror.xtom.com.hk/ubuntu/ xenial-backports main restricted universe multiverse
deb-src https://mirror.xtom.com.hk/ubuntu/ xenial-backports main restricted universe multiverse

deb https://mirror.xtom.com.hk/ubuntu/ xenial-security main restricted universe multiverse
deb-src https://mirror.xtom.com.hk/ubuntu/ xenial-security main restricted universe multiverse

# 預發佈軟件源，不建議啟用
# deb https://mirror.xtom.com.hk/ubuntu/ xenial-proposed main restricted universe multiverse
# deb-src https://mirror.xtom.com.hk/ubuntu/ xenial-proposed main restricted universe multiverse
```

更改完 `sources.list` 文件後請運行 `sudo apt-get update` 更新索引以生效

> 使用 HTTPS 可以有效避免國內運營商的緩存劫持

## 鏡像下載

如果需要下載 Ubuntu 的 ISO 鏡像以便安裝，請參考 `ubuntu-releases`

## 相關鏈接

* 官方主頁: https://www.ubuntu.com/
* 文檔: https://help.ubuntu.com/
* Wiki: https://wiki.ubuntu.com/
* 郵件列表: https://community.ubuntu.com/contribute/support/mailinglists/
* 提問: https://askubuntu.com/
* 論壇: https://ubuntuforums.org/
* 中文論壇: https://forum.ubuntu.org.cn/
* Ubuntu 源使用幫助： http://mirrors.ustc.edu.cn/help/ubuntu.html
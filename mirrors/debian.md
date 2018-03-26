# Debian 源使用幫助

## 地址

https://mirror.xtom.com.hk/debian/

## 說明

Debian 軟件源

## 收錄架構

Debian 支持的所有架構，如 AMD64 (x86_64), Intel x86, ARM, MIPS, ppc64el, s390x 等


## 收錄版本

Debian Old Stable, Stable, Testing, Unstable(sid)

當前 Stable 為 Debian 9，代號為 Stretch

## 使用說明


**操作前請做好相應備份**

一般情況下，將 `/etc/apt/sources.list` 文件中 Debian 默認的源地址 `http://deb.debian.org/`
替換為 `http://mirror.xtom.com.hk` 即可。

可以使用如下命令：

```bash
sudo sed -i 's/deb.debian.org/mirror.xtom.com.hk/g' /etc/apt/sources.list
```

當然也可以直接編輯 `/etc/apt/sources.list` 文件（需要使用 sudo）

以下是 Debian 9 Stretch 參考配置內容：

```bash
deb http://mirror.xtom.com.hk/debian/ stretch main contrib non-free
deb-src http://mirror.xtom.com.hk/debian/ stretch main contrib non-free

deb http://mirror.xtom.com.hk/debian/ stretch-updates main contrib non-free
deb-src http://mirror.xtom.com.hk/debian/ stretch-updates main contrib non-free

deb http://mirror.xtom.com.hk/debian/ stretch-backports main contrib non-free
deb-src http://mirror.xtom.com.hk/debian/ stretch-backports main contrib non-free

deb http://mirror.xtom.com.hk/debian-security/ stretch/updates main contrib non-free
deb-src http://mirror.xtom.com.hk/debian-security/ stretch/updates main contrib non-free
```

同時你也可能需要更改 Debian Security 源，請參考 [debian-security](/mirrors/debian-security.html)

更改完 `sources.list` 文件後請運行 `sudo apt-get update` 更新索引以生效

> 使用 HTTPS 可以有效避免國內運營商的緩存劫持，但需要事先安裝 `apt-transport-https` (Debian Buster 及以上版本不需要)

## 相關鏈接

* 官方主頁: https://www.debian.org/
* 郵件列表: https://www.debian.org/MailingLists/
* Wiki: https://wiki.debian.org/
* 文檔: https://www.debian.org/doc/
* 鏡像列表: https://www.debian.org/mirror/list
* Debian 源使用幫助： http://mirrors.ustc.edu.cn/help/debian.html
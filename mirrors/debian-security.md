# Debian Security 源使用幫助

## 地址

https://mirror.xtom.com.hk/debian-security/

## 說明

Debian 軟件安全更新源

## 收錄架構

Debian 支持的所有架構，如 AMD64 (x86_64), Intel x86, ARM, MIPS, ppc64el, s390x 等

## 收錄版本


Debian Old Old Stable, Old Stable, Stable

當前 Stable 為 Debian 9，代號為 Stretch

## 使用說明

**操作前請做好相應備份**

一般情況下，將 `/etc/apt/sources.list` 文件中 Debian 默認的源地址 `http://security.debian.org/debian-security/`
替換為 `http://mirror.xtom.com.hk/debian-security/` 即可。

> 如果你在使用 Debian 8 "Jessie" 或更早的版本，則默認的 debian-security 源地址為 `http://security.debian.org/` （和新版不同最後沒有子目錄）。下面的指南主要針對最新穩定版（Debian 9 "Stretch"），請舊版本用戶注意。


可以直接使用如下命令完成上述修改：

```bash
sudo sed -i 's|security.debian.org/debian-security|mirror.xtom.com.hk/debian-security|g' /etc/apt/sources.list
```

當然也可以直接編輯 `/etc/apt/sources.list` 文件（需要使用 sudo）

以下是 Debian Stable 參考配置內容：

```bash
deb http://mirror.xtom.com.hk/debian-security/ stable/updates main non-free contrib
deb-src http://mirror.xtom.com.hk/debian-security/ stable/updates main non-free contrib
```

更改完 `sources.list` 文件後請運行 `sudo apt-get update` 更新索引以生效。

> 使用 HTTPS 可以有效避免國內運營商的緩存劫持，但需要事先安裝 `apt-transport-https` (Debian Buster 及以上版本不需要)。


## 相關鏈接

* 官方主頁: https://www.debian.org/security/
* Debian 安全追蹤網: https://security-tracker.debian.org/tracker/
* Debian Security 源使用幫助： http://mirrors.ustc.edu.cn/help/debian-security.html
# Configuration for Joshuto

[Official Repository](https://github.com/kamiyaa/joshuto)

Tutorial: https://www.bilibili.com/video/BV1Zo4y1G7QZ

## Installation

``` bash
# 1. joshuto
JOSHUTO_VERSION=$(curl -s https://api.github.com/repos/kamiyaa/joshuto/tags | jq -r '.[].name' | sort -rV | head -n 1)
JOSHUTO_FOLDER="joshuto-${JOSHUTO_VERSION}-x86_64-unknown-linux-musl"
JOSHUTO_DOWNLOAD_URL="https://github.com/kamiyaa/joshuto/releases/download/${JOSHUTO_VERSION}/${JOSHUTO_FOLDER}.tar.gz"
JOSHUTO_COMPRESSED_FILE="${JOSHUTO_FOLDER}.tar.gz"

## 下载并安装最新版本 joshuto
wget -q "$JOSHUTO_DOWNLOAD_URL" -O "/tmp/$JOSHUTO_COMPRESSED_FILE"
tar -C /tmp -xzf "/tmp/${JOSHUTO_COMPRESSED_FILE}"
sudo mv "/tmp/${JOSHUTO_FOLDER}/joshuto" /usr/local/bin

## 清理临时文件
rm "/tmp/${JOSHUTO_COMPRESSED_FILE}"
rm -fr "/tmp/${JOSHUTO_FOLDER}"

## 验证安装
/usr/local/bin/joshuto version
```

## Get Configuration

``` bash
git clone https://github.com/LittleNewton/joshuto-config.git $HOME/.config/joshuto
```
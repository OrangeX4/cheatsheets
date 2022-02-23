---
title: proxy
categories: server
---

## get started

### Git Proxy

```bash
# 使用 Socks5，推荐
git config --global http.proxy 'socks5://127.0.0.1:7890'
git config --global https.proxy 'socks5://127.0.0.1:7890'

# 使用 HTTP，似乎无效
git config --global http.proxy http://127.0.0.1:7890
git config --global https.proxy http://127.0.0.1:7890

# 取消代理
git config --global --unset http.proxy
git config --global --unset https.proxy
```

### Pip Proxy

```bash
# 设置代理
export http_proxy='http://127.0.0.1:7890'
export https_proxy='http://127.0.0.1:7890'

# 临时设置： 
pip install -r requirements.txt --proxy=127.0.0.1:7890
```

### Pip Source

```bash
# 南大源
pip config set global.index-url http://mirrors.nju.edu.cn/pypi/web/simple/
# 清华源
pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple
# 阿里源
pip config set global.index-url https://mirrors.aliyun.com/pypi/simple/
# 腾讯源
pip config set global.index-url http://mirrors.cloud.tencent.com/pypi/simple
# 豆瓣源
pip config set global.index-url http://pypi.douban.com/simple/

# 临时使用
pip install markdown -i http://mirrors.nju.edu.cn/pypi/web/simple/
```

### Npm Proxy

```bash
# 设置代理
npm config set proxy=http://127.0.0.1:7890
npm config set registry=http://registry.npmjs.org

# 查看代理
npm config get proxy

# 取消代理
npm config delete proxy
```

### Npm Source

```bash
# 临时使用
npm --registry https://registry.npm.taobao.org install express

# 持久使用
npm config set registry https://registry.npm.taobao.org

# 查看源
npm config get registry
```

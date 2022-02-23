---
title: sheet
categories: desktop
---

## get started

### Search Folders

```bash
# 查找超过 1 GiB 的目录并排序
du -h --max-depth=1 | grep G | sort -n

# 查找超过 1 MiB 的目录并排序
du -h --max-depth=1 | grep M | sort -n
```

### Clean Space

```bash
# Apt 清理
sudo apt autoremove
sudo apt autoclean
sudo apt clean

# 删除本机部分无用文件
rm -rf ~/.local/share/Kingsoft/PDF
rm -rf ~/.cache/vscode-cpptools/ipch
rm -rf ~/.cache/pip
rm -rf ~/.config/Code/CachedExtensionVSIXs
rm -rf ~/.config/Code/CachedData
rm -rf ~/.config/Code/User/workspaceStorage
```

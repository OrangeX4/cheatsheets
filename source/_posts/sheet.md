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

# 显示大容量软件包
dpigs -H --lines=20

# 显示硬盘分析
baobab
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

# 清理 journal
journalctl --vacuum-time=1w

# 清理配置文件
dpkg --list | grep "^rc" | cut -d " " -f 3 | xargs sudo dpkg --purge
```

### Screenshot OCR

```bash
#!/bin/bash 
# Dependencies: tesseract-ocr imagemagick scrot xsel

select tesseract_lang in eng rus equ ;do break;done
# quick language menu, add more if you need other languages.

SCR_IMG=`mktemp`
trap "rm $SCR_IMG*" EXIT

scrot -s $SCR_IMG.png -q 100    
# increase image quality with option -q from default 75 to 100

mogrify -modulate 100,0 -resize 400% $SCR_IMG.png 
#should increase detection rate

tesseract $SCR_IMG.png $SCR_IMG &> /dev/null
cat $SCR_IMG.txt | xsel -bi

exit
```
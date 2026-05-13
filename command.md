# This is record for command!
---
## tmux
```
tmux new -s session_name
tmux ls
tmux attach -t session_name
Ctrl+b d
Crtl+d
```
---
## copy
复制单个文件
```
cp /xxx/xxx/xx.x /xxx/xx.x
cp /xxx/xxx/xx.x /xxx/
```
复制文件夹下所有文件
```
cp /xxx/xxx/ /xxx/xxx/xxx/ -r
```

---
## zip/unzip
压缩单个文件/压缩多个文件/递归压缩目录
```
zip archive.zip example.txt
zip archive.zip file1.txt file2.txt file3.txt
zip -r archive.zip directory/
```
解压缩
```
unzip archive.zip
unzip archive.zip -d /path/to/directory
```
仅查看压缩包中的文件列表，不解压
```
unzip -l archive.zip
```

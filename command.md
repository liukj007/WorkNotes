# This is record for command!
---
## tmux
新建/显示/连接/离开/向上滑动/删除
```
tmux new -s session_name
tmux ls
tmux attach -t session_name
Ctrl+b d
Ctrl+b [ q
Crtl+d
```
---
## copy
复制单个文件
```
cp /xxx/xxx/xx.x /xxx/xx.x
cp /xxx/xxx/xx.x /xxx/
```
复制文件夹下所有文件（不创建/创建子目录）
```
cp -r /xxx/xxx/* /xxx/xxx/xxx/
cp -r /xxx/xxx/ /xxx/xxx/xxx/
```

---
## zip/unzip
压缩单个文件/压缩多个文件/压缩单个文件夹/递归压缩目录
```
zip archive.zip example.txt
zip archive.zip file1.txt file2.txt file3.txt
zip archive.zip directory/
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

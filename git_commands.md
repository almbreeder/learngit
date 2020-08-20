## git的一些常用命令

git config --global user.name "xxx"
git config --global user.email "xxx"

**使用utf-8 Rom写文件**

添加文件
git add filename
git add filename1
提交更改
git commit -m "description"

查看状态
git status

查看提交记录
git log 

查看命令历史
git reflog

回滚版本上一个版本
git reset --hard HEAD^
git reset --hard HEAD~1

回滚到指定版本
git reset --hard commit_id
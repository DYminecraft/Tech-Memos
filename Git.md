流程
1. 工作区
2. 暂存区
3. 本地仓库

工作区 git add-> 暂存区 git commit -> 本地仓库 git status 

git reset
1. soft：需要A-B版本之间的内容，回退至A版本。
2. hard：不需要A-B版本之间的内容，回退至A版本
3. mixed(默认)：与soft类似，但需要git add

git reflog
操作历史记录，有每一次提交的id

查看文件的区别
git diff(默认)：查看工作区和暂存区之间文件的区别
git diff HEAD：查看工作区和仓库之间文件的区别
git diff --cached：查看暂存区和仓库之间文件的区别
git diff id1 id2：查看两个版本之间文件的区别
git diff id1 id2 filename：查看两个版本之间某一文件的区别
HEAD：分支的最新提交节点
HEAD~/HEAD^：HEAD的前1个版本
HEAD~x/HEAD^x：HEAD的前x个版本

git rm：从工作区和暂存区中删除

.gitignore
1. 系统自动生成文件
2. 编译生成的中间文件和结果文件
3. 运行时生成的日志、缓存和临时文件
4. 敏感信息文件

配置ssh密钥
在用户.ssh文件夹下，
```shell
ssh-keygen -t ed25519 -C "your_email@example.com"
```

git push
git pull
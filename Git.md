## 流程
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

## 查看文件的区别
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

## 配置ssh密钥
在用户.ssh文件夹下，
```shell
ssh-keygen -t ed25519 -C "your_email@example.com"
```

git push
git pull

## 分支
git branch：查看分支
git branch branch-name：创建分支
git switch branch-name：切换分支

git merge branch-name：把branch-name分支合并到当前分支

git branch -d branch-name：删除已合并的branch-name分支
git branch -D branch-name：删除未合并的branch-name分支

### 解决分支的合并冲突
一般规定：
1. feat(feature)分支，开发新功能
冲突文件需要手动编辑，commit合并完成
git merge --abort：中断合并

git rebase：理解为git A rebase to B，A分支从AB的共同祖先剪掉，接到B分支上。一般少用

rebase相较merge，把历史记录直线化。
## 一般工作流
1. git flow
	1. main：主线分支，只接受来自hotfix和release的合并。可直接在生产环境中运行。命名：v1.0.0
		1. 主版本：主要功能变化和重大更新
		2. 次版本：一些新功能、更新和改进，通常不影响现有功能
		3. 修订版本：小bug修复和安全漏洞补丁，通常不修改现有接口
	2. hotfix：main线上版本的bug热修复。命名：hotfix-#issueid-desc
	3. release：发布前的测试和验证。
	4. develop：开发。
	5. feature：开发新功能，从develop中分离出来。命名：feature-a-new-feature
2. github flow
	1. main
	2. feature：开发完开启PR，Review完发布和合并

## 关联远程仓库、本地仓库
git remote add shortname url
git push -u origin main:main 把当前仓库的main推到远程origin仓库的main
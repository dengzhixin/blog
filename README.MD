# git命令(本地仓库)

#### 基本命令
git init 初始化，就是在当前目录创建.git目录

git add 路径 将文件标记为待提交的文件

git commit -m "理由" 将已经被标记的文件提交

**git commit -v** 也是提交文件，这是会打开一个文件，里面详情描述了被标记的文件进行了什么修改，在里面输入理由后保存文件即可提交

git reset --hard xxxxxx  切换版本，注意如果此时存在没有被提交的文件，reset后文件会被git丢失

git log 列出提交记录
git reflog 列出详情提交记录，包括reset切换版本的记录


#### 分支
**git branch x** 基于当前的时间线创建x分支
**git checkout x** 切换到x分支

合并：
1.切换到需要保留的分支
2.执行checkout merge x 合并x分支到当前分支
3.使用vscode解决冲突(git status -sb 傻子都能看懂的文件状态)
4.git commit 提交，此时git会自动填写提交信息


git branch -d x 删除分支







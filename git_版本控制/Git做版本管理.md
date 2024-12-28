## 项目初始化
+ 在项目文件夹中打开Git bash，或在vscode中打开项目文件夹，创建bash终端
+ 输入`git init`初始化项目，会在项目文件夹中新建一个`.git`的隐藏文件；初始化后可以做后续git的版本控制

## 版本控制提交
+ 绑定github：

bash终端中输入：`git remote add origin github仓库地址.git`

修改主分支名称：`git branch -M main`

推送初始项目文件到github：`git push -u origin main`

+ 通过指令添加用户名和邮箱：

`git config --global user.name "your name"`

`git config --global user.email "your email"`

+ SSH秘钥生成

```git
# 1.生成新的SSH秘钥
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
# 通常会在 ~/.ssh 中生成 id_rsa 和 id_rsa.pub 文件

# 2.添加 SSH 密钥到 SSH Agent
eval "$(ssh-agent -s)"
ssh-add ~/.ssh/id_rsa

# 3.将公钥添加到github
cat ~/.ssh/id_rsa.pub
# 在github页面点击个人资料，进入SSH和GPG keys页面
# 点击 New SSH key，填写标题，将公钥内容粘贴到 Key 区域，点击 Add SSH Key。

# 4.测试 SSH 连接
ssh -T git@github.com

# 5.检查远程仓库地址
git remote -v
# 若输出为https地址，调整成SSH地址
git remote set-url origin git@github.com:username/repo.git
```

+ 创建分支并在分支上做提交修改
+ 借助可视化工具(fork)或vscode的git len插件进行修改提交
    - 更改内容点击“+”进入暂存修改
    - 添加修改内容点击提交
    - 输入`git push`上传到github

## 分支创建及管理
+ `git checkout -b <branch name>`基于当前分支创建分支
+ `git checkout <branch name>`切换分支
+ `git branch`列举所有分支
+ `git branch -D <branch name>`删除特定分支
+ `git merge <branch name>`合并分支：此项需要在主分支上操作；


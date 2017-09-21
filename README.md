# git 本地库关联github

## 在github上添加ssh key (添加一个公钥)
#### 创建一个SSH key
```javascript
root@localhost .ssh]#  ssh-keygen -t rsa -C "8888@gmail.com"
```
参数说明：
> 指定要创建的密钥类型，如rsa1 、rsa、dsa
> -C （comment）添加注释，比如邮箱

#### 复制公钥到github

输入命令后，一路回车，直到出现如下图中字符时，说明ssh key 已生成
拷贝文件id_rsa.pub中的内容
登录自己的github——settings——点击SSH and GPG keys——new SSH keys
添加title及粘贴公钥内容，点击add ssh key，即完成ssh key的添加

#### 测试ssh key

```javascript
ssh -T git@github.com
```

## 关联第一次推送
```javascript
git remote add origin git@github.com:yoclove/git-github.git
git push -u origin master
```

> git push命令可把当前分支master推送到远程，第一次推送时，添加-u参数，不但会把本地master分支的内容推送到远程新的master分支，同时把本地mater和远程mater分支关联起来，以后推送或者克隆时就可以简化命令。


# 如何使用


#### 本地命令 git init
#### 本地命令 git add .
#### 本地命令 git commit -m 'init commit'
#### github上新建一个repo 生成一下代码
```javascript
git remote add origin git@github.com:yoclove/git-github.git
git push -u origin master
```
#### 本地命令粘贴以上代码，之后使用 git push 推送到github

# Git初学笔记

## 1. download

### 1.1 [git官网](https://git-scm.com/downloads)

windows安装过程可参考[知乎吴师兄](https://www.zhihu.com/question/30119197/answer/1877067450)

### 1.2 检查是否安装成功

打开Git bash 之后输入git看到如下图所示即为安装成功

![](C:\Users\78570\Pictures\git初态.png)

## 2. git初体验及常用命令

### 2.1 git使用前

在我们进行任何的git操作之前，我们都得先切换到 Git 的仓库目录。换言之，我们得到先进入到（我们定义的）Git 仓库的**最顶层文件目录**下，然后从此目录中进入 Git Bash，这样之后的操作才能顺利进行

### 2.2 常用命令

- ①**git status**查看仓库状态(用的较为频繁)

- ②**git init**仓库初始化

- ③**git add** 将文件添加到仓库

- ④**git commit**

  git commit -m"test commit"  将文件提交到git仓库

- ⑤**git log** 打印仓库提交日志

- ⑥**git branch** 查看仓库分支情况

  创建分支例：git branch a （创建了一个a 的分支）

- ⑦**git checkout** 切换分支

  切换主分支例：git checkout a(切换到a分支)

- ⑧**git merge** 合并分支

  合并时需注意一点：**在合并分支的时候，要考虑到两个分支是否有冲突，如果有冲突，则不能直接合并，需要先解决冲突；反之，则可以直接合并。**

- ⑨**git branch -d a** 删除a分支

  不过有的时候，通过git branch -d命令可以出现删除不了现象，例如分支a的代码没有合并到主分支等，这时如果我们一定要删除该分支，那么我们可以通过命令**git branch -D**进行**强制删除**

- ⑩**git tag** 为当前分支添加标签

## 3.git进阶

### 3.1利用ssh完成git与github的绑定

1. 生成ssh key  ： 安装了 Git Bash，其也应该自带了 SSH  ，Git Bash 中输入ssh命令，查看本机是否安装 SSH。输入ssh-keygen -t rsa命令，表示我们指定 RSA 算法生成密钥，然后敲三次回车键，期间不需要输入密码，之后就就会生成两个文件，分别为id_rsa和id_rsa.pub，即密钥id_rsa和公钥id_rsa.pub. Windows 10 ThinkPad：C:\Users\think\.ssh（生成路径）                                                  针对通过Publisher 无法打开文件的情况可参考[打开公钥文件](https://blog.csdn.net/J_____Q/article/details/108866850)
2. 添加SSH key 将公钥内容复制到key的位置即可（在github中完成）
3. 验证是否绑定成功 （打开git bash 输入ssh -T git@github.com进行测试：）

​     如下图所示:

![](C:\Users\78570\Pictures\验证.png)

4. 通过git向github提交代码

​      push：该单词直译过来就是“推”的意思，如果我们本地的代码有了更新，为了保持本地与远程的代码同步，我们就需要把本地的代码           推到远程的仓库，代码示例：

``` java
git push origin master
```

​      pull：该单词直译过来就是“拉”的意思，如果我们远程仓库的代码有了更新，同样为了保持本地与远程的代码同步，我们就需要把远程的代码拉到本地，代码示例：

```java
git pull origin master
```

//一般情况下，我们在push操作之前都会先进行pull操作，这样不容易造成冲突

剩余提交代码部分请参考 [知乎吴师兄](https://www.zhihu.com/question/30119197/answer/1877067450)

**好嗨哟 ~ **


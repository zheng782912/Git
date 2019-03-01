# Git-

## 新建一个Git代码库

- **git init [project-name]**

![](https://raw.githubusercontent.com/zheng782912/Git/master/Git%20pig/1.JPG)

![2](https://raw.githubusercontent.com/zheng782912/Git/master/Git%20pig/2.JPG)

- 新建目录 demo，并将其初始化为 Git 代码库。
- 默认会在代码库目录中生成 .git 隐藏文件夹，这样才能用 Git 操控。

## 下载一个项目和它的整个代码历史

- **git clone [ 项目url ]**
    - 将指定项目全部下载到本地
    - 如下图所示将项目 JS 下载到 demo 文件夹中。

![3](https://raw.githubusercontent.com/zheng782912/Git/master/Git%20pig/3.JPG)

- GitHub 有两个 url 链接地址。

![4](https://raw.githubusercontent.com/zheng782912/Git/master/Git%20pig/4.JPG)

- HTTPS : 可以直接使用下载
- SSH ：需要将本地密钥添加到 GitHub 服务器上。
    - **ssh-keygen -t rsa -C "账号"**
    - 下图红线处可以添加密码（私人的安全电脑就没必要了）, 如果不填写直接两次回车跳过。

![5](https://raw.githubusercontent.com/zheng782912/Git/master/Git%20pig/5.JPG)

>在 C 盘某子文件夹中会出现 `.ssh` 文件夹，并且会在此目录中生成 `id_rsa` 和 `id_rsa.pub` 两个文件。

>将 `id_rsa.pub` 中的所有文本复制添加到 GitHub 的 SSH keys 中。

![6](https://raw.githubusercontent.com/zheng782912/Git/master/Git%20pig/6.JPG)

>**eval $(ssh-agent -s)** - 如果能查看到 pid 信息，那么就表示正常运行,然后就可以用 SSH key 来下载代码库。

![7](https://raw.githubusercontent.com/zheng782912/Git/master/Git%20pig/7.JPG)

## Git 分区完整提交流程

![01](https://raw.githubusercontent.com/zheng782912/Git/master/Git%20pig/01.JPG)

Git 分区分为三个区
- 工作区：代码(文件)编辑的地方;
- 暂存区：暂时缓存文件的地方。
- 在 git 中，暂存区的作用是：
    - 为了避免工作过程中出现的一些误操作，保护工作区和版本区(版本回退和撤销)
    - 可以进行分支处理

>本次演示的目录是 gitTest

![02](https://raw.githubusercontent.com/zheng782912/Git/master/Git%20pig/02.JPG)

>远程 github 目录如下:

![03](https://raw.githubusercontent.com/zheng782912/Git/master/Git%20pig/03.JPG)

- 提交 `test.txt` 为例，当 `test.txt` 开发完成之后。
- 首先通过 **git status** 查看当前工作区的状态

![001](https://raw.githubusercontent.com/zheng782912/Git/master/Git%20pig/001.JPG)

- 这时候显示一个新添加的文件为红色的 `test.txt`。
- 执行 **git add 添加的文件** 把文件添加到缓存区之后再执行 **git status** 查看缓存区状态

![002](https://raw.githubusercontent.com/zheng782912/Git/master/Git%20pig/002.JPG)

- 上面显示了绿色的新添加的文件，说明了已经把文件添加到缓存区。
- 接着通过 **git commit -m "提交说明"** 把缓存区的文件提交到版本区。

![003](https://raw.githubusercontent.com/zheng782912/Git/master/Git%20pig/003.JPG)

- 最后使用 **git push origin master** 命令将版本区的文件提交到远程 github 仓库中。

![004](https://raw.githubusercontent.com/zheng782912/Git/master/Git%20pig/004.JPG)

- 再次查看 GitHub 远程仓库，就会如下图添加进来新文件 `test.txt` 。

![005](https://raw.githubusercontent.com/zheng782912/Git/master/Git%20pig/005.JPG)


## Git 删除 GitHub 远程仓库的文件夹

- **git rm -r --cached 要删除的文件夹** （不会删除本地克隆仓库的文件夹）

![0001](https://raw.githubusercontent.com/zheng782912/Git/master/Git%20pig/0001.JPG)

- **git commit -m '提交说明'** 提交添加操作说明，缓存区的文件提交到版本区。

![0002](https://raw.githubusercontent.com/zheng782912/Git/master/Git%20pig/0002.JPG)

- **git push -u origin master** 将本次更改提交到远程 github 仓库中去，删除完毕。

![0003](https://raw.githubusercontent.com/zheng782912/Git/master/Git%20pig/1111.JPG)

![0004](https://raw.githubusercontent.com/zheng782912/Git/master/Git%20pig/0004.JPG)

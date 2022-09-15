### Git

Markdown文档.md格式

https://fishc.com.cn/ 论坛 

github desktop身份验证错误 重新登录一下

初次使用git

`git config --globbal user.name "用户名"`

`git config --globbal user.email "邮箱"`

#### Git命令行模式

进入要分配仓库的路径(文件夹)

1. `git init` **初始化空的仓库**
2. 在工作目录中添加、修改文件；
3. 将需要进行版本管理的文件**放入暂存区域**；`add`
   - `git add 文件名`
4. 将暂存区域的文件**提交到 Git 仓库**。`commit`
   - `git commit -m "干什么了"`

- `git status`**查看当前身份**
- 如果git仓库新增加了文件或者修改，则需要执行步骤3、4
- 如果放入暂存区域反悔了，则`git restore 文件名` **移出暂存区**

`git log`**查看历史存放**

![image-20220824230526512](img/image-20220824230526512.png)

**`git reset HEAD~n(回退几个版本数) `**

- `git reset --mixed HEAD~n` 

  - 默认 
  - 移动head指向，将其指向上一个快照

  - 将head移动狗指向的快照回滚到暂存区

- `git reset --soft HEAD~n`
  - **移动head指向**，将其指向上一个快照
- `git reset --hard HEAD~n`
  - 移动head指向，将其指向上一个快照
  - 将head移动狗指向的快照回滚到暂存区
  - 将暂存区域的文件还原到工作目录 (具有危险性)

#### **回滚指定版本快照**

​	`git reset 版本快照 文件名/路径`

- 可回滚、可前滚
- 要知道版本的id号

#### **版本对比**

`git diff` 版本对比工作区和缓存区的内容

- 就是说放到暂存区里后(或者回滚后)，再更改了工作目录的内容  回比较两个的不同
- 如果返回的内容过多  最后会以冒号结尾   输入h 会 展示帮助文档

`git diff 快照ID1 快照ID2` **对比两个版本之间的快照  后面加-- 文件名表示比较某个文件**

`git diff 快照ID1` **对比快照与当前工作目录的内容**  即`git diff HEAD`

`git diff --cached  [快照ID]` **比较暂存区域跟仓库的内容**

![image-20220826235911479](img/image-20220826235911479.png)

#### 修改最后一次提交

更为简单的方法

- 执行待 `--amend`选项的`commit提交命令`,  Git就会更正最近的一次提交 

- `-m`带上后不会进入提交命令的编辑
- `git commit --amend  -m`

#### **误删文件**

`git reset 文件名`

`git checkout`

#### **删除文件**

- 两个步骤
  1. `git rm 文件名` 该命令只是删除工作目录和暂存区域的文件，取消跟踪，下次提交时不纳入版本管理，并不删除快照
  2. `git log`  

- 若是工作目录与暂存区域的文件不一致
  - 直接使用`git rm 文件名`会提示不一样  加上`-f`会强制删除 同时删除
  - 加上`--cached` 文件名删除暂存区域爆率工作区域的文件

#### **重命名文件**

`git mv 源文件 新文件`



### 分支

<img src="img/image-20220831224242477.png" alt="image-20220831224242477" style="zoom:67%;" />

- `git branch 新分支名`创建新分支
- `git reflog`
- `git log --decorate`  显示提交的所有引用`--oneline --graph --all`仅显示第一行，以抽象的图像显示，显示所有
- `git chekout 分支名`  切换分支
- `git merge 分支名` 将指定的分支名 添加到本分支
  - 若是有文件冲突，则不会合并，需要手动修改

- `git branch -d 分支名`删除分支

 

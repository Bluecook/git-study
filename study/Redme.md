#### .gitignore 文件

在目录下新建一个.gitignore 文件

**/node_modules(忽略所有的node_modlues文件夹)
/db (忽略db文件夹下的所有文件)

1、git init 初始化本地仓库
2、git add . (提交所有文件到本地仓库添加文件到暂存区)
3、git commit -m 'message'(将暂存区所有文件添加到本地仓库,message即是我们用来简要说明这次提交的语句)
4、git ls-files (查看已经放到本地仓库的文件)
把本地库与远程库关联（如果已经有origin关联则可以忽略）
5、git remote add origin 你的远程库地址
6、推送（提交）代码：
   git push <远程主机名> <本地分支名>:<远程分支名>
 7、git fetch (从远程仓库下载新分支与数据)(-----执行7后需要执行8)

8、git merge (从远端仓库提取数据并尝试合并到当前分支)

 9、执行 git fetch origin master 时，它的意思是从名为 origin 的远程上拉取名为 master 的分支到本地分支 origin/master 中。既然是拉取代码，当然需要同时指定远程名与分支名，所以分开写。
 10、执行 git merge origin/master 时，它的意思是合并名为 origin/master 的分支到当前所在分支。既然是分支的合并，当然就与远程名没有直接的关系，所以没有出现远程名。需要指定的是被合并的分支。
 11、执行 git push origin master 时，它的意思是推送本地的 master 分支到远程 origin，涉及到远程以及分支，当然也得分开写了。

####  推送到远程仓库

12、git push [alias] [branch](以上命令将你的 [branch]本地分支推送成为 [alias] 远程仓库上的分支)

13、git push origin master    # 推送到 Github



#### 远程仓库以及常用分支指令

//远程分支名 仓库地址
git clone -b 分支名 仓库地址

//查看远程分支
git branch -r
//创建本地分支并关联
git checkout -b 本地分支 origin/远程分支
git status  //拉取之前先查看状态 ，确定本地仓库都保存了 
git pull  //进行拉去对应分支的内容(需要切换到对应分支)（如果没有本地没有，远端有，需要关联）
git add .    //暂存 内容  
git commit -m '备注'  //存储到本地仓库
git push  //上传到远端仓库
与远程代码仓库建立连接：git remote add origin 代码仓库地址
将远程分支拉到本地：git fetch origin index（index远程分支名）

最后一步将远程分支拉取到本地：git pull origin index（index为远程分支名）

####   创建v1分支提交步骤

查看所有分支：

         git branch 
创建分支：

        git branch 仓库分支名   //例子 git branch v1      v1即是仓库分支名

切换到v1分支：

         git checkout v1

查看分支状态

          git status    //红色提示为未暂存（创建分支一定查看分支状态）

执行add指令：

   git add .    //add之后查看状态提示字的颜色为绿色 表示已暂存，未存储到本地库

执行commit注释：

     git commit -m "第一次提交代码"  //注释自己写随便写  提交之后状态为 clean   

提交到服务器：在分支状态提交的就是分支仓库，在master主分支上就是提交的master仓库
        git push 提交到远端仓库将v1分支合并到master本地分支
创建v1分支：

         git branch v1

切换到v1分支：

         git checkout v1

在v1分支仓库里添加一个  我是文件.txt   文件

查看分支状态

          git status    //红色提示为未暂存（创建分支一定查看分支状态）

执行add指令：

         git add .    //add  之后查看状态  提示字的颜色为绿色 表示已暂存，未存储到本地库

提交commit本地文件：

         git commit -m “增加readme.txt”   //提交之后状态为 clean 

切换到master分支：

        git checkout master

把v1分支合并到master分支：

         git merge v1  //注意主分支合并 其他分支  或者你在其他分支上合并其他分支，都要切换到要合并的分支上     //并且一定要确定分支状态是不是为全部提交 
        //提交master到服务器：
         git push //在master分支上操作


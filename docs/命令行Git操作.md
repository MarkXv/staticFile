# git的命令行操作
>尽量使用明令行对项目进行git操作（gitlib库）  


## 1. 打开明令行窗口
- 首先平台必须安装git客户端  
	[git安装包下载](https://github.com/git-for-windows/git/releases/download/v2.17.0.windows.1/Git-2.17.0-64-bit.exe "git的安装")
- 点击安装（网上有安装教程，傻瓜式安装）  
	[git在Windows下安装步骤](https://blog.csdn.net/jiguanghoverli/article/details/7902791)
- 在对应项目的根目录下右键
	![](2018-05-06_145852.png)  
	![](2018-05-06_150524.png)  
- 也可以在文件管理系统栏使用CMD明令进入命令行窗口（什么方法都行）
	![](2018-05-06_150610.png)  
	![](2018-05-06_150610.png)  
	在这里如果不能再CMD下使用则将git安装目录下的CMD文件夹路径添加到path环境变量中即可  
	![](2018-05-06_151158.png)
## 2. git明令连接gitlib的简单操作
> 我们使用git clone明令克隆远端仓库时为克隆的存储库中的每个分支创建远程跟踪分支，我们就有了对远程仓库的跟踪  
> 如果我们需要新增远端连接通过git remote add来实现  
> 通过git remote -v查看目前已有的连接
## 3. 项目中常见操作
- 查看本地与远端的同步情况（属于自己的分支）  
	`git status`  
	这个操作也是本地库与远端自己分支的比对
- 同步远端（上游仓库）  
	`git pull upstream `   
	上班之前完成这个操作
- 在修改完成后项目推送到远端的操作
	- 将提交的信息添加到索引库中  
		`git add .`  
		添加全部信息
	- 将修改信息进行推送  
		`git commit -m"本次提交的摘要信息" ` 
	- 将本地的更新推送到远端（属于自己的分支）  
		`git push `  
		与git pull相似
	- 通过web进行请求分支的合并    
		[git操作](https://github.com/MarkXv/staticFile/blob/master/docs/Windows%E4%B8%8BEclipse%E4%B8%ADGit%E7%9A%84%E5%9F%BA%E6%9C%AC%E6%93%8D%E4%BD%9C.md)中有关于请求合并的操作流程  
## 4. 注意
- 在git push 和git pull时极易发生冲突  
	通常的办法就是手动将冲突修改，然后重新提交即可
- 有冲突的情况下回导致分支合并时无法合并  
	在项目中避免修改不属于自己的代码，在同属于不同的人的文件处理时，要求一个进行修改。





		106  git push
      107  git pull upstream
      108  git status
      109  pwd
      110  ls -a
      111  vi .gitignore
      112  ll
      113  git pull upstream
      114  git status
      115  git add .
      116  git commit -m"sj"
      117  git push
      118  git pull  upstream
      119  git status
      120  git add .
      121  git commit -m"sj"
      122  git push
      123  git pull upstream
      124  vim .gitignore
      125  history

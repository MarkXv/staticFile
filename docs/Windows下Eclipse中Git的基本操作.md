#windows环境下Eclipse中git的基本操作
### 1.新建分支（fork）
通过Web进入需要新建fork的远端仓库
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_085324.png)
在相应的仓库中会有一个fork按钮如下图  
**注意：在登录状态下才有这个按钮**
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_085629.png)

fork点击之后会新建相应的分支，并进入相应的分支中
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_090124.png)
之后可以在其他的位置下点击fork回到自己的仓库

### 2.使用Eclipse链接远程仓库
1.在Explise工具的Windows ->show view->other 下添加Git的
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_084345.png)
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_084809.png)

之后会出现一个新的工作空间
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_084837.png)

2.新建一个git链接
方便起见我们可以将git的本地存放位置进行修改
Windows->Preferences->Team->Git
将Default repository folder 修改为自己的目录
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_090503.png)
clone远程仓库的项目到本地
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_091343.png)
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_091455.png)
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_091616.png)
clone后的项目
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_091644.png)
### 3.将远程仓库的项目打入Eclipse中
File->Import->Maven
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_092118.png)
根据项目的不同选择自己的项目进行导入   
如果重新导项目时可能会出现
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_093337.png)
此时由于在删除项目的时候Eclipse会自动close项目仍然会有删除的项目  
删除之后进行导入就可以了
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_093808.png)
打入完成
### 4.本地编辑之后进行commit and push
右击git中的远程链接，Commit...
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_094050.png)
进去commit的界面
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_094237.png)  
点击“+”相当于命令行的 git add

![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_094237.png)  
点击Commit and Push 相当于 git commit and git push 

提交时如果遇到提交过程终止，会导致Eclipse认为已经提交报错等问题，    
尝试修改一下重新commit and push
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_094638.png)
输入username and password 点击OK  

---
提交过程会出现一个本次push的信息的消息框，点击close

### 5.在web端发起分支合并的请求
项目commit and push 后发起分支合并的请求  
在Web端点击Merge Requests进入分支合并的操作页面  
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-23_191320.png)  
点击页面new merge requests  


![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-23_191350.png)
选择需要合并的分支和要合并到的主分支点击
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_095606.png)
之后等待管理员将分支合并即可

### 6.远程仓库中的项目与本地同步
远程仓库进行分支合并之后参与项目的均应该在工作开始之前同步远程仓库中的项目。  
新建远端仓库的连接   
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_095813.png)    
之后pull仓库均从这里进入  
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_100136.png)
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_100157.png)
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_100332.png)
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_100352.png)

![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_100412.png)

由于Ecplise的版本不一致  
可能pull的途径不一样
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_101021.png)

![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_101059.png)

或者一些版本使用 Merge进行pull
![](http://raw.githubusercontent.com/MarkXv/staticFile/master/img/go_git/2018-04-24_101520.png)


### 7.注意事项
	在导入项目木之后可能由于导入的是JRE而导致打包启动报错
	
### 8.本示例的启动
	1. 现行打包core使用Maven Install进行打包将core打包到Maven的本地仓库，其他的项目便可以依赖core  
	2. 启动api-server 时使用Maven Builde 进行启动（clear package spring-boot:run）
		1. clean 表示清楚之前的项目保证现在的项目时最新的
		2. package 对当前项目进行打包
		3. spring-boot 是spring-boot-maven-plugin
		
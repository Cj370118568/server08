#server 2008日常维护步骤
-
### 每日检查：
1. [事件日志检查（应用程序／安全性／系统）](事件日志检查.md)

	点击 "开始" -> "管理工具" -> "事件查看器"
	
2. 共享文件夹检查

	+ 右键“网络” 属性 网络和共享中心  共享和发现 
关闭，网络共享，文件共享，公用文件共享，打印机共享，显示我正在共享的所有文件和文件夹，显示这台计算机上所有共享的网络文件夹
	+ 发现有未经允许的共享文件夹,马上删除
	
3. 本地用户和组检查
	
	a)[开始]->（[控制面板] ->）[管理工具]->[计算机管理]->[本地用户和组]->[组] 
	
	b)双击“名称”列中Administrators用户，查看成员。
	
	c)发现有未经允许的用户和组,马上删除
	<p align="center"><img height="480" src="Recourse/5.JPG"/>

5. 系统服务和应用程序检查

	1） 依次展开[开始]->[控制面板]  ->[添加删除程序] 
	
	2） 查看系统安装组件和应用程序。
	
6. 进程检查

	+ 打开任务管理器，切到进程选项查看当前运行的进程，发现可疑的进程关闭掉，找到对应的路径把程序删除掉，必要时联系我。
	+ 下面是上周拍下的正常运行的进程
	<p align="center"><img height="480" src="Recourse/6.JPG"/><img height="480" src="Recourse/7.JPG"/> 
7. 检查CPU使用和内存占有情况

	+ 检查主要服务器操作系统的资源控制策略，查看是否对CPU、硬盘、内存和网络等资源的使用情况进行监控；
	
	+ 每日至少三次查看“系统资源监控器”及磁盘使用状况并记录。 或使用集中监控平台实时监控系统资源使用情况。
	+ CPU使用率不超过70%。 
	+ 内存使用率不超过70%
	
8. 检查系统更新是否正常

	+ 系统的每个更新补丁都必须要安装
	
9. 杀毒软件使用
	+ 发现可疑文件立刻删除
	+ 1~2天扫一次毒
	+ 随时保持杀毒软件病毒库是最新的


### 每月检查
1. 数据库检查
	
	+ 检查数据库日常维护的运行结果
	+ 检查数据库的事务日志
	+ 检查数据库文件的碎片
	+ 数据库更新情况
		
		1） 依次展开[开始]->[控制面板]  ->[添加删除程序] 
		
		2） 查看操作系统和主要数据库管理系统的补丁更新情况。 

2. 日志分析

	检查主要服务器的恶意代码防范策略，查看是否安装了实时检测与查杀恶意代码的软件产品,并且及时更新了软件版本和恶意代码库
	
3. 系统服务检查

	检查是否设置了专门的升级服务器实现对主要服务器操作系统补丁的升级，主要服务器操作系统是否具有操作系统补丁更新策略；
	
	1）系统安装的组件和应用程序遵循了最小安装的原则； 
	
	2）不必要的服务没有启动； 
	
	3）不必要的端口没有打开； 
	 
	4）
	a)“共享名”列为空，无C$、D$、IPC$等默认共享。
	b)HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Lsa\restrictanonymous值不为“0”（0表示共享开启）  
	5）系统补丁先测试，再升级；补丁号为较新版本。
	
	6）检查主要服务器操作系统和主要数据库管理系统的资源控制策略，查看是否设定了终端接入方式、网络地址范围等条件限制终端登录 
# miaoyan
电影可视化系统

更新内容详见自述文件
特别标出
1.	界面进行了优化，再也不是红绿色盲测试了
2.	Demo演示进行了更新，去除了桌面背景，添加了背景音乐
3.某些界面采用了无窗口模型，更加美观



1.运行方法
1.首先运行本程序的前提是建立一个符合如下链接的数据库：host='localhost', user='root', password='201314xIn', port=3306
	将github上的16.sql导入到文件中
2.解压miaoyan.zip从page1文件开始运行
3.如果想测试爬虫，请在第一步中不要导入16.sql，而是运行s1.python来建立表格并运行爬虫.，
		
2.项目依赖环境
		python3.0
		第三方库包括：pyecharts
							pyecharts_snapshot
							PyQt5
							Pandas
							pymysql
							threading
							qtpandas
3.	实现功能以及实现技术
首先，我的文件page1命名的由来是程序的第一个界面，故它从此开始运行。Dialog1和dialog2分别代表第一页的两个弹窗
Mine文件对应程序的主界面，Mine1，Mine2，Mine3，Mine4，Mine5代码程序的5个功能，
1.多线程
		实现技术：通过threading库，将要进行的生成png操作和显示html操作分为两个线程，使用threading.Thread（target = ‘’，args = ‘’）来实现
		这段代码主要位于每个ui类中的 
2 .可视化
	实现技术：通过pyecharts，声明一个模型，然后用add添加数据和元素即可、
这一部分主要位于每一个界面中的
 
3.额外功能：展示数据库
实现技术：声明一个DataFrameModel，将数据库db参数赋值给该窗口
这个功能的代码位于mine5中的类声明之前以及后面一句
self.model.setDataFrame(db)
4.	实现报表
实现技术：用doc库来声明一个word文档，并通过add_picture函数向其中添加内容，最后用os打开
主要位于mine.py中的click6
 
							

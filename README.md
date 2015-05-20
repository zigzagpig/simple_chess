###简介 简单记谱程序

简单的象棋游戏程序，主要实现象棋二人对局、每一步记谱（如车二平七），结束后输出到文件，包含象棋规则的合法性判断。本程序主要是寻找编程的手感，为接下来学习 ruby 做准备。程序用 C 语言实现，300多行。基本做到了模块化程序设计，部分模块使用了同构复用。但存在着使用全局变量的大毛病，程序的界面也相当简单且没有方便的操作方式，需要输入命令。已经跟同学对弈多盘，暂未测试出问题。

---
###程序包含的模块简要伪代码
```rb
main//主函数
	read_basic_word//读取关键汉字
	read_chess_in//读取初始棋盘
		set_shuxing//设置棋子初始颜色
	show//读取关键汉字
	打开文件用于写入棋谱;
	start//开始下棋 直到游戏结束
		get_command//获取下棋指令
		moves//根据指令移动
			move_is_ok//判断下棋命令是否出界
				name_zu//卒、兵
				name_pao//炮
					i_touch//四向搜索以判断能否移动，下同
				name_ju//车
					i_touch
				name_ma//马
				name_xiang//相、象
				name_shi//士
				name_jiang//将、帅
					i_touch
				上面//判断下棋命令是否符合棋子和移动规则
				若是符合//执行 go 移动
					go//指令合法则进行移动
						pu//打谱
						is_win//是否赢了结束
						移动是否杀子;
						show//刷新棋盘布局
						回合结束,转换颜色;
	关闭文件并结束;
end
```
##象棋初始界面
![](http://7xivgw.com1.z0.glb.clouddn.com/15-5-16/45592599.jpg)

---

###简单的演示
####第1步

![](http://7xivgw.com1.z0.glb.clouddn.com/15-5-16/34365478.jpg)

####第2步
![](http://7xivgw.com1.z0.glb.clouddn.com/15-5-16/61765763.jpg)

####第3步
![](http://7xivgw.com1.z0.glb.clouddn.com/15-5-16/23189853.jpg)

####第4步
![](http://7xivgw.com1.z0.glb.clouddn.com/15-5-16/64431964.jpg)

####第5步
![](http://7xivgw.com1.z0.glb.clouddn.com/15-5-16/66704470.jpg)

####第6步
![](http://7xivgw.com1.z0.glb.clouddn.com/15-5-16/16084277.jpg)

####第7步
![](http://7xivgw.com1.z0.glb.clouddn.com/15-5-16/90869268.jpg)

---
###演示的输出结果
![](http://7xivgw.com1.z0.glb.clouddn.com/15-5-16/98925268.jpg)

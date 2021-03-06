# 项目背景 #

JQBolt 是一款基于 迅雷Bolt界面引擎 的Lua框架，其设计借鉴了 Javascript 的 JQuery 框架 “Write Less,Do More”（写得更少,做得更多）的核心理念，在框架设计、API设计方面都参考了JQuery的思想。

# 项目介绍 #
- 名称：JQBolt
- 官网：https://github.com/zhenghecn/JQBolt/
- 开源协议：与Lua一样，使用MIT许可协议
- 功能：文档对象选择、链式调用、事件绑定的前后端分离、全局数据存取封装、位置快捷设置、动画效果

# 快速入门 #
### 文档对象选择 ###

目前支持以#ID开头的文档对象选择方式：

根据ID选择

    jqbolt("#button"，self).size();
	
选择子对象

    jqbolt("#button > *"，self).size();

根据类型选择子对象

    jqbolt("#button > LayoutObject"，self).size();

选择兄弟对象

    jqbolt("#button ~ LayoutObject"，self).size();

### 链式调用 ###

大部分API都支持链式调用，使得编写的代码更加简单并且性能更好：

    jqbolt("#button"，self).eq(1).data("key","value").size();

### 事件绑定的前后端分离 ###

可以将所有Bolt界面XML资源中的事件绑定通过Lua代码方便实现，实现前后端分离，并且编写的代码结构性更强，支持LayoutObject的所有事件：

    jqbolt("#button"，self).ondragquery(function ( ... )
		do more
	end);

### 全局数据存取封装 ###

再也不怕记不住XLGetGlobal、XLSetGlobal怎么拼写了，并且提供了语义更明确的删除操作：

    jqbolt().data("key","value")	--set
	jqbolt().data("key")			--get
	jqbolt().removedata("key")		--remove

### 位置快捷设置 ###

更快捷的对象位置设置，不必再自己计算对象的坐标，还支持相对位移操作：

    jqbolt("#button"，self).left(100);	--set
	jqbolt("#button"，self).left();		--get
	jqbolt("#button"，self).right();
	jqbolt("#button"，self).height();
	jqbolt("#button"，self).width();
	jqbolt("#button"，self).offset(10,-10);

### 动画效果 ###

封装原有的动画API，操作更简单

# 项目目标 #

- 支持更强大的文档选择器
- 通过对事件的绑定封装，支持代码性能分析
- 通过使用JQBolt，实现Bolt的基础控件集

# 交流 #
 
- 邮件交流：yulong@zhenghe.cn
- Bolt群：@于龙 @孙超 @郝林
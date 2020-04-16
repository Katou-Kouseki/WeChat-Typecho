# WeChat-Typecho
微信小程序版Typecho https://www.xsy.fun/

## 介绍
本开源小程序最开始应该是由成都第七帅大佬写的，经过安好屋大佬的修改，然后再到我手上修改前端页面，所以函数命名规则不是我写的，因为我使用的是handsome主题，文章摘要好像有点问题，所以我就删掉了，推荐文章也删了，感觉没什么必要，如果不删除那就和轮播图功能重复了，基本上我能读懂改过的代码都写上了注释，应该很好自己修改，建议善用全局搜索。

![](https://github.com/xsy2004/WeChat-Typecho/raw/master/yl.jpg)

## 教程
在```/common/vendor.js```第236行修改你的信息，这函数命名规则不是我写的，别打我

在```/pages/about/home/home.wxml```第6行和第8行修改你的博客名和简介

在```/pages/index/index.wxml```第三行修改小程序最顶上的名称

在```/pages/index/index.js```第57行修改每篇文章下的作者信息

在```/app.json```第16行修改你的博客名

在```/pages/about/home/home.wxss```第2行修改关于界面的头像地址

在```/pages/about/home/home.wxml```第4行修改头像地址

在```/pages/about/home/home.js第73```和74行修改微信赞赏码的图片地址

在```/pages/details/details.wxml```第157行修改你自己想点赞后出现的图片，反正自己改


### 代码解释
app.js是最初的入口文件，wxss是相当于html项目中的css，如果在js里添加新代码要再json文件中声明。

static是放资源文件的地方，可以自行修改素材，但好像不是全部都引用了，自己慢慢找吧。

pages是所有的页面，可以被引用跳转，例如跳转关于页面，地址为```pages/about/home/home```about下的home目录的home方法叭，大概就这意思，我也是第一次接触微信小程序。。

这个项目引入了Color UI，可以自己去下载demo自己 ~~抄~~ 写。

在/pages/index/index.js第26行下面是修改首页那两个跳转按钮的

```
	categories: [{
		cuIcon: "write",//这个是图标，可以自己去color ui的小程序找名称修改
		color: "white",//这个是文字颜色
		bg_color: "bg-gradual-green",//这个是背景颜色，可自行修改
		badge: 1,//小红点文章个数，填1就是一个小红点，大于1就是显示数字，大于99显示99+
		mid: "24",//这个是分类id
		title: "随笔",
		name: "Essay"
	}，
```
可以自行添加参数，调用方法如下```{{item.title}}```使用前要声明```wx:for="{{categories}}"```

求大佬赞赏啦![](https://github.com/xsy2004/WeChat-Typecho/raw/master/zsm.jpg)

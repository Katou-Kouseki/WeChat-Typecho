[![tittle](https://github.com/xsy2004/WeChat-Typecho/raw/master/tittle.png "tittle")](https://github.com/xsy2004/WeChat-Typecho/raw/master/tittle.png "tittle")
# WeChat-Typecho
微信小程序版Typecho https://www.xsy.fun/

## 前言
最近我看到不少博主都发布了微信小程序版Typecho，但是质量层次不齐，开源的界面不美观，也有美观的，但是要收费，秉着节俭的原则，还是在github尝试了n多的项目之后找到了个真正能跑起来的项目，先不说界面怎么样，起码是可以跑起来的，其他项目多多少少在我这个主题下有些问题，也可能是当时的调试问题吧，毕竟是第一次接触微信小程序，最开始还不是很熟悉项目的构建，后来慢慢花的时间多了才摸清楚具体的操作，正是因为开源的程序界面并不是很美观而且handsome主题启用他们比较困难，例如头图的丢失，文章摘要的丢失，等等，所以我选择在一版能跑起来的项目上修改前端页面。

### 项目地址
[WeChat-Typecho](https://github.com/xsy2004/WeChat-Typecho "WeChat-Typecho")
求求大佬Star啊，卑微
#### 扫码预览
[![小程序码](https://cdn.xsiy.ltd/photo/cid178/cxm.jpg "小程序码")](https://cdn.xsiy.ltd/photo/cid178/cxm.jpg "小程序码")

## 特别鸣谢
把致谢放在最开头是因为我自己也是一个~~码农~~菜鸡，所以深知写代码的不容易，所以在此特别感谢

[WeTypecho](https://github.com/MingliangLu/WeTypecho "WeTypecho")——成都第七帅大佬，博客端插件作者
[Pisces-Mini-Program](https://gitee.com/Byclemon/Pisces-Mini-Program "Pisces-Mini-Program")——基于WeTypecho修改作者
[ColorUI](https://github.com/weilanwl/ColorUI "ColorUI")——小程序CSS库

## 说明
为什么我没有选择github上的其他作者的项目？
因为我希望我的微信小程序不仅仅是可以浏览，而是可以交互，用户可以做到使用小程序评论，去表达对文章的看法与思考，如果以后我有能力去编写后端js了，我会将github上我觉得很好看的项目给完善
例如 [WxappForTypecho](https://github.com/loveempathy/WxappForTypecho "WxappForTypecho")

#### 项目中的字母函数命名不是我写的！！！

## 小程序发布要求
1. 域名已备案
2. 域名开启Https
3. 已成年，或者拥有18岁以上微信绑卡账号

[![微信端域名配置](https://cdn.xsiy.ltd/photo/cid178/1.png "微信端域名配置")](https://cdn.xsiy.ltd/photo/cid178/1.png "微信端域名配置")

将你的域名添加进去，如果你的图片等资源存放的地址不是你上面设置的域名
还需要将你的图片资源域名添加进去，否则小程序端可能无法显示资源。

## 功能
目前支持的基本功能如下：

1. 查看分类目录文章
2. 个人关于界面显示
3. 首页文章轮播图
4. 评论文章
5. 自动获取文章头图
6. 图片视频显示
7. 支持markdown,html解析
8. 推荐阅读文章
9. 搜索文章
10. 自定义字符显示不同卡片样式

### 自定义字符
style （首页文章显示样式，值默认为3，其他的我也没测试）

1. 代码大图卡片形式
2. 代表小图卡片显示形式
3. 代表背景卡片形式

isPay（文章是否需要广告启动，默认为0） 1：是 0：否

thumb（文章缩略图）


## 教程
不能获取到文章可能是PHP版本的问题！！！！！
之前没讲是我的疏忽，其实我一开始也没发现

**本小程序测试于PHP7.1,PHP7.0版本，有问题请更换PHP版本**

在```/common/vendor.js```第236行修改你的信息，这函数命名规则不是我写的，别打我

在微信开发者工具调试的时候要在详情里面勾选，不校验合法域名，web-view，那一项，要不然在调试的时候会显示不了文章

**修改r和i并且与后端小程序对应上**

![](https://cdn.xsiy.ltd/photo/cid178/2.png)

在```/pages/about/home/home.wxml```第6行和第8行修改你的博客名和简介

在```/pages/index/index.wxml```第三行修改小程序最顶上的名称

在```/pages/index/index.js```第57行修改每篇文章下的作者信息

在```/app.json```第16行修改你的博客名

在```/pages/about/home/home.wxss```第2行修改关于界面的头像地址

在```/pages/about/home/home.wxml```第4行修改头像地址

在```/pages/about/home/home.js第73```和74行修改微信赞赏码的图片地址

在```/pages/details/details.wxml```第157行修改你自己想点赞后出现的图片，反正自己改

### Typecho插件端
复制`WeTypecho`到插件目录， 在后台激活并设置，名字要对否则报错。
- APISEC
- 博客作者名称
- 博客网址

这三项必填，其他随便（吧）

要与小程序端config.js中API_SECRET字段保持一致，否则无法从服务器读取数据

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

求大佬赞赏啦![](https://cdn.xsiy.ltd/wxxcx/zsm.jpg)

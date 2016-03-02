## 使用前必读：
需更改内容位置(如果真有人想用的话)：

1. index.html 顶部百度分析代码；
2. index.html 底部CNZZ、GA统计代码；
3. index.html & resume/index.html 内简历内容；
4. index.html GA 上方 disqus 评论代码 shortName 部分替换，有两处；
5. index.html 第 81 行blog链接代码；
6. index.html 第 42 行网易云音乐外链代码。

### 建议修改：

1. /images/favicon_o.png, blog.png, blog-full.png, toggle_o.png, toggle_x.png；<br>
2. /images/bg 所有图片(原图经过模糊处理)。

---

## TravelLife

这是第一次独立设计个人主页，借鉴了[麦田](http://itmyhome.com)这位博主的排版，然后根据自己的需求作的修改；名称没有想太多，就以旅行的背景图取意，叫作旅行人生。

虽然代码量不多，但还是选择开源出来[Github/TravelLife](https://github.com/James0112/TravelLife)，希望多交流；除了简历部分之外，必须修改的地方不算很多，用上也不是难事。

## About

在此说明一下几个技术点，尽管都不是很难：

#### 背景图轮播

这里并没有使用传统的 javascript 实现方式，而是直接使用 css3 的 animation + @keyframes 规则：


```css 
#bg {
	position: relative;
	height: 100%;
	width: 100%;
	background: url(../images/bg/00.jpg) center no-repeat;
	-moz-background-size: cover;
	background-size: cover;
	-webkit-animation: bg 100s ease-in-out infinite;
	     -o-animation: bg 100s ease-in-out infinite;
	        animation: bg 100s ease-in-out infinite;
}

@-webkit-keyframes bg {
	6.25% {
		background-image: url(../images/bg/00.jpg);
	}
	18.75% {
		background-image: url(../images/bg/01.jpg);
	}
	31.25% {
		background-image: url(../images/bg/02.jpg);
	}
	43.75% {
		background-image: url(../images/bg/03.jpg);
	}
	56.25% {
		background-image: url(../images/bg/04.jpg);
	}
	68.75% {
		background-image: url(../images/bg/05.jpg);
	}
	81.25% {
		background-image: url(../images/bg/06.jpg);
	}
	93.75% {
		background-image: url(../images/bg/00.jpg);
	}
}

...

```

注：火狐浏览器官方、IE并不支持 @keyframes 规则。 (仅限写文时)

#### DIV + CSS 网页简历

除了几处可以用 div 代替的 section 以外,简历全用 DIV＋CSS 完成，最宽为 846px;

所有代码均在 resume 文件夹中，为了可以更好的维护，拆分为 resume.html, resume.css, resume-screen.css & resume-screen-details.css;

resume-screen.css 为几个主要变化的屏幕宽度样式，resume-screen-details.css则是强迫症爆发，让简历排版在改变屏幕大小时平滑变化,所以基本全部屏幕适用。

#### CDN 加速

和我的个人博客一样，使用的是又拍云的加速服务，不用的话...高清图像加载太慢(就是喜欢高清，其实主要是懒得做 web 专用图片，再者服务器在国外速度还是受比较大影响的，特别国内这种环境下。)

#### 启用 https 

这是被逼的，不知道是不是域名后缀太非主流，经常被跳转到百度域名纠错系统，严重到必须使用代理才能访问。所以特意去研究了一番：

* [HTTP/2 与 WEB 性能优化（一）](https://imququ.com/post/http2-and-wpo-1.html)
* [HTTP/2 与 WEB 性能优化（二）](https://imququ.com/post/http2-and-wpo-2.html)
* [HTTP/2 与 WEB 性能优化（三）](https://imququ.com/post/http2-and-wpo-3.html)

发现了么，方向偏了去看做优化，其实用上 http/2 的前提是 SSL 部署；网上查阅一番，最终还是回到屈前辈的这篇文章——[Let's Encrypt，免费好用的 HTTPS 证书](https://imququ.com/post/letsencrypt-certificate.html)，我的主页和博客都是使用的这个证书，方法和步骤里面都有，不再重复。

可能会发现我的主页小绿锁并没有亮，又是怎么回事？

因为我强制把网易云音乐的 iframe 外链改成了 https，所以产生错误，而如果用 http 则会无法打开网易云音乐。

同时自己发现并没有发现有支持 https 外链的音乐平台（如果有人知道，请告诉我！），就只有暂且先用着网易云。

#### 施工页面

根目录里除了有 index.html 页面，还有一个 default.html 是用于当主页修改时，临时切换的页面

#### 结语
以后主页会根据需要一步步添加功能完善。













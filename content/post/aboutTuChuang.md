---
title: "关于图床"
date: 2018-09-14T16:12:19+08:00
draft: false
---

#  关于图床

> 博客里免不了使用图床，比较了很多家，最终一直犹豫使用阿里的还是腾讯的。

> 由于博客全是放在 `Github` 上的静态页面，图床的防盗链 貌似设置之后，由于请求的时候请求头中根本没有携带 `Referer` ，所以防盗链一直是拦的，也就没办法显示图片。
 

# 1. 阿里对象存储 OSS 

  * 先说优点
   1. 阿里云的对象存储的优点是比较稳定，功能也更加齐全。

   2. 更改设置后能立即生效。

   3. 除了常规的存储之外，还有很多图片相关的功能。

   4. `http` 和 `https` 的图片都能稳定的在各种浏览器上展示。

   5. 有手机 App （`阿里云`）来管理云产品，查看使用明细、产生具体的报表、上传图片、删除图片都很方便，对于旅游什么的很友好。

  * 再来说说缺点

  	1. 首先价格方面：存储包 100 G 是 9 元 ，流量、请求 都要额外收费。 而腾讯的 COS 每个月都有免费额度。

  	   	所以当时我花了 9 块钱买了 OSS 一年的存储包之后，还在测试，就给我发一封短信，告诉我已经欠费 0.01 元。

  	   	看了一下，果然是流量扣费。虽然不多，但是正式使用之后，我的图片都是高质量的，所以流量费算下来也不是特别少。 

  	   	有的人可能说，你可以压缩图片啊，我是这么考虑过，但是我还是喜欢高质量的图片，这样即便我为存储支付一定的费用也是心甘情愿的。

       	因为个人博客，随着内容的增多，大部分的图片都是存储在 OSS 上，真正使用下行流量的文章，或者别人看的文章中占的图片要小于我 OSS 上总图片的张数，所以大部分的费用应该集中在存储方面。请求和流量其实对于一个博客来说并不多。

  		而且随着博客内容的后续增多，请求和流量基本上维持不变，主要是存储的图片会越来越多。

  	2. 没有自己的 Mac 或者 Windows 客户端，只能用云市场上面的，所以会存在一定的安全风险。

#### 总结

	虽然稳定、可靠、便捷，但是没有免费额度，也没有 PC 端的软件来管理 OSS 。

# 2. 腾讯对象存储 COS
 
 * 先说优点

 	1. 相较于阿里的 OSS ，腾讯的 COS 每个月是 50 G 的免费存储，还有大量的免费请求次数和流量，参见 [免费额度](https://www.qcloud.com/document/product/436/6240?_ga=1.74556754.1129592029.1537955259) 页面。

 		所以，对于我的个人小博客来说还是很划算的。 并且以后存储容量大了，和阿里云的 OSS 相比，价格上是差不多的。

 	2. 有自己的 PC 端管理软件来管理 COS 。

 	3. 可以使用 QQ 、微信直接登录（也算是一个优点吧）.

* 再来说说缺点

	1. 没有 App 来监控、管理 COS ，更没有手机端的报表来直接体现 COS 的具体使用情况。

	2. 会有一些 Bug ：

		 2.1) 自定义域名，图片一般默认的域名是 https://XX.XXX.com/xxx/xxx.jpg 之类的，这个是腾讯自己默认的域名

		 我想改成 https://image.baichaohua.com/2018/123.png 这种自己的域名。
 	  
 	  	虽然有设置域名的地方，但是我发现它这个设置有时候会出现设置了也无效的问题（域名已经添加记录），需要删除添加的自定义域名，然后重新添加。

 		2.2) 还有一个问题就是 图片使用 https 的协议在某些浏览器可能无法显示的问题，所以最好使用 http 。

 		2.3) 然后就是 和阿里相反，腾讯有自己的 COS 客户端， MAC 和 Windows 都有，但是却没有手机客户端来管理云产品。 这对于手机上传就很不友好了，解决办法就是根据官方的 API 文档，自己开发一款简单的应用来使用了。

#### 总结
	
	有一些 Bug 和不友好的点，但是胜在有免费额度，能用、没什么大问题。




# 综上

 我最终选择了腾讯云的 COS ，原因是：

 1. 每个月有完全够我用的 [免费额度](https://www.qcloud.com/document/product/436/6240?_ga=1.74556754.1129592029.1537955259) ，以后容量上去了，价格和阿里差不多。

 2. 虽然使用 `https` 协议好一些，但是个人的小博客，估计看到的人也不多，权当是自己的一片小空间，`http` 也就可以了。

 3. 有 Bug 相信也会慢慢改进的，体验不友好的地方也会慢慢改进的。长久看下来，还是值得用的。
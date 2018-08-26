---
title: 使用CDN（Content Delivery Network）加速站点访问速度汇总指北
permalink: 使用CDN（Content Delivery Network）加速站点访问速度汇总指北
date: 2018-08-24 10:39:27
tags:
  CDN
---

关于使用CDN（Content Delivery Network）加速站点访问速度汇总指北，总结自己关于自己对CDN以及网络传输的理解。

<!-- more -->

![Alt text](https://s1.ax1x.com/2018/08/25/PHDOeg.png)

> * 1.关于网址，IP
> * 2.关于CDN
> * 3.缓存的两种方式
> * 4.如何使用CDN加速（[又拍云](https://console.upyun.com/register/?invite=HkvfEBqUX)，[阿里云](https://www.aliyun.com)等）
> * 5.完

### 关于网址，IP？

网址，顾名思义就是互联网上的一个地址，如<span>http://www.baidu.com</span>等。当用户在互联网上访问一个网页时，实际上用户访问的是一个服务器，阿里云等。但是服务器是没有网址的，它有另一个名字，叫IP，所以网址和IP对应起来，用户就可以通过网址或IP访问我们的是服务器（互联网），这里就需要另一个东西，DNS解析。负责把网址和IP对应起来，一般可以通过域名服务商设置。

### 关于CDN

上面说了DNS解析，DNS解析就是把网址解析到对应的IP地址上，CDN就是在DNS解析过程中做手脚，cdn全称是内容分发网络。其目的是让用户能够更快速的得到请求的数据。简单来讲，cdn就是用来加速的，他能让用户就近访问数据，这样就更更快的获取到需要的数据。举个例子，现在服务器在北京，深圳的用户想要获取服务器上的数据就需要跨越一个很远的距离，这显然就比北京的用户访问北京的服务器速度要慢。但是现在我们在深圳建立一个cdn服务器，上面缓存住一些数据，深圳用户访问时先访问这个cdn服务器，如果服务器上有用户请求的数据就可以直接返回，这样速度就大大的提升了。

### 缓存的两种方式

cdn中缓存了服务器上的部分资源。那么服务器怎么去更新cdn节点的缓存呢？这里有两种方式，一种是服务器主动去更新缓存，cdn节点被动接受。另一种方式是当用户请求的资源不存在时，cdn服务器向上游服务器发起请求，更新缓存，然后将数据返回给用户，这种方式是cdn服务器主动，源站服务器被动。显然第一种方式存在很多问题，例如很容易产生404等，所以一般采用第二种缓存方式。

![Alt text](https://s1.ax1x.com/2018/08/25/PHrQOO.png)

### 如何使用CDN加速（[又拍云](https://console.upyun.com/register/?invite=HkvfEBqUX)，[阿里云](https://www.aliyun.com)等）

  ---

  <p>

  以[又拍云](https://console.upyun.com/register/?invite=HkvfEBqUX)为例，个人感觉[又拍云](https://console.upyun.com/register/?invite=HkvfEBqUX)比较好用，设置修改实时生效，融合http和https比较适合新人站长，比如我！！！但是貌似没有免费额度，个人权衡吧。

  **Ⅰ. 首先添加加速域名，支持泛域名，如图**

  注意：回源地址填写资源服务器IP地址或网址，网址不能与加速域名相同，回源地址就是需要被动访问缓存的的资源地址，CDN缓存资源的地址。

  ![img](https://s1.ax1x.com/2018/08/25/PHswCR.png)

  **Ⅱ. 选择需要在那些地方进行CDN的加速缓存**

  一般分为全球加速和国内加速。

  ![img](https://s1.ax1x.com/2018/08/25/PHsa59.png)

  **Ⅲ. 点击创建完成**

  然后在域名服务商处添加一个域名解析，如下图,记录类型为CNAME；主机记录处填子域名（比如需要添加 xxxxx.example.com 的解析，只需要在主机记录处填写 xxxxx 即可;如果添加主域名 example.com 的解析，在主机记录处填写 @）；	记录值填写CDN服务商提供的cname值；其他默认就可以。

  ![img](https://s1.ax1x.com/2018/08/25/PH687F.png)

  </p>

  ---

### 完

如有不懂的朋友可以在下面留言。由于本站使用的是日本服务器，本站点正在使用又拍云CDN服务，话说[又拍云](https://console.upyun.com/register/?invite=HkvfEBqUX)能不能打赏一点小费啊！！！期待嘤嘤嘤！！！

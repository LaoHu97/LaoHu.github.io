---
title: 关于微信小程序button按钮组件去掉默认边框
date: 2018-08-27 16:32:11
tags:

	小程序
---

**关于微信小程序button按钮组件使用如下CSS样式覆盖默认样式无效：**

{% codeblock %}
  border: none;
{% endcodeblock %}

<!-- more -->

**给微信小程序button按钮组件添加如下CSS代码：**

{% codeblock %}
	button[type=primary]::after {
	  border: 0;
	}
{% endcodeblock %}

**原因：为什么要使用:after和:before来写button按钮的边框**

可能是因为:after和:before具有更强的扩展性，具体原因还望大神告知，万分感谢！！！ 


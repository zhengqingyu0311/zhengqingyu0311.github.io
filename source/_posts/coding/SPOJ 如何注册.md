---
title: SPOJ 如何注册
password: b7618131f0aeda5b0ca9b7a179750089424ffbb775d7ad2ee160710a208aef9a
mathjax: true
categories: 编程
tags:
  - 编程
  - C++
  - 算法
  - SPOJ
abbrlink: 14154
date: 2022-09-17 13:09:09
---
## 如何注册 SPOJ？

这篇文章将会带你解决 SPOJ 注册时，报错 `wrong or unfilled captcha`   的问题，同时它也是一个 SPOJ 注册的小教程。如果你觉得它为你带来了帮助，请将它分享给他人。


刚注册的时候，会出现这个页面：
![错误页面](https://img-blog.csdnimg.cn/34cc14fd82d340408dea9e5aebf59da8.png)
大家尽量按照下面的操作处理，它们不会花费你超过 $3$ 分钟的时间。实在不行再去找别的大佬帮忙注册。

## 注册流程

1. 在你的浏览器中安装插件 。

   **对于 Google 用户**：[请在插件的 release 页安装](https://github.com/jiacai2050/gooreplacer/releases)。您应该点击 **页面最底部的** Assets 展开，然后下载 ``chrome_gooreplacer_1574507740.zip``，将其解压。下载完成后，在 ``chrome://extensions/`` 处，勾选顶部的“开发者模式”，选择“加载已解压的拓展程序”，选择解压好的文件夹加载拓展程序。

   **对于 Firefox 用户（不区分国内版 / 国际版）**：[这里是 Firefox 最新版官方安装链接](https://download-ssl.firefox.com.cn/releases-sha2/full/102.0/zh-CN/Firefox-full-latest-win64.exe)。Firefox 下载完成后，请点击 [这里](https://addons.mozilla.org/zh-CN/firefox/addon/gooreplacer/) 下载 Gooreplacer。
   
   请不用担心，这个插件对于你平常的使用不会带来任何影响。你也可以在注册完成后立即删除这个插件。

1. 设置该插件。

   下载完成后，点击浏览器顶栏中橙色小刷子的图标，接下来会弹出一个页面 **（如果您下载的版本足够新，请先点击橙色小刷子，再在弹出的窗口中点击最上方的蓝色按钮『配置规则』）**。点击页面中表格上方的“新增”，在弹出的窗口内依次输入 `www.google.com/recaptcha`，“通配符”，`recaptcha.net/recaptcha`，点击“提交”。
   
   ![](https://img-blog.csdnimg.cn/img_convert/7cea2a7ca35ba958385ff9eb542133f3.png)
   
   ![](https://img-blog.csdnimg.cn/img_convert/2a8db481f4d74bee76c7f0de3fd17fba.png)
   
1. 访问 [SPOJ](https://www.spoj.com/)，然后点击正中央的 ``Sign up &  Starting coding`` 进入注册页面，[直接访问](https://www.spoj.com/register/)

   ![](https://img-blog.csdnimg.cn/img_convert/cd818bcef72b668a071c5b75ffcbbbc5.png)

   接下来，点击`I'm not a robot`，待绿色钩钩显示后点击`Create account`成注册。
   
   ![](https://img-blog.csdnimg.cn/img_convert/5b262dc8c3a518de4dfdd002ddd6888f.png)

## 原因

SPOJ 为了防止有人使用机器恶意注册大量无意义账号，采用了 Recaptcha。而 Recaptcha 是 Google 负责搞的。而国内不通过某些手段，明显是上不了 Google 的，这里我们帮助同学们使用了一个国内可以访问的、类似于 Google Recaptcha 镜像网站的 `recaptcha.net`，以 Gooreplacer 为访问媒介。所以这种方法只能解决 Recaptcha 无法访问的问题。

这种处理方法是完完全全的合法行为，请同学们放心。



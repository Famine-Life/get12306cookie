# 获取12306cookie值的油猴脚本

一键安装地址：
[地址](https://greasyfork.org/zh-CN/scripts/419934-%E8%8E%B7%E5%8F%9612306cookie%E5%80%BC)

## 目标
我们的目的是方便、快速的获取到抢票需要的cookie值，例如
```
【=========获取到tk========】
【tk】:
0rrsdzeFYUp8N2HY_VXr62ZJgrTA3kyMy0L1L0
【RAIL_EXPIRATION】:
1610437890585
【RAIL_DEVICEID】:
WqYpoZ06tGPYW8yXwricrBBxanfPSIZss0eJdPPOqykfExmVuWE5BSUkd8yE6JSoUdIUrvIQQZOfatcIuuVVf3MDuPbZxf4Tb1tO30UWulOMEyqzmQ9VumuY3o5GJ6U61UbYOhj0emsCGSW7NsamYex-RlR2gSQ3
```
效果如图：
![12306cookie](/images/12306.png)

## 油猴脚本是什么？怎么用？
请参考我的博文：
https://www.cnblogs.com/famine/p/10090022.html

**如果你对油猴很了解了~ 那么：**
去`YH_123-6.md` 文件，复制粘贴，就完事了。

![yh_12306](/images/yh.png)



# 关于里面有个上传服务器的按钮，这是为了docker用户而加的

我的设想是，点击按钮上传最新的tk值（如果要切换抢票人还要上传其他信息），覆盖到项目的`TickerConfig.py`文件中，然后 `docker-compose up --build -d` 重启项目，就完成了**抢票的重启~**或者**抢票人的切换**.

**这需要:**
  - 一个后台接收tk值等信息的程序，并且能更新信息到 `TickerConfig.py` 文件中。当然同时能重启 docker 抢票项目最好。
  - 该接收信息的程序必须跑在https的地址上，所以~ 我们需要一个备案了的服务器 :(  在哭了。。。555
  - 完成该程序不是很难。。。但是目前没有备案的域名在手上，所以就算写出来了。也没法测试  gg
  - 先这样吧。


## 日志

 - 2021.01.12 发布V0.2
   新增功能：点击按钮即可发送cookie值到服务器（根据接收程序）。已发布接收程序 [地址](https://github.com/Famine-Life/get12306cookieByJava)

 - 2021.01.13 新增功能：登录12306后，点击按钮，一键启动linux服务器上的抢票程序。
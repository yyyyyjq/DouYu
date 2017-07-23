# DouYu
斗鱼小程序模仿之路
第一弹-----用不了dom选择器如何实现登录弹窗效果


接触微信小程序也就几天时间，感觉很有意思，我也是个小白。
下面就分享一个在填坑路上的小小经验，让和我一样正在学习的朋友们避免踩坑。
![image](https://github.com/yyyyyjq/DouYu/raw/master/images/wxml.png)
![image](https://github.com/yyyyyjq/DouYu/raw/master/images/登录界面.png)

这里是wxml文件，注意class为landing和toplanding的两个view，后面都添加了样式，
分别为opacity和display。

这两个样式是什么意思呢？

![image](https://github.com/yyyyyjq/DouYu/raw/master/images/js.png)

我们来看js文件，data里面分别是opacity为1，display为none。

opacity：1，意思就是透明度为1，换句话说就是你可以直接看见的，
它是不透明的，也就是我们第一眼看见的登录界面。

display："none"，通俗来讲，就是可以当作包含这个样式的东西是不存在的，
也就是我们点击登录之后看到的界面，你第一时间是看不见的，只有点击了登录这个按钮才能看到。

之前我就在想，没有dom怎么才能动态添加类名来改变样式，从而实现点击登录的效果呢？
后来我就想出了这个办法，感觉连mask层都省了啊！

就是通过改变landing和toplanding的“存在感”来实现。
一开始登录界面landing的存在感是满满的，而此时toplanding的display为none，是不存在的，你只能看见landing。

这时候给点击登录绑定一个点击事件bindtap：tablanding，在js里面定义，点击登录以后改变opacity和display的状态。
点击登录以后，opacity的值改为0，display为“flex”。

这个时候登录界面landing的透明度就变成了0，也就是完全透明，看不见了。
但是toplanding的display状态改了，这玩意就变成了存在感满满的输入账号密码的界面了。
也就实现了一个简洁的点击登录效果

![image](https://github.com/yyyyyjq/DouYu/raw/master/images/点击登录后.png)



    旅梦开发团学员 易嘉奇 1766883482@qq.com


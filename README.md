# html_css_skill
html css相关经验总结


#html增加QQ即时通信功能

步骤：

首先在QQ商家设置代码中的QQ号码（285457718）为在线状态： 用这个商家QQ（285457718）登录http://shang.qq.com/widget/set.php ，然后花三分钟设置一下就可以了。

在html中加入以下代码： [html] view plain copy 
并给这个a标签加上css样式（样式请自己更改）： [html] view plain copy .qqzixun{
width: 30px;
height: 100px;
background-color: #15b1ea;
position: fixed;
right: 0px;
bottom: 200px;
}

保存之后，在网页中点击这个类名为qqzixun的a标签，选择自己咨询要用的qq号码登录就可以咨询刚才设置好的那个285457718的商家QQ号啦。

# 弹窗剧中对其的方法 需求：要求一个div元素上下左右剧中对其
html:
  <div class='test'></div>
css:
    .test {
      width:200px;
      height: 200px;
      margin: auto auto;
      background: red;
      position: absolute;
      top: 50%;
      left: 50%;
      margin-top: -100px;
      margin-left: -100px;
    }

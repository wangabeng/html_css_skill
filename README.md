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
    
 # 如何使用fontawesome字体图标，有两种方法：
方法1 直接使用CDN的CSS文件：<link rel="stylesheet" type="text/css" href="http://cdn.bootcss.com/font-awesome/4.7.0/css/font-awesome.css">

方法2 把CDN的CSS文件下载到本地，并且把字体文件也下载到本地：（推荐）
@font-face {
  font-family: 'FontAwesome';
  src: url('./fonts/fontawesome-webfont.eot');
  src: url('./fonts/fontawesome-webfont.eot') format('embedded-opentype'), url('./fonts/fontawesome-webfont.woff2') format('woff2'), url('../fonts/fontawesome-webfont.woff') format('woff'), url('./fonts/fontawesome-webfont.ttf') format('truetype'), url('./fonts/fontawesome-webfont.svg') format('svg');
  font-weight: normal;
  font-style: normal;
}

例：src: url('./fonts/fontawesome-webfont.eot');此处字体文件放置在本地目录下

方法3 通过CDN 链接JS文件
<!-- 方法3 使用cdn文件 -->
<!-- <script src="https://use.fontawesome.com/cf2248f49c.js"></script> -->
方法3不兼容ie8， 就是ie8及以下会失效。

××webpack中配置font-awesome (此方法可以兼容ie8)
  1 安装依赖
  npm install font-awesome --save
  2 在js文件中引用
  require('node_modules/font-awesome/css/font-awesome.min.css') // 需要在webpack.config.js中配置别名
  如下：
  resolve: {
    alias: {
      node_modules: __dirname + '/node_modules',
      util: __dirname + '/src/util',
      page: __dirname + '/src/page',
      service: __dirname + '/src/service',
      image: __dirname + '/src/image'
    }
  }
  3 在webpack.config.js中添加对字体文件的处理loader 用file-loader即可 
      {
        test: /\.(eot|ttf|woff|woff2)\w*/,
        loader: 'file-loader'
      }

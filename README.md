# 响应式的百度首页  
####写两个页面，一个页面版一个手机版  
####然后用media的设置来进行切换
==========================================
#要点如下：
####1、手机版有一些svg图标需要把它们相应的转换文件下载，放入CSS和HTML所在文件中，然后在CSS中添上如下代码  
  @font-face {
        font-family: 'iconfont';  
        src: url('iconfont.eot');  
        /* IE9*/  
        src: url('iconfont.eot?#iefix') format('embedded-opentype'), /* IE6-IE8 */  
        url('iconfont.woff') format('woff'), /* chrome、firefox */  
        url('iconfont.ttf') format('truetype'), /* chrome、firefox、opera、Safari, Android, iOS 4.2+*/  
        url('iconfont.svg#iconfont') format('svg');  
        /* iOS 4.1- */  
    }  
      
####2、统一设置这些图标可以统一命名成icon-这种类型，于是就可以用 [class^="icon-"] 来统一设置了，比如：  
    [class^="icon-"] {  
        font-family: "iconfont" !important;  
        font-size: 20px;  
        font-style: normal;  
    }  
####3、手机版的关键在于宽要是百分比，总结了一下，应当用盒模型是最恰当的，用一个 display: box;的父容器包裹一些box-flex: x;(x是该子div占父div的多少百分比，根据需要定)的子容器。

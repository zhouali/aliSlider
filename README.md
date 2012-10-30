aliSlider
=========

一、适用平台
    Android、iOS、Chrome、Safari极佳

    【备注】虽然有对其他浏览器进行兼容，但是效果不太理想，因为不同浏览器对CSS3的效果呈现各异，所以建议不要使用这种鼠标
            拖动或者手势touch进行切换
二、如何使用
    1. Html 页面构建：（主体滑动的格式-代码会自动人为container第一个子元素为滑动区域，所以不要在container和scroller直接
       添加多余代码）

          <div class="navs" id="navigator">
              <a href="javascript:void(0)">新闻</a>
              <a href="javascript:void(0)">军事</a>
              <a href="javascript:void(0)">滚动</a>
           </div>
	        <div id="container">
	            <div class="scroller">
	                <!-- 分页具体内容 start-->
	                <div class="mod"></div>
                    <div class="mod"></div>
	                <div class="mod"></div>
	                <!-- 分页具体内容 end-->
	            </div>
	       </div>

    2. 设置 container的宽高（必须）

         <style>
              #container{width:100%;height:200px;}
              .foc{font-weight:bold;}
         </style>

    3. 引入js

	       <script src="aliSlider-v1.0-min.js"></script>

    4. 构建Slider

         var d = document,
             g = 'getElementById',
             navigator = d[g]("navigator"),
             container = d[g]("container");  
	       var newSlider = new Slider(container,{
	                                  navEle : navigator,
	                                  navSelector:"a",
	                                  navSelClass:"foc",
	                                  loopFlag: true
	                      });      
	【注意事项】由于Slider中内容在初始加载时，js并没有加载完毕，建议利用CSS进行初始设置，只显示某一页，其他页进行
                   隐藏，Slider会在JavaScript中加入对所有页面的显示，这也是为了避免网络缓慢的时候出现的布局问题。


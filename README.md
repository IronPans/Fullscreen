# Fullscreen（全屏滚动插件）

fullscreen.js是一个支持全屏滚动的插件，根据鼠标滚轮的滚动去切换不同的页面。

##用法：
引入css：  
`<link rel="stylesheet" href="../dist/fullscreen.css" />`

引入js：  
`<script src="../dist/fullscreen.js"></script>`

页面：
```
<div class="fullscreen-container">
			<div class="fullscreen-wrapper">
				<div class="fullscreen-slide"></div>
				<div class="fullscreen-slide"></div>
				<div class="fullscreen-slide"></div>
				<div class="fullscreen-slide"></div>
			</div>
		</div>
```

###初始化
`var nf = new NFullscreen(".fullscreen-container", {});`

###可选参数
pagination: true  是否显示分页器  
paginationClickable:true   分页器是否可点击控制页面滚动  
init:funciton(fullscreen){}  初始化回调函数  
pageChangeEnd:function(fullscreen){}  回调函数：页面滚动结束时执行  

###属性
fullscreen.activeIndex  返回当前页面的索引，从0开始


###简单例子
```
var slides=document.querySelectorAll(".fullscreen-slide");
			function show1() {
				slides[0].style.background='red';
			};

			function show2() {
				slides[1].style.background='green';
			}

			function show3() {
				slides[2].style.background='blue';
			}

			function show4() {
				slides[3].style.background='purple';
			}
			var nf = new NFullscreen(".fullscreen-container", {
				pagination: true,
				init:function(fullscreen){
					show1();
				},
				pageChangeEnd: function(fullscreen) {
					var index = fullscreen.activeIndex;
					eval('show' + (index + 1) + '()');
				},
				paginationClickable:true
			});
	```
	
后期继续完善...

# swiper-demo
swiper 页面开发模版，基本在需要注意的地方都做了注释备注了，拿到手上只要稍微对着注释更改相应内容即可。

swiper开发模版，主要用于H5页面展示类，模版都套好了，加了一些逻辑的东西，只需要在对应页面填内容和样式即可。
添加的部分有：

  结构：
      <!-- 如果有上滑箭头或者需要fix定位的内容，内容填在这里 -->
			<div class="tonext"></div> 
      
      预载
				<div class="swiper-slide page0" >
					<!-- 预加载百分比 -->
					<span>此处加载进度百分比</span>
				</div>
       <!-- 分页器 -->
				<div class="swiper-pagination"></div>
  样式:
    1.设置统一背景色 ，如果有需要 */
    .allPage {
      background: ;
    }
    2.预载页面样式设置
    3.下拉方向箭头样式
  行为js：
    1.主程序初始化：
    autoplay: 5000,//可选选项，自动滑动
		pagination: '.swiper-pagination',  // 是否出现分页器
        paginationClickable: true,			// 是否点击分页器跳转
        paginationType : 'fraction',       // 分页器类型，bullets 圆点 fraction 分数式 progress 进度条custom 自定义
		direction: 'vertical', // 不写的话默认横向
		mousewheelControl : true,  // 增加滚轮控制
		keyboardControl : true,  // 键盘控制
		onSlideChangeEnd: function(swiper) {
			swiperAnimate(swiper); //每个slide切换结束时也运行当前slide动画
			if(swiper.activeIndex == 1) {
				mySwiper.lockSwipeToPrev(); // 禁止上滑倒加载页
				mySwiper.unlockSwipeToPrev(); // 解锁上滑
				page1_ani(); // 执行第一页动画程序
			} else if(swiper.activeIndex == 2) {
				page2_ani(); // 执行第二页动画
			} else if(swiper.activeIndex == 3) {
				page3_ani(); // 执行第三页动画
			} else if(swiper.activeIndex == 4) {
				page4_ani(); // 执行第四页动画
				mySwiper.unlockSwipeToNext(); // 解锁上滑
			} else if(swiper.activeIndex == 5) {
				mySwiper.lockSwipeToNext(); // 禁止下滑
			}
		}
    2.图片预载设置
    3.向下箭头初始化设置
    
    
    
    
    

使用swiper 轮播插件ajax 请求加载图片时，无法滑动问题

因为banner图是动态创建的，在插件开始初始化时，文档流中没用图片，故没有创建相应宽度，通过调整js加载顺序，问题还是没有解决。最后找到swiper插件 api 有属性是可以根据内容变动，自动初始化插件的，添加observer：true后问题解决！

var mySwiper = new Swiper ('.swiper-container', {
        pagination: '.swiper-pagination',
        autoplay: 5000,
        loop: true,
        observer:true,//修改swiper自己或子元素时，自动初始化swiper
    	observeParents:true,//修改swiper的父元素时，自动初始化swiper
 }) 	



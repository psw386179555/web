

[swiper](http://www.swiper.com.cn/ "swiper官网")

```
<section class="pc-banner">
    <div class="swiper-container">
        <div class="swiper-wrapper">
            <div class="swiper-slide swiper-slide-center none-effect"><a href="#"><img src="images/top_hero_conc_2017.jpg" ></a></div>
            <div class="swiper-slide"><a href="#"><img src="images/top_hero_cs_2017.jpg" ></a></div>
            <div class="swiper-slide"><a href="#"><img src="images/top_hero_cw_im17.jpg" ></a></div>
            <div class="swiper-slide"><a href="#"><img src="images/top_hero_hakko.jpg" ></a></div>
            <div class="swiper-slide"><a href="#"><img src="images/top_hero_karadacalpis_im02.jpg" ></a></div>
        </div>
    </div>
    <div class="swiper-pagination"></div>

    <div class="button">
        <div class="swiper-button-prev"></div>
        <div class="swiper-button-next"></div>
    </div>

</section>
```

引入swiper.min.js和swiper.min.css

```js
 <script>
	window.onload = function() {
    var swiper = new Swiper('.swiper-container',{
		autoplay:3000,
		speed:1000,
		autoplayDisableOnInteraction : false,
		loop:true,
		centeredSlides : true,
		slidesPerView:2,
        pagination : '.swiper-pagination',
		paginationClickable:true,
		prevButton:'.swiper-button-prev',
        nextButton:'.swiper-button-next',
		onInit:function(swiper){
			swiper.slides[2].className="swiper-slide swiper-slide-active";//第一次打开不要动画
			},
        breakpoints: { 
                668: {
                    slidesPerView: 1,
                 }
            }
		});
		};
    </script>
```




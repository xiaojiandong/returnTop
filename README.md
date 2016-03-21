# returnTop
回到顶部


# 方法1，窗口滚动
    $(function(){
       var returnTopObj = $('.js_return_top');
       var DEVICE_HEIGHT = $(window).height(); // 窗口高度
       $('.js_first_page').css({'height' : DEVICE_HEIGHT + 'px' , 'background-color' : 'pink'});

       // 绑定窗口滚动事件
       $(window).on('scroll' , function(){
         var currentScrollTop  = $(window).scrollTop();
         if( currentScrollTop > DEVICE_HEIGHT ){
             returnTopObj.show();
             returnTopObj.on('click' , function(){
                 returnTop(currentScrollTop)
             });
         }else{
             returnTopObj.hide();
         }
       });
      } 


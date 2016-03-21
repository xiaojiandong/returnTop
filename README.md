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
# 窗口2，点击回到顶部
 // 点击返回顶部
    $(function(){
       function returnTop (currentScrollTop){
           var timer = null;
           timer = setInterval(function(){
               currentScrollTop = (currentScrollTop / 1.3 ).toFixed(2); // 设置滚动条缓冲
               if( currentScrollTop < 1 ){
                   currentScrollTop = Math.floor(currentScrollTop); //向下取整，最终为0
               }
               if( currentScrollTop <=0 ){
                   clearInterval(timer);
               }
               $(window).scrollTop( currentScrollTop ); // 重置滚动条高度，返回顶部
           } , 30);
       }
      } 

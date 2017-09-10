# lunbo-jquery
a lunbo-jquery

<!DOCTYPE html>
<html>

	<head>
		<meta charset="UTF-8">

       <title></title> 
      <script src="http://libs.baidu.com/jquery/1.9.1/jquery.min.js"></script>
       <style type="text/css">
       .main { width: 590px; height: 340px; overflow: hidden; position: relative; 
        }

		.box {
			width: 5310px;
			height: 340px;
			font-size: 0px;
			position: absolute;
		}
		
	.main>span	{
		
		display:none;
		}
	
	.main:hover span {
			float: left;
			display: block;
			position: absolute;
			width: 30px;
			height: 60px;
			background-color: rgba(0,0,0,.3);
			top:50%;
			margin-top: -30px;
			line-height: 60px;
			text-align: center;
			font-size:20px ;
			z-index: 22;
		
			
		}
		
		.pre {
			left:0;
		}
		.next {
			 right:0
		}
		#control {
			position: absolute;
			z-index: 2;
			bottom: 30px;
			width: 240px;
			height: 24px;
			left: 50%;
			margin-left: -100px;
			text-align: center;
			line-height: 30px;
			border-radius: 15px;
			background-color: rgba(0, 0, 0, 0.3);
		}
		
		#control a {
			display: inline-block;
			width: 16px;
			height: 16px;
			border-radius: 50%;
			background-color: #fff;
		}
		#control .colors{
			background-color:red ;
			}
		
	</style>
	
	
	
</head>

<body>
	<div class="main">
		
		<div class="box">
		
			<img src="images/1.jpg" alt="" />
			<img src="images/2.jpg" alt="" />
			<img src="images/3.jpg" alt="" />
			<img src="images/4.jpg" alt="" />
			<img src="images/5.jpg" alt="" />
			<img src="images/6.jpg" alt="" />
			<img src="images/7.jpg" alt="" />
			<img src="images/8.jpg" alt="" />
			<img src="images/1.jpg" alt="" />
		</div>
		<span class="pre">&lt;</span>
		<span class="next">&gt;</span>
		<div id='control'>
			<a href="javascript:void(0);" class="colors"></a>
			<a href="javascript:void(0);"></a>
			<a href="javascript:void(0);"></a>
			<a href="javascript:void(0);"></a>
			<a href="javascript:void(0);"></a>
			<a href="javascript:void(0);"></a>
			<a href="javascript:void(0);"></a>
			<a href="javascript:void(0);"></a>
		</div>
	</div>
	
	
	<script type="text/javascript">
		var i=0;
		var time;
		$("doument").ready(function(){
			time=setInterval(move,2000)
			
		});
		
		function move(){
				i++;
				if(i>8){
					i=1;					
				}
				if(i<0){
					i=7;
				$(".box").css('left','-4720px');	
				}
				
				$(".box").stop().animate({
				 left:-590*i
				 },500, function(){
				 	if(i==8){
				 		$(".box").css('left','0');
				 		
				 	}
				 	
				 });
				 
				 
				 
				 var t=i;
				 if(t>7){
				 	
				 	t=0;
				 }
				 $('#control a').eq(t).addClass('colors').siblings().removeClass('colors');
			}
		
			$('.main').hover(function(){
			
					clearInterval(time)
			},function(){
				 time=setInterval(move,2000)
		    });
			
		   $(".pre").click(function(){
		   	i-=2;
		   	move(); 	
		   });
		   var lock=true;
		    $(".next").click(function(){
		    	if(lock){
		    	move();
		    	lock=false;
		    	
		    	setTimeout(function(){
		    		lock=true;
		    	},500)
		    	
		    	}
		       
		    });
				
		
			 $('#control a').click(function(){
           $(this).addClass('colors').siblings().removeClass('colors') 
	        i=$(this).index()-1; 
	           move();
			
				}); 
		
		
	</script>
	
</body>
</html>

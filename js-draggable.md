##　使用原生JS实现拖拽

````
<!DOCTYPE html PUBLIC "-//W3C//DTD HTML 4.01//EN"
"http://www.w3.org/TR/html4/strict.dtd">

<html xmlns="http://www.w3.org/1999/xhtml" lang="en">
	<head>
		<meta http-equiv="Content-Type" content="text/html; charset=utf-8" />
		<title>原生js拖拽效果</title>
		<style type="text/css">
			*{ margin:0; padding:0;}
			#box{ position:absolute; left:0; top:0; width:100px; height:100px; background:#f60;}
		</style>
	</head>
	<body>
		<div id="box"></div>
		<script type="text/javascript">
			var oBox = document.getElementById('box');
			oBox.onmousedown = function(e){ //当鼠标位于框内时执行onmousedown函数，即可拖拽
				var oEvent =e || window.event,
					disL = oEvent.clientX - oBox.offsetLeft, //获得当前鼠标距离左边框的长度
					disT = oEvent.clientY - oBox.offsetTop, //获得当前鼠标距离上边框的长度
					maxL = document.documentElement.clientWidth - oBox.offsetWidth, // 水平最大偏移量
					maxT = document.documentElement.clientHeight - oBox.offsetHeight; // 垂直最大偏移量
				document.onmousemove = function(e){ // 当鼠标位于框内且发生移动时，执行onmousemove函数
					var oEvent = e || window.event,
						disX = oEvent.clientX - disL, //获得水平位置上的偏移量
						disY = oEvent.clientY - disT; //获得垂直位置上的偏移量
						//console.log(disX);
					if(disX <=0){ disX =0}
					if(disY <=0){ disY =0}
					if(disX >=maxL){ disX =maxL}
					if(disY >=maxT){ disY =maxT}
					oBox.style.left = disX+'px'; //设置此时的框的属性
					oBox.style.top = disY+'px';
				}
			}
			document.onmouseup=function(){
			document.onmousemove=null; // 当mouseup时，不执行onmousemove函数
		}
		</script>
	</body>
</html>
````

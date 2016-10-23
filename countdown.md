## 实现倒计时的小功能

````
<!DOCTYPE html>
<html>
<head>
	<title>demo</title>
	<meta charset="utf-8">
	<style type="text/css">
		*{
			font-size: 60px;
		}
		input{
			display: inline-block;
			width: 200px;
			height: 100px;
			line-height: 100px;
			text-align: center;
			border: none;
		}
	</style>
</head>
<body>
倒计时：<input type="text" id="input1" placeholder="min" value="59" onblur="getvalue()"> : <input type="text" id="input2" placeholder="sec" value="59">
<button id="btn1">start</button><button id="btn2" disabled="true">stop</button>
<div id="parent"></div>
</body>
<script type="text/javascript">
var input1 = document.getElementById('input1');
var input2 = document.getElementById('input2');
var btn1 = document.getElementById('btn1');
var btn2 = document.getElementById('btn2');
var min,sec;
function getvalue(){
	min = input1.value;
	sec = input2.value;
	btn1.disabled = false;
	if(parseInt(sec)==0&&parseInt(min)==0){
		btn1.disabled = true;
	};
};
btn1.onclick = function(){
	min = input1.value;
	sec = input2.value;
	btn1.disabled = true;
	btn2.disabled = false;
	// if(parseInt(sec)==0&&parseInt(min)==0){
	// 	btn1.disabled = true;
	// };
	// var f = function(sec,min){//sec--second,j--minutes
		var time = setInterval(function(){
				if(parseInt(sec)>=0&&parseInt(min)>=0){
					if(sec == 0){
					sec = 60;
					min--;
				};
				sec--;
				if(sec.toString().length == 1){
					input2.value = "0"+sec;
				}else{
					input2.value = sec;
				};
				if(min.toString().length == 1){
					input1.value = "0"+min;
				}else{
					input1.value = min;
				};
				if(sec==0&&min==0){
					alert('DONE!!');
					input2.value = 59; input1.value = 59;
					btn1.disabled = false;
					clearInterval(time);
					btn2.disabled = true;
				};
			};
			btn2.onclick = function(){
				clearInterval(time);
				btn1.disabled = false;
			}
		},1000);
	// };
	// f(sec,min);
};
</script>
</html>
````

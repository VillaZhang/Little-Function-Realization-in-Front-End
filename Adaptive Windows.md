# Adaptive windows
## Adaptive center part with fixed left side and fixed right side
````
<!DOCTYPE html>
<html>
<head>
	<title>demo</title>
</head>
<style type="text/css">
	*{
		padding: 0;
		margin: 0;
	}
	body{
		width: 100%;
	}
	.content{
		/*width: 100%;*/
		max-height: 400px;
		background: yellow;
		padding:20px;
		margin: 20px;
		/*float: left;*/
	}
	.border{
		/*border: 1px solid #999;*/
	}
	.class1{
		width: 100px;
		height: 150px;
		/*margin-left: 20px;*/
		background: green;
		float: left;
	}
	.class2{
		background: red;
		margin: 0px 120px 20px 120px;
		/*margin-bottom: 20px;*/
		height: 300px;
	}
	.class3{
		width: 100px;
		float: right;
		margin-top: -320px;
		background: black;
		height: 320px;
		margin-bottom: 20px;
	}
</style>
<body>
<div class="content">
	<div class="class1 border"></div>
	<div class="class2 border"></div>
	<div class="class3 border"></div>
</div>
</body>
</html>
````

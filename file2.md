```html

<!DOCTYPE html>
<html>

	<head>
	
	
		<style>
		
		
			.kotak-orange{
			
			
				background: orange;
				
				height: 100px;
				
				width: 100px;
			
			
			
			}
			
			
			
			.kotak-biru{
			
			
				background: lightskyblue;
				
				height: 100px;
				
				width: 100px;
			
			
			}
			
			
			
			.kotak-hitam{
			
			
				background: #000000;
				
				height: 100px;
				
				width: 100px;
			
			
			}
		
		
		
		
		
		</style>
	
	
	
	
	</head>
	
	
	<body>
	
	
		<div class="kotak-orange"></div>
		
		<div class="kotak-biru"></div>
		
		<div class="kotak-hitam"></div>
	
	
	
	
	
	</body>



</html>



```

source code di atas menunjukan cara bagaimana mengatur posisi elemen dengan menggunakan CSS. Di bawah ini adalah pengembangan dari source code di atas:

```html

<!DOCTYPE html>
<html>

	<head>
	
	
		<title>CSS 2</title>
		
		<style>
		
		
			.kotak-orange{
			
				position: relative;
			
				background: orange;
				
				height: 100px;
				
				width: 100px;
				
				top: 100px;
				
				left: 100px;
			
			
			
			}
			
			
			.kotak-biru{
			
				background: lightskyblue;
				
				height: 100px;
				
				width: 100px;
			
			
			}
			
			
			.kotak-hitam{
			
				position: relative;
			
				background: #000000;
				
				height: 100px;
				
				width: 100px;
				
				bottom: 100px;
				
				left: 200px;
			
			}
		
		
		
		</style>
	
	
	</head>
	
	
	<body>
	
	
		<div class="kotak-orange"></div>
		
		<div class="kotak-biru"></div>
		
		<div class="kotak-hitam"></div>
	
	
	
	
	
	</body>





</html>


```

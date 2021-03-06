ajaxPageSystem
====================



---


## Button Syntax

```html

	<button class="pageBtn" data-page="seite2" data-task="">Open Page 2</button>
	
	<div class="pageBtn" data-page="seite2" data-task="myFunc">Open Page 2 with task</button>
	
	<a class="pageBtn" data-page="seite2" data-task="myFunc" data-content="myData">Open Page 2 with task and content</button>

```
---

The class 'pageBtn' is a mandatory disclosure.

To change the page, you must specify the data-page attribute.<br /> 
To perform a task, add the data-task attribute.<br /> 
You can also combine them.

<br /> <br /> 

---

# Usage

```html
	
	<head>
		<style>	
			.page {
				display: none;
			}
		</style>
	</head
	<body>
		
		<div class="" id="page">loading...</div>
		
		<script src="js/ajaxPageSystem.min.js"></script>
		<script src="js/ajaxPageSystem-tasks.js"></script>
		
		<script>
			window.onload = function() {
				APS.page.initialize({
					start: 'seite1',
					handler: 'pageBtn',
					container: 'page'
				});
			};
		</script>
		
	</body>
```

<br /> 
---

<br /> <br /> 

## Initialize Options

* #### start

	@require: true<br /> 
	@type: string
	
	your start page id
	
	###### Example:
	```javascript
	{
		start: 'seite1'
	}
	```



* #### handler

	@require: true<br /> 
	@type: string<br /> 
	@default: 'pageBtn'
	
	the button class
	
	###### Example:
	```javascript
	{
		handler: 'pageBtn'
	}
	```
	
* #### container

	@require: true<br /> 
	@type: string<br /> 
	@default: 'page'
	
	the master container for all templates

	###### Example:
	```javascript
	{
		container: 'page'
	}
	```

	
* #### mockupDebug

	@require: false<br /> 
	@type: boolean<br /> 
	@default: false
	
	if set to true shows the hidden mockup buttons

	###### Example:
	```javascript
	{
		mockupDebug: true
	}
	```
	
* #### mockup

	@require: false<br /> 
	@type: string<br /> 
	@default: {}
	
	
	all values are set with the css units vw and vh !
	
	x, y, width, heigth -> are required
	
	page, task and comments -> are used as explained above
	
	title -> the button text, only display if set mockupDebug: true
	
	###### Example:

	```html
		
	
		<script>
			window.onload = function() {
				APS.page.initialize({
					start: 'seite1',
					handler: 'pageBtn',
					container: 'page',
					mockupDebug: true,
					mockup: {
						'page_1': [
							{
								x: 50,
								y: 50,
								width: 30,
								height: 5,
								page: 'seite2',
								task: 'myFunc',
								content: 'myData',
								title: 'Goto Page 2'
							},
							{
								x: 50,
								y: 60,
								width: 30,
								height: 5,
								page: 'seite3'
							}
						],
						'page_2': [
							{
								x: 60,
								y: 20,
								width: 10,
								height: 5,
								page: 'seite3',
								title: 'Goto Page 3'
							}
						]
					}
				});
			};
		</script>
	
	```



---





# Task Example


```js
	myFunc: function (page, content, e) {
		
		// paste your code here...
		
		console.log('myFunc !','page:',page,'content:',content,'e:',e);
		
		return true; // if false or missing, the page will not change!
	}
```		

To define your own function, edit the onPageSystem-tasks file.<br /> 
You can add new functions comma seperated.<br /> 
The name of you function is the data-task attribute you have to set.<br /> 
In this Example it is data-task"myFunc"<br /> 

You can add a data-content="" attribute to the button elements.<br /> 
After clicking the button you will have the content in your task function.

<br /> <br /> 
---
---




	
		
### Autor

Christian Marienfeld

www.chrisland.de


### Licence

Licence MIT

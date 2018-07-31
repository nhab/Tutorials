Is a bookmark in the web browser that contains JavaScript commands that add new features to the browser. 

### concept
The executing script has access to the current page, which it may inspect and change.

If the script returns an undefined type (rather than, for example, a string), 

the browser will not load a new page,

with the result that the script simply runs against the current page content. 

This permits changes such as in-place font size and color changes without a page reload.

An anonymous function that does not return a value, define a function, etc., 
can be used to force the script to return an undefined type:
```javascript
	javascript:(function(){
		//Statements returning a non-undefined type, e.g. assignments
	})();
```

```javascript
	//Example: to change font of the current page
	javascript:(
	  function(){
	  document.getElementsByTagName('body')[0].style.setProperty('font-family',%20'serif',%20'important');
	  }
	)();
```
				
 Resources :
 
	tones of it http://marklets.com/
	
	Steve Kangas of http://bookmarklets.com
	
	Tantek Çelik called these scripts favelets
							

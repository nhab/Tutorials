## Headers : 
 # &nbsp;&nbsp; This is an < h1 > tag    `# This is an < h1 > tag  ` 
 ### &nbsp;&nbsp; This is an < h2 > tag   `### This is an < h2 > tag ` 
 ###### &nbsp;&nbsp; This is an < h6 > tag   `###### This is an < h6 > tag` 
### &nbsp;&nbsp; New Line (ENTER)
 &nbsp;&nbsp; hit <Enter> 3 times after line 

&nbsp;&nbsp; this is the next line

## Emphasis
   &nbsp;&nbsp; *Mark down renders HTML tags either*    ` *Mark down renders HTML tags either* ` 
   
   &nbsp;&nbsp; _Mark down renders HTML tags either_   `_Mark down renders HTML tags either_`

   &nbsp;&nbsp; **Mark down renders HTML tags either**  `**Mark down renders HTML tags either**` 

   &nbsp;&nbsp; __Mark down renders HTML tags either__  `__Mark down renders HTML tags either__`

  &nbsp;&nbsp; _You **can** combine italic and bold_   `_You **can** combine italic and bold_` 
## Comment
   &nbsp;&nbsp; [comment]: <> (The comment)  `[comment]: <> (The comment)`
   &nbsp;&nbsp;  [//]: <> (also comment.)  `[//]: <> (also a comment.)`
## Unordered List : 
 * Item 1    `* Item 1 `
 * Item 2    `* Item 2`
   * Item 2a `*   Item 2a`
   * Item 2b `*   Item 2a`
## Ordered List : 
 1. Item 1 `1. Item 1`
 1. Item 2 `1. Item 2 `
 1. Item 3 `1. Item 3`
    1. Item 3a `1. Item 3a`
    1. Item 3b `1. Item 3b`
## Images
  ![GitHub Logo](https://avatars0.githubusercontent.com/u/6296819?s=40&v=4) 
  Format: ![Alt Text](url)  `![GitHub Logo](https://avatars0.githubusercontent.com/u/6296819?s=40&v=4) 
  Format: ![Alt Text](url) `
## Links
  http://github.com - automatic! 
 [GitHub](http://github.com)  `http://github.com - automatic! 
 [GitHub](http://github.com)`
## Blockquotes
 As Don Juan Matus said: 
 > a man of knowledge lives by acting, not by thinking about acting,
 > nor by thinking about what he will think when he has finished 
## Inline code
 should use an |<addr>` element 
### Code block
    Indent every line of the block 
    by at least 4 spaces.
	
  Alternatively, you can use 3 backtick quote marks before and after the block, like this:
```
This is a code 
block
```
## javascript syntax highlighting
 ```javascript
function fancyAlert(arg) {
  if(arg) {
    $.facebox({div:'#foo'})
  }
}
```

     ```javascript
    function fancyAlert(arg) {
      if(arg) {
        $.facebox({div:'#foo'})
      }
    }
    ```
    
## Tables
Markdown | Less | Pretty Markdown
--- | :---: | ---:               
*Still* | `renders` | **nicely** 
1 | 2 | 3                       

  `Markdown | Less | Pretty Markdown `
  
  `--- | :---: | ---:`
  
  `*Still* | `renders` | **nicely**`
  
  `1 | 2 | 3`
  
 ## Indentation
  &nbsp;&nbsp; Can be managed by inserting a number of `&nbsp;&nbsp;`
  
  &nbsp;&nbsp;&nbsp;&nbsp; Can be managed by inserting a number of `&nbsp;&nbsp;&nbsp;&nbsp;`
  
  	+ or do tab, then the + sign, then space, then your content
	
		+ another do tab, then the + sign, then space, then your content

## using css
you can define a css without using < Style > tag

`	  . table-of-contents ul {`

`	  list-style-type: none;`

`	}`

`<nav class="table-of-contents">`

`  	this is a normal line of text`
	
`  	* this is the first level of bullet points, made up of <space><space>*<space>`
	
`    		* this is more indented, composed of <space><space><space><space>*<space>`
	
`</nav>`


.table-of-contents ul {
  list-style-type: none;
}
<nav class="table-of-contents">
  this is a normal line of text
	
  * this is the first level of bullet points, made up of <space><space>*<space>
	
    * this is more indented, composed of <space><space><space><space>*<space>
	
</nav>

## Horizontal Rule
	Three or more
	...
	---
	***
	___
## mentioning someone ( @mentions )
	Typing an @ symbol, followed by a username, will notify that person to come
	and view the comment. This is called an “@mention”, because you’re mentioning the individual.
	You can also @mention teams within an organization.

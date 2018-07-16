# Node.js
	  Has a command-line tool that can be run as a regular web server 
	  and lets one run JavaScript programs
				

## nvm
   	Is node version manager
  
	to this version the default one:
	  $ nvm alias default 0.10.31      

## npm 
        :is a package manager for javascript and the Node.js server platform
  
	 -Npm is included in nodejs installs by default.
  
	 -you can search online for your neede package here https://www.npmjs.com/
   
	 :Features
   
		 - local dependencies:
     
		 	It installs application dependencies locally, not globally.
      
		 - multiple versions of the same dependency:
     
	   It handles multiple versions of the same module at the same time.
     
	 	- tarball or git dependencies:
    
			You can specify tarballs or git repositories as dependencies.
      
		- Easy module publishing (to the npm registry).
    
		- Easy creation of CLI utilities that others can install (with npm).
    
## Example of shell scripts in Node.js 		

	-running the first hello world
  
		1.create a file named h.js
    
		2.write this line inside it and save: console.log("Hello World");
    
		3.in command prompt run this command : node h.js
    
		4.finished!this will prints Hello world.
    
	-running a script with arguments
  
		1.put this content inside your script 
    
			process.argv.forEach((val, index) => {
				console.log(`${index}: ${val}`);
			});
      
		2.run your script by proving arguments:
    
			 node h.js one two=three four
       
## Modules (or packages or libraries)

	- are set of libraries for doing real things.
  
	- Node implements the CommonJS interface for modules. 
  
	:proccesses:
  
		-loading depencies (using the require keyword):
			
			For example, we can require some native modules:
      
				var http = require('http');
        
				var dns = require('dns');
        
				We can also require relative files:
        
				var myFile = require('./myFile'); // loads myFile.js
        
		-Installing modules from npm:
    
			either search for them on the website or on Github. 
      
			The syntax for installing an npm module locally :
      
				# where express === module name
        
				$ npm install express
        
		You can require module install from npm as you would do with the native ones, 
    
		no need to specify the absolute or relative path:
    
			var express = require('express');
      
		-Node modules aren`t automatically injected into the global scope
    
		, instead you just assigned them to a variable of your choice. 
    
	   
		That means that you don`t have to care about two or more modules 
    
		that have functions with the same name.

		- creating your own modules
    
			1-
				configure npm
        
				npm set init.author.name "Brent Ertz"
        
				npm set init.author.email "brent.ertz@gmail.com"
        
				npm set init.author.url "http://brentertz.com"
        
				
				npm adduser
			2-
				The primary 2 items that we are concerned with here are require and exports. 
        
				You require other modules that you wish to use in your code 
        
				and your module exports anything that should be exposed publicly.
        
				For example:
        
				var other = require('other_module');
        
				module.exports = function() {
        
						console.log(other.doSomething());
            
				}
        
			3.Executing the following command will ask you a bunch of questions, 
      
			and then write out a package.json file.
      
					npm init
          
			4. Create an index.js file to hold the primary module code.
      
			FOR EXAMPLE:
```javascript
				/**
				* Escape special characters in the given string of html.
				*
				* @param  {String} html
				* @return {String}
				*/
				module.exports = {
				escape: function(html) {
					return String(html)
							.replace(/&/g, '&amp;')
							.replace(/"/g, '&quot;')
							.replace(/'/g, '&#39;')
							.replace(/</g, '&lt;')
							.replace(/>/g, '&gt;');
					},
					/**
					* Unescape special characters in the given string of html.
					*
					* @param  {String} html
					* @return {String}
					*/
					unescape: function(html) {
					return String(html)
							.replace(/&amp;/g, '&')
							.replace(/&quot;/g, '"')
							.replace(/&#39;/g, ''')
							.replace(/&lt;/g, '<')
							.replace(/&gt;/g, '>');
					}
				};
			....
```
      
## callbak

		-you are telling it to do something and when it is done it will call your function 		(callback).
    
		-In asynchronous programming we do not return values when our functions are done,
    
			but instead we use the continuation-passing style (CPS)
      
## Events

	The standard callback pattern works well for the use cases 
  
	where we want to be notified when the async function finishes. 
  
	However, there are situations that require being notified of different events 
  
	that do not occur at the same time.
  
## Streams 

	represent an abstract interface for asynchronously manipulating a continuous flow of data.
  
	They are similar to Unix pipes and can be classified into five types: 
  
		readable
    
		, writable
    
		, transform
    
		, duplex 
    
		and "classic".

##  Reference it:

		<script src="//cdnjs.cloudflare.com/ajax/libs/angular.js/1.4.2/angular.js"></script>
    
##  Installing  Node.js and NPM

	How to install NVM (node version manager) on an Ubuntu system.
  
		1. prerequisite: make sure system has a C++ compiler:
    
		   	$ sudo apt-get update
		  	$ sudo apt-get install build-essential libssl-dev
        
		2. NVM Installation:
    
			   copy-paste the one-line installer for NVM into the terminal:
		   	$ curl https://raw.githubusercontent.com/creationix/nvm/v0.13.1/install.sh | bash

		3. Checking NVM Installation:
			so we will logout and login to verify that:

			$ nvm

			If there's no error when typing in the nvm command, that means that everything's alright.
		4. Now we can move on to actually installing Node and npm.

			$ nvm install v0.10.31
		5.Both node and npm should be available in the terminal now:

			$ node -v &amp;&amp; npm -v
			v0.10.31
			1.4.23

## Install From source
		wget http://nodejs.org/dist/node-v0.4.4.tar.gz
		$ tar -xzf node-v0.4.4.tar.gz
		$ cd node-v0.4.4
		$ ./configure
		$ sudo make install



##  switching between node versions

	$ nvm install v0.8.10
	$ nvm use v0.8.10
	
    - show you the full list of versions and also the current and default versions :

	$ nvm list
	
##  getting the version(in command line):
		node -v
		
##  Hello world Example:
	Writing a node.js program is as simple as creating a new file with a '.js' extension.
	
	For example you could create a simple 'hello_world.js' file with the following content:
	
	console.log('Hello World');

	After you have saved the file, you can execute it from your terminal like so:

	$ node hello.js
	
	Hello World
	
## A hello world http server:

	 program that responds to hello world via http.
	 We'll call the file 'hello_http.js' and put the following code into it:
```javascript
		var http = require('http');

		var server = http.createServer(function(req, res) {
		res.writeHead(200);
		res.end('Hello Http');
		});
		server.listen(8080);
```

	Now lets run this program from the terminal by typing:

		$ node hello_http.js
		
	Testing the server is as simple as opening a new browser tab,
	
	and navigating to the following url: http://localhost:8080/. 
	
	As expected, you should see a response that reads: 'Hello Http'.

	Alternatively, you could also open up a new terminal and use curl to test your server:

	$ curl localhost:8080
	Hello Http

- directory structure
	C:\Program Files\nodejs\node_modules\npm\node_modules
	
## using node commands

	1. with no arguments. 
		This will open an interactive shell 
		where you can execute raw JavaScript code.
			$ node
			> console.log('Hello World');
			Hello World
			undefined
			
	2. by providing it a JavaScript file to execute.
		This is almost always how you will be using it.
			hello.js
			console.log('Hello World');
			$ node hello.js
			Hello World
	
## file operations
		readFile : 
			takes a file path and a callback.
			The callback will be invoked when the file is done being read.
			The file data comes in the form of a Buffer,
			which is basically a byte array. 
			We can convert it to a string using the toString() function.
```javascript										
				// Load the fs (filesystem) module.
				var fs = require('fs');// 

				// Read the contents of the file into memory.
				fs.readFile('example_log.txt', function (err, logData) {
				
				// If an error occurred, throwing it will
				// display the exception and kill our app.
				if (err) throw err;
				
				// logData is a Buffer, convert to string.
				var text = logData.toString();
				
				var results = {};

				// Break up the file into lines.
				var lines = text.split('\n');
				
				lines.forEach(function(line) {
					var parts = line.split(' ');
					var letter = parts[1];
					var count = parseInt(parts[2]);
					
				if(!results[letter]) {
					results[letter] = 0;
					}
					
				results[letter] += parseInt(count);
				});
				
				console.log(results);
				// { A: 2, B: 14, C: 6 }
				});
```
HTTP server example
```javascript
	var http = require('http');

	http.createServer(function (req, res) {
		res.writeHead(200, {'Content-Type': 'text/plain'});
		res.end('Hello World\n');
	}).listen(8080);

	console.log('Server running on port 8080.');

	// This is not a full-featured HTTP server.
	// It can't serve any HTML file or images.
	// In fact, no matter what you request, it will return 'Hello World'.
	// However, you can run this and hit http://localhost:8080 in your browser and you'll see the text.
				
	// If you want this to be a full-featured web server, then you have to do that work.
```

## Creating a realtime application with Express and Socket.io

Express is the most popular web framework for Node,<br>
while Socket.IO is a realtime framework that enables bi-directional communication between web clients and the server. <br>
We are going to create a basic tracking pixel application using the two that has a dashboard which reports realtime visits.

Besides Express and Socket.IO we will need to install the emptygif module. When the user visits http://localhost:1337/tpx.gif, a message will be sent to all the users that are viewing the homepage. The message will contain information related to the clients, mainly their IP address and user agent.

Below is the code for the server.js file:
```javascript
	var emptygif = require('emptygif');
	var express = require('express');
	var app = express();
	var server = require('http').createServer(app);
	var io = require('socket.io')(server);

	app.get('/tpx.gif', function(req, res, next) {
	io.emit('visit', {
		ip: req.ip,
		ua: req.headers['user-agent']
	});

	emptygif.sendEmptyGif(req, res, {
		'Content-Type': 'image/gif',
		'Content-Length': emptygif.emptyGifBufferLength,
		'Cache-Control': 'public, max-age=0' // or specify expiry to make sure it will call everytime
	});
	});

	app.use(express.static(__dirname + '/public'));

	server.listen(1337);
```

Now on the frontend all we have to do is listen for that 'visit' event emitted by the server and modify the UI accordingly, like so:

```html
    	<!DOCTYPE HTML>
	    <html lang="en">
	    <head>
	    <meta charset="UTF-8">
	    <title>Realtime pixel tracking dashboard</title>
	    <style type="text/css">
	  	.visit {
	  	margin: 5px 0;
	  	border-bottom: 1px dotted #CCC;
	  	padding: 5px 0;
	  	}
	  	.ip {
	  	margin: 0 10px;
	  	border-left: 1px dotted #CCC;
	  	border-right: 1px dotted #CCC;
	  	padding: 0 5px;
	  	}
	   </style>
	   </head>
	   <body>
	    <h1>Realtime pixel tracking dashboard</h1>

	   <div class="visits"></div>

	   <script src="https://code.jquery.com/jquery-1.10.2.min.js"></script>
	   <script src="//cdnjs.cloudflare.com/ajax/libs/moment.js/2.8.1/moment.min.js"></script>
	   <script src="/socket.io/socket.io.js"></script>
	   <script>
		  $(function() {
	  	var socket = io();
	  	var containerEl = $('.visits');

	  	socket.on('visit', function(visit) {
			var newItem = '<div class="visit">';
			newItem += '<span class="date">' + moment().format('MMMM Do YYYY, HH:mm:ss') + '</span>';
			newItem += '<span class="ip">' + visit.ip + '</span>';
			newItem += '<span class="ua">' + visit.ua + '</span></div>';
			containerEl.append(newItem);
		 });
		 });
	   </script>
	  </body>
	   </html>

Now start up the application, open the dashboard in a tab and the tracking pixel URL in different browsers.

The dashboard should be similar to this one:

### Resources :
	
	source code repository for function writen in javascript https://www.npmjs.com
	reference https://nodejs.org/docs/latest/api/
	
	nod.js by gamma https://github.com/egamma/nodejs-guidelines   
	https://www.youtube.com/watch?v=Rc9LJ9bdHJY
	http://blog.modulus.io/absolute-beginners-guide-to-nodejs
	http://noeticforce.com/best-nodejs-tutorial-with-examples

	https://scotch.io/tutorials/building-a-real-time-markdown-viewer

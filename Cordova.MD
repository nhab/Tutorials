## Cordova
	is a  Free and open source platform for building hybrid mobile applications
	
	using HTML, CSS and JavaScript Targetting multiple platforms with one code base

|Concept   | Description   |
|:---			|:---|
|		WebView: |	you will see your app interface through the WebView component.Think of it as a browser that displays Web pages (user interface).|
|			|In fact, WebView is an HTML rendering engine, which renders HTML pages.|
|			|   |
|		Web App: |	This is where your application code is stored.|
|			|The app is implemented as an HTML Web page and is typically named index.html
|			|, which points to external files such as CSS, JavaScript 
|			|and other important resources required for it to run.
|			|This component also has a very crucial file called config.xml
|			|, which stores all-important metadata information about the app
|			|, such as its name, description and some specific parameters 
|			|affecting the working of the app.

|		Plugins:|
			-they enable you to invoke native code from JavaScript.
			-Plugins are an important component of the Cordova ecosystem. 
			-They provide an interface for Cordova and native components 
			to communicate with each other, and are bound to standard device APIs.

			Apache Cordova maintains such a set of plugins called the Core Plugins
			, which allow your application to access core device capabilities 
			such as the battery, camera, accelerometer, etc.

		:process:
			1.installing
				1. Download and install Node.js (https://nodejs.org/). 
				The Cordova command line tool is distributed as an npm package
				, so we will use Node and npm to install Cordova.

				2. Install the Cordova module using the npm utility of Node.js. 
				The Cordova module will be automatically downloaded by the npm utility.
					a. If you are using Windows, run the following command in the command prompt:

					$ npm install -g cordova

					b. If you are using Linux or OS X, run the following command in the terminal:

					$ sudo npm install -g cordova

			2.Checking cordova exists: 

				$ cordova -v 

				shows its version
			3.Creating an app
				1.change to the directory you want create your  project
				via the command prompt terminal
				2.creates the required directory structure by:
					running the following command:
					$ cordova create torchapp com.app.torch Torch

					description:
						cordova create:
							creates a default Web-based application 
							whose home page is the index.html file in /www directory.
							This page loads up when you run your app. 
							In short, this is the entry point of the app.

						torchapp:
							directory name in which the app will be created.

						com.app.torch: 
							This is the default reverse domain value, 
							in which the classes will be stored. 
							You can use your own domain value.

						Torch:
							This is the name (title) of the app.
					For a complete set of options, type cordova help create.
					directory structure
						will have the following structure:
							·hooks\
							· platform\
							· plugins\
							· www\
							o   css\
							o   img\
							o   js\
							o   index.html
							· config.xml
						which
							hooks\:
								This directory is used to store scripts for customising cordova-cli-commands.
							platform\:
								This directory contains all the scripts and source code
								for the platform that you add to your Cordova project.
							plugins\:
								This directory is used to store plugins, which will be used in the app.
							www\: 
								This directory stores all the Web artefacts of the project
								, such as CSS, HTML and JavaScript files. 
								Most of the code will be stored here. 
								In short, this is the brain of the Cordova app.
							config.xml: 
								This file contains all the important information about the Cordova app
								, such as its name, description, content-src, etc. 
								It allows you to customise the behaviour of your project.
				3.Adding the platform
						Since we are creating an app for the Android platform, 
						we need to add the platform to the Cordova project. 
						
						Go to the Cordova project’s directory, torchapp, 
						and run the following command:

						$ cordova platform add android -–save
						$ cordova platform add browser --usegit
				4.checking platforms/prerequisites
					4.1.Checking current set of platforms:

						$ cordova platform ls

					4.2.checking Prerequisites for building an app
							To build and run apps on the computer, 
							you need to install SDKs for each targeted platform;
							or if you are using a browser for the development
							,it does not require any platform SDKs.

							You can check if your system meets the requirements 
							for building the platform by running the following command:
							
							$ cordova requirements
				5. installing android sdk 
					http://askubuntu.com/questions/318246/complete-installation-guide-for-android-sdk-adt-bundle-on-ubuntu
					1-download from bottom of this page : http://developer.android.com/sdk/index.html
					2-unzip it go to the directory \tools
					3-run this command line:
						./android
					4-install desired targets :
						after running that command line, update tool will run
						select desired target android versions and tools
						and install them
				6. android sdk path
					in android sdk manager window > below the menu bar ,it is written
				7.setting environment variables
					1-display current enviroment variable
						$ set

						1-The $PATH defined the search path for commands.
						2- $PS1 defines your prompt settings.
						3- list of Commonly_Used_Shell_Variables : https://bash.cyberciti.biz/guide/Variables#Commonly_Used_Shell_Variables
						
						4-You can display the value of a variable using printf or echo command:
							$ echo "$HOME" 
							$ echo $PATH
							$ printf "%s\n" $PATH

						5-You can modify each environmental or system variable using the export command
							export PATH=${PATH}:/home/vivek/bin
							To set the JAVA_HOME environment variable :
								export PATH=${PATH}:/usr/java/jdk1.5.0_07/bin

							:res: https://bash.cyberciti.biz/guide/Export_Variables

					2-add Installed Targets to environment variables and make it permenant:
						-Press CTRL + ALT + T to open a new terminal 
						-Run $gedit ~/.bashrc
						($ sudo gedit .profile)
					3-Add the following to the top of the entire text and then save it.
					(Do not close the file)

						export PATH=${PATH}:~/android-sdk-linux/tools
						export PATH=${PATH}:~/android-sdk-linux/platform-tools
				8.running the app
					$ cordova run <platform name>
				9.Creating the app interface
					1.image
						-select image from sites like:http://www.flaticon.com/
						-download the icon , preferably of size 64×64 pixels in .png format
						, rename it power.png 
						and copy it to the www/img/ directory in the Cordova project’s directory.
					2-then edit index.html in the way you like.
						for example:
							<!DOCTYPE html>
							<html>
							<head>
								<meta http-equiv=”Content-Security-Policy” content=”default-src ‘self’ data: gap: https://ssl.gstatic.com ‘unsafe-eval’; style-src ‘self’ ‘unsafe-inline’; media-src *”>
								<meta name=”format-detection” content=”telephone=no”>
								<meta name=”msapplication-tap-highlight” content=”no”>
								<meta name=”viewport” content=”user-scalable=no, initial-scale=1, maximum-scale=1, minimum-scale=1, width=device-width”>
								<link rel=”stylesheet” type=”text/css” href=”css/index.css”>
								<title>Torch Light</title>
							</head>
							<body>
								<div class=”app”>
									<div id=”deviceready” align=”center”>
										<img src=”img/power.png” id=”torch”/>
									</div>
								</div>
								<script type=”text/javascript” src=”cordova.js”></script>
								<script type=”text/javascript” src=”js/index.js”></script>
							</body>
							</html>
					3.Adding style to the app
						in the torchapp/www/css/ directory
				10.Installing and adding the plugin
					for example flashlight/torch plugin
						:run the following command in your project directory:
						$ cordova plugin add cordova-plugin-flashlight
					This command adds the plugin to the Cordova project. 
					We can access this plugin using JavaScript code.
				11.Adding logic to the app by editing the index.js 
					index.js
						var app = {
							// Application Constructor
							initialize: function () {
								this.bindEvents();
							},
							bindEvents: function () {
								document.addEventListener(‘deviceready’, this.onDeviceReady, false);
							},
							onDeviceReady: function () {
								app.receivedEvent(‘deviceready’);
								document.getElementById(“torch”).addEventListener(“click”, function () {
								window.plugins.flashlight.toggle();
								});
							},   
							receivedEvent: function(id) {
							console.log(id);
							}   
						};
						app.initialize();
					:description
						-initialize()
							: This is a default application constructor. 
							It makes a call to bindEvent() when the application starts up.
						-bindEvent()
							: This is a bind event listener that binds events 
							such as load, deviceready, offline, etc, which are required on start up. 
							In the above code, this function is listening for the ‘deviceready’ event.
								Once the device is ready, it 		makes a call to onDeviceReady().
						-onDeviceReady()
							: This is a ‘deviceready’ event handler;
								in this function, we make an explicit call to app.receivedEvent()
								, which specifies the device is ready. 
								We have added the plugin code to turn on the flashlight of the mobile’s camera 
								in this function.
								We have added a click event listener to an element whose ID is ‘torch’
								, which means that when we click that element
								, the window.plugins.flashlight.toggle() function is called. 
								In simple words, it toggles the flashlight on/off, when we click the element.

						-receivedEvent()
							: This function is used to handle the deviceready event.
				12.Building the app
						$ cordova build android
					This command generates a .apk file
						at C:\project\torchapp\platforms\android\build\outputs\apk\ location 
					in our project directory with the name ‘android-debug.apk’.

					Note: You can use the cordova build command to build the app for multiple target platforms
						such as iOS, Windows Phone, etc, by suitably replacing the keyword android 
						in the above command statement.
				13.Installing and testing the app
					Now copy or transfer the android-debug.apk file to your phone 
					via USB cable or Bluetooth, 
					and install it (while installing, you may receive an ‘Install blocked’ message,
					as shown in Figure 2. So click Settings, check the ‘Unknown Sources’ option and select ‘OK’, 
					as shown in Figure 3). This will now give you access permission of the app;
					next, click on ‘Install’.
					After installing the app, open it as shown in Figure 4. Since this is a torch application, we have created a white background for the app, so the user can use the bright screen light as well. When you open the app, you will see a black power button image at the top-centre. Click on it to toggle the mobile camera flashlight on/off.
					res: https://github.com/aniketkudale/torch-app/
						-http://opensourceforu.com/2016/08/build-first-mobile-application-using-apache-cordova/
				14.-debugging cordova app
					http://stackoverflow.com/questions/21332853/is-there-a-real-solution-to-debug-cordova-apps
		-your first app 	https://www.toptal.com/mobile/developing-mobile-applications-with-apache-cordova
	:res https://cordova.apache.org/
	

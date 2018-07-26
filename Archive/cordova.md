<pre>
1.Creating an app source project
    :{
        Frameworks
            :Questions
                comparing capabilities of framework?
                    compare frameworks http://noeticforce.com/mobile-app-development-cordova-vs-react-native-vs-xamarin
            :{
                #cordova
                    :Mobile apps with HTML, CSS & JS Target multiple platforms 
                    with one code base Free and open source
                    :{
                        WebView: 
                            you will see your app interface through the WebView component.
                            Think of it as a browser that displays Web pages (user interface).
                            In fact, WebView is an HTML rendering engine, which renders HTML pages.

                        Web App: 
                            This is where your application code is stored.
                            The app is implemented as an HTML Web page and is typically named index.html
                            , which points to external files such as CSS, JavaScript 
                            and other important resources required for it to run.
                            This component also has a very crucial file called config.xml
                            , which stores all-important metadata information about the app
                            , such as its name, description and some specific parameters 
                            affecting the working of the app.

                        Plugins:
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
                #jquery mobile
                    : https://jquerymobile.com/
                    
                #ionicframework
                    -Ionic currently requires AngularJS in order to work at its full potential.
                    :process
                        - http://ionicframework.com/docs/guide/building.html
                        - your first app res:https://scotch.io/tutorials/create-your-first-mobile-app-with-angularjs-and-ionic
                                https://github.com/ashteya/ionic-tutorial-dinnerapp
                    res: http://ionicframework.com/
                            http://view.ionic.io/


                #sap ui5 mobile
                    :process
                        1.installing
                            :Res
                                https://help.sap.com/saphelp_nw74/helpdata/en/f2/5b203ec8254605a3bcbc07734b3c20/content.htm?frameset=/en/7b/b04e05f9484e1b95b38a2e48ecef4f/frameset.htm&current_toc=/en/5c/be4e5b4a19479a92b1d32ff23b7b63/plain.htm&node_id=24
                                https://help.sap.com/saphelp_nw74/helpdata/en/7b/b04e05f9484e1b95b38a2e48ecef4f/content.htm?frameset=/en/8b/49fc198bf04b2d9800fc37fecbb218/frameset.htm&current_toc=/en/5c/be4e5b4a19479a92b1d32ff23b7b63/plain.htm&node_id=21&show_children=false
                            :prerequisits
                                - Operating system: Windows XP, Vista, 7 (32- or 64-Bit), 8/8.1
                                - Java Runtime environment: JRE 1.6, 32/64-Bit 
                                - APUI5 ABAP Team Provider 
                                - Eclipse Platform for SAPUI5 tools: 
                https://help.sap.com/saphelp_nw74/helpdata/en/59/2f36fd077b45349a67dcb3efb46ab1/content.htm
                #NativeScript 2
                    :
                        build cross-platform, native iOS and Android apps without web views.
                        Using Angular, TypeScript
                        or modern JavaScript 
                        it runs on node.js
                        Get 100% access to native APIs via JavaScript 
                        and reuse of packages from npm, CocoaPods and Gradle. 
                        Open source and backed by Telerik.
                    :prerequisits
                        •Windows 7 Service Pack 1 or later
                        •The latest Node.js 0.10.x, 0.12.x, 4.x, 5.x, or 6.x stable official release
                        •(Optional) Chocolatey to simplify the installation of dependencies
                        •JDK 8 or a later stable official release
                        •Android SDK 22 or a later stable official release
                        •Local Maven repository for Support Libraries
                        •Android SDK Build-tools 23.0.3 or a later stable official release
                        •(Optional) Genymotion to expand your testing options

                        You must also have the following two environment variables setup for Android development:
                        •JAVA_HOME
                        •ANDROID_HOME

                        The recommended ways to create NativeScript Applications is either 
                            through the Command-Line Interface (CLI)
                            or through the Telerik AppBuilder.
                    :process
                        1.Setting Up NativeScript
                            1.1. install Node.js. 
                                - check if it is already installed:
                                    $ node --version

                            1.2. install the NativeScript command-line tool (CLI) 
                                by executing this command line:
                                    
                                    npm install -g nativescript

                            1.3. install the development tool for each platform that you want to deploy to.
                                For Android, this is the Android SDK.
                                For iOS, it's XCode

                        -howto
                            http://code.tutsplus.com/tutorials/create-your-first-nativescript-app--cms-26957
                    res: https://docs.nativescript.org/
                #ratchet 
                    :Build mobile apps with simple HTML, CSS, and JS components.
                    https://github.com/twbs/ratchet		
                #Rhino	
                    : converts JavaScript scripts into classes. 
                        - it can be used as a debugger by using the Rhino shell. 
                        - It can be used in applications by embedding Rhino.
                        - it is a open source project	git clone https://github.com/mozilla/rhino.git
                    :process
                        -Execute JavaScript in Android without WebView
                            
                            Of course, you don't have to get the source code. If you want to use it in your Android project. Download Rhino first, unzip it, put the js.jar file under libs folder. It is very small, so you don't need to worry your apk file will be ridiculously large because of this one external jar.

                            Here is some simple code to execute JavaScript code.

                            Object[] params = new Object[] { "javaScriptParam" };

                            // Every Rhino VM begins with the enter()
                            // This Context is not Android's Context
                            Context rhino = Context.enter();

                            // Turn off optimization to make Rhino Android compatible
                            rhino.setOptimizationLevel(-1);
                            try {
                                Scriptable scope = rhino.initStandardObjects();

                                // Note the forth argument is 1, which means the JavaScript source has
                                // been compressed to only one line using something like YUI
                                rhino.evaluateString(scope, javaScriptCode, "JavaScript", 1, null);

                                // Get the functionName defined in JavaScriptCode
                                Object obj = scope.get(functionNameInJavaScriptCode, scope);

                                if (obj instanceof Function) {
                                    Function jsFunction = (Function) obj;

                                    // Call the function with params
                                    Object jsResult = jsFunction.call(rhino, scope, scope, params);
                                    // Parse the jsResult object to a String
                                    String result = Context.toString(jsResult);
                                }
                            } finally {
                                Context.exit();
                            }
                    :res 
                        documentation https://developer.mozilla.org/en-US/docs/Mozilla/Projects/Rhino/Documentation
                        https://developer.mozilla.org/en-US/docs/Mozilla/Projects/Rhino
                #framework7
                    res: http://framework7.io/
                #iphone ios sdk app dev
                    res:
                        https://www.amazon.com/Beginning-iPhone-Development-Exploring-iOS-ebook/dp/B00M4FC7O6/187-3091559-9159912?ie=UTF8&me=&ref_=mt_kindle#nav-subnav
                #sencha
                    :To modernize Oracle Forms 
                    :process
                        your first app http://docs.sencha.com/architect/3/guides/tutorials/first_mobile_application.html
                                            https://www.sitepoint.com/building-simple-app-using-ionic-advanced-html5-mobile-app-framework/
                    res:http://docs.sencha.com/architect/3/index.html

        Tools
            phonegap
                :PhoneGap is based on the open source Cordova and is the commercial version owned by Adobe.
                -use WebView
                -You can use any choice of JavaScript or UI frameworks to get started with PhoneGap. jQuery Mobile alongside KnockOut.js or AngularJS is a nice combination. Once you are done with your code, PhoneGap takes it from there and wraps it based on the intended platform. Applications built using PhoneGap use a web view to render their content. 
                -PhoneGap has a minimal set of web APIs to access phone hardware features and it’s possible to write custom plugins to suit requirements.
                ::process
                    http://modernweb.com/2013/03/29/phonegap-build-part1/ 
                res:http://phonegap.com/
            #Ibm mobileFirst studio
                res: https://mobilefirstplatform.ibmcloud.com/tutorials/en/foundation/6.3/hello-world/creating-your-first-hybrid-application/
            intel-xdk
                :res:https://software.intel.com/en-us/intel-xdk
                ::process
                    https://udinra.com/blog/create-mobile-app-intel-xdk
            appgyver
                free for start but advance features have price
                res: https://www.appgyver.com/

            #scriptit
                res:
                    https://scriptit-app.com
                    http://lifeofcoding.com/2015/04/05/Execute-JavaScript-in-Android-without-WebView/
            #Telerik Appbuilder vs Extension
                res:https://visualstudiogallery.msdn.microsoft.com/d486edc5-aae3-4ad9-84c1-578efc0a32ed
            #Xamarin
                https://www.youtube.com/channel/UCmrqaIMRI3z2MxfwfeDudsw

2.building apk
    building and deploying Cordova apps:
        $ cordova build android
    and you can also run the app directly on the device / emulator
        $ cordova run android
        $ cordova emulate android

    If you want to build a release version of an APK from the command line for production, this is also possible.
    However, this does not sign your release:
        $ cordova build android --release

3.signing an APK
    :tools: 
        there are many tools for signing:
            - jarsigner
            -android studio itself
            -  apk-signer https://bitbucket.org/haibison/apk-signer/
            https://shatter-box.com/knowledgebase/android-apk-signing-tool-apk-signer/
            -signer and aligner :http://lukealderton.com/projects/programs/android-apk-signer-aligner.aspx
        Generate a private key 
            http://docs.oracle.com/javase/6/docs/technotes/tools/solaris/keytool.html

    :terms:
        Certificate:(Public key)
            -Android requires that all APKs be digitally signed with a certificate
            before they can be installed

            -public-key certificate = digital certificate = identity certificate 
                are to ensure that any future updates to your APK are authentic 
                and come from the original author.

                -it contains the public key of a public/private key pair
                , as well as some other metadata identifying the owner of the key 
                (for example, name and location). 
                The owner of the certificate holds the corresponding private key.
                
                -When you sign an APK, the signing tool attaches the public-key certificate to the APK. 
                -The public-key certificate serves as as a "fingerprint" 
                    that uniquely associates the APK to you
                    and your corresponding private key.
                -This helps Android ensure that any future updates to your APK are authentic and come from the original author.  
        keystore file (private key)
            :is a binary file that contains one or more PRIVATE keys.
            - You are branding your application with your credentials. 
            You can brand multiple applications with the same key.
            -a certificate, using a public/private key mechanism (the certificate is signed with your private key)						 
            When you sign an APK for release ,you can choose to generate a new keystore and private key 
            (or use a keystore and private key you already have)
    :process
        Steps of Sign Your App Manually
            1-	Generate a private key using keytool. For example:
                $ keytool -genkey -v -keystore my-release-key.keystore
                -alias alias_name -keyalg RSA -keysize 2048 -validity 10000
            2-Compile your app in release mode to obtain an unsigned APK.
            3-Sign your app with your private key using jarsigner
                :X
                    $ jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1
                    -keystore my-release-key.keystore my_application.apk alias_name
            4-Verify that your APK is signed. For example:
                $ jarsigner -verify -verbose -certs my_application.apk
            5-Align the final APK package using zipalign.
                $ zipalign -v 4 your_project_name-unaligned.apk your_project_name.apk
                zipalign ensures that all uncompressed data starts with a particular byte alignment
                relative to the start of the file, which reduces the amount of RAM consumed by an app.
        Securing Your Private Key
            Your reputation as a developer entity depends on your securing your private key properly, at all times, until the key is expired. Here are some tips for keeping your key secure:

            -Select strong passwords for the keystore and key.
            -Do not give or lend anyone your private key, and do not let unauthorized persons know your keystore and key passwords.
            -Keep the keystore file containing your private key in a safe, secure place.
        Remove Signing Information from Your Build Files
            When you create a signing configuration, Android Studio adds your signing information in plain text to the module's build.gradle files. If you are working with a team or open-sourcing your code, you should move this sensitive information out of the build files so it is not easily accessible to others. To do this, you should create a separate properties file to store secure information and refer to that file in your build files as follows:

            Create a signing configuration, and assign it to one or more build types. These instructions assume you have configured a single signing configuration for your release build type, as described in Configure the Build Process to Automatically Sign Your APK, above.
            Create a file named keystore.properties in the root directory of your project. This file should contain your signing information, as follows:
            storePassword=myStorePassword
            keyPassword=mykeyPassword
            keyAlias=myKeyAlias
            storeFile=myStoreFileLocation
            In your module's build.gradle file, add code to load your keystore.properties file before the android {} block.
            ...

            // Create a variable called keystorePropertiesFile, and initialize it to your
            // keystore.properties file, in the rootProject folder.
            def keystorePropertiesFile = rootProject.file("keystore.properties")

            // Initialize a new Properties() object called keystoreProperties.
            def keystoreProperties = new Properties()

            // Load your keystore.properties file into the keystoreProperties object.
            keystoreProperties.load(new FileInputStream(keystorePropertiesFile))

            android {
                ...
            }
            Note: You could choose to store your keystore.properties file in another location (for example, in the module folder rather than the root folder for the project, or on your build server if you are using a continuous integration tool). In that case, you should modify the code above to correctly initialize keystorePropertiesFile using your actual keystore.properties file's location.

            You can refer to properties stored in keystoreProperties using the syntax keystoreProperties['propertyName']. Modify the signingConfigs block of your module's build.gradle file to reference the signing information stored in keystoreProperties using this syntax.
            android {
                signingConfigs {
                    config {
                        keyAlias keystoreProperties['keyAlias']
                        keyPassword keystoreProperties['keyPassword']
                        storeFile file(keystoreProperties['storeFile'])
                        storePassword keystoreProperties['storePassword']
                    }
                }
                ...
            }
            Open the Build Variants tool window and ensure that the release build type is selected.
            Click Build > Build APK to build your release build, and confirm that Android Studio has created a signed APK in the build/outputs/apk/ directory for your module.
            Because your build files no longer contain sensitive information, you can now include them in source control or upload them to a shared codebase. Be sure to keep the keystore.properties file secure. This may include removing it from your source control system.
        how to create signed APK ?( using cordova command line interface)
            res:
                http://stackoverflow.com/questions/26449512/how-to-create-signed-apk-file-using-cordova-command-line-interface
                http://ilee.co.uk/Sign-Releases-with-Cordova-Android/

    res:https://developer.android.com/studio/publish/app-signing.html 
4.publishinng on googlePaly
    :{
        1.Registering for a Google Play publisher account (it has $25 registration fee! )
            visit https://play.google.com/apps/publish/signup/ 
        2.Setting up a Google payments merchant account, if you will sell apps or in-app products.
        3.Exploring the Google Play Developer Console and publishing tools.
        Add an APK
            Go to your Google Play Developer Console.
            Select All applications > Add new application.
            Using the drop down menu, select a default language and add a title for your app. ...
            Select Upload APK.
            Choose from the Production, Beta, or Alpha channels and select Upload your APK.
    http://developer.android.com/distribute/googleplay/start.html
</pre>
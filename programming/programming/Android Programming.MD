```
:why
    -door to passive incom and independence:
    developed, Android applications can be packaged easily
    and sold out either through a store such as 
        Google Play,
        SlideME,
        Opera Mobile Store,
        Mobango,
        F-droid
        and the Amazon Appstore.
    -cutting edge tech

:Parts:(main layers of android os)
    1.Linux kernel(device drivers)
        -a level of abstraction between the device hardware 
        -it contains all the essential hardware drivers like camera, keypad, display etc.
        
    2.Libraries
        including
            -WebKit : open-source Web browser engine ,
            -libc   :( "standard C library")well known library libc 
            -SQLite : database which is a useful repository for storage and sharing of application data, 
            libraries to play and record audio and video,
            SSL libraries responsible for Internet security etc.
            
    3.Android Libraries
        :{
        
            android.app		 − Provides access to the application model and is the cornerstone of all Android applications.
            android.content  − Facilitates content access, publishing and messaging between applications and application components.
            android.database − Used to access data published by content providers and includes SQLite database management classes.
            android.opengl 	 − A Java interface to the OpenGL ES 3D graphics rendering API.
            android.os 		 − Provides applications with access to standard operating system services including messages, system services and inter-process communication.
            android.text 	 − Used to render and manipulate text on a device display.
            android.view 	 − The fundamental building blocks of application user interfaces.
            android.widget   − A rich collection of pre-built user interface components such as buttons, labels, list views, layout managers, radio buttons etc.
            android.webkit 	 − A set of classes intended to allow web-browsing capabilities to be built into applications.
            
    4.Android Runtime
        :{
            Dalvik Virtual Machine
                :This section provides a key component called Dalvik Virtual Machine
                which is a kind of Java Virtual Machine specially designed and optimized for Android.

                :{
                    The Dalvik VM makes use of Linux core features
                    like memory management 
                    and multi-threading,
                    which is intrinsic in the Java language. 
                    
                    The Dalvik VM enables every Android application to run in its own process,
                    with its own instance of the Dalvik virtual machine.

            -java support:The Android runtime also provides a set of core libraries 
            wto program using standard Java programming language.

    5.The Android framework
        :{
            Activity Manager 		− Controls all aspects of the application lifecycle and activity stack.
                - activity :
                    -represents a single screen with a user interface.
                    -is the subclass of ContextThemeWrapper class.
            Content Providers 		− Allows applications to publish and share data with other applications.

            Resource Manager 		− Provides access to non-code embedded resources such as strings, color settings and user interface layouts.

            Notifications Manager   − Allows applications to display alerts and notifications to the user.

            View System 			− An extensible set of views used to create application user interfaces.
            
    6.your Applications
        Application components are the essential building blocks of an Android application.
        These components are loosely coupled by the application manifest file "AndroidManifest.xml" 
        that describes each component of the application and how they interact.

        :{:(components)
            -Activities 		:represents a single screen with a user interface =forms in win apps
                
                    (actions on the screen.) 
                :X
                    an email application might have one activity that shows a list of new emails,
                    another activity to compose an email, 
                    and another activity for reading emails
                :syntax
                    public class MainActivity extends Activity {}
            -Services 			:runs in the background to perform long-running operations.
                :X
                    For example, a service might play music in the background 
                    while the user is in a different application, 
                    or it might fetch data over the network without blocking user interaction with an activity.
                :syntax
                    public class MyService extends Service {}
            
            -Broadcast Receivers 
                :They handle communication between Android OS and applications.

                -A broadcast receiver (receiver) can be registered to listen to system messages and intents. 
                A receiver gets notified by the Android system if the specified event occurs. 
                public void onReceive(context,intent){}

                public class MyReceiver  extends  BroadcastReceiver {}


                
                -Home screen widgets
                    are broadcast receivers which provide interactive components 
                    which are primarily used on the Android home screen. 
                    They typically display some kind of data 
                    and allow the user to perform actions with them.
                    For example, a widget can display a short summary of new emails 
                    and if the user selects an email, it could start the email application with the selected email.

                To avoid confusion with views (which are also called widgets), 
                this text uses the term home screen widgets, if it speaks about widgets.

                Live wallpapers allow you to create animated backgrounds for the Android home screen.

                
            -Content Providers(providers) :	They handle data and database management issues.
                public class MyContentProvider extends  ContentProvider {
                    public void onCreate(){}
                }
        
            -Fragments 	are a portion of UI in an Activity.
                like:ListFragment,DetailsFragment.
            -Views 		UI elements  including buttons, lists forms etc.
            -ViewGroup is responsible for arranging other views. It is also known as layout manager.
            -Layouts 	View hierarchies that control screen format and appearance of the views.
                :{
                    Constraint layout

                        Constraint layout is provided by an external library. 
                        It allows you to use a flat view hierarchy and has great performance.
                        Also the design tools support constraint layout very well.
                            New projects should prefer the usage of constraint layout.
                    FrameLayout 
                        is a layout manager which draws all child elements on top of each other.
                            This allows to create nice visual effects.
                    LinearLayout 
                        puts all its child elements into a single column or row 
                        depending on the android:orientation attribute.
                        Possible values for this attribute are horizontal and vertical. 
                        horizontal is the default value.
                    

                    RelativeLayout 
                        allows positioning the widget relative to each other. 
                        This can be used for complex layouts. 
                        RelativeLayout is a complex layout manager and should only be used
                            if such a complex layout is required, as it performs a resource intensive calculation
                            to layout its children.

                        A simple usage for RelativeLayout is if you want to center a single component. 
                        Just add one component to the RelativeLayout 
                        and set the android:layout_centerInParent attribute to true.

                        <?xml version="1.0" encoding="utf-8"?>
                        <RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
                            android:layout_width="match_parent"
                            android:layout_height="match_parent"
                            android:orientation="vertical" >

                            <ProgressBar
                                android:id="@+id/progressBar1"
                                style="?android:attr/progressBarStyleLarge"
                                android:layout_width="wrap_content"
                                android:layout_height="wrap_content"
                                android:layout_centerInParent="true"
                                />

                        </RelativeLayout>

                    GridLayout

                        GridLayout was introduced with Android 4.0. This layout allows you to organize a view 
                        into a Grid. GridLayout separates its drawing area into: rows, columns, and cells.

                        You can specify how many columns you want to define for each View, 
                        in which row and column it should be placed as well as how many columns and rows
                            it should use. If not specified, GridLayout uses defaults, 
                            e.g., one column, one row and the position of a view depends
                            on the order of the declaration.

                        The following layout file defines a layout using GridLayout.

                        <?xml version="1.0" encoding="utf-8"?>
                        <GridLayout xmlns:android="http://schemas.android.com/apk/res/android"
                            android:id="@+id/GridLayout1"
                            android:layout_width="match_parent"
                            android:layout_height="match_parent"
                            android:columnCount="4"
                            android:useDefaultMargins="true" >

                            <TextView
                                android:layout_column="0"
                                android:layout_columnSpan="3"
                                android:layout_gravity="center_horizontal"
                                android:layout_marginTop="40dp"
                                android:layout_row="0"
                                android:text="User Credentials"
                                android:textSize="32dip" />

                            <TextView
                                android:layout_column="0"
                                android:layout_gravity="right"
                                android:layout_row="1"
                                android:text="User Name: " >
                            </TextView>

                            <EditText
                                android:id="@+id/input1"
                                android:layout_column="1"
                                android:layout_columnSpan="2"
                                android:layout_row="1"
                                android:ems="10" />

                            <TextView
                                android:layout_column="0"
                                android:layout_gravity="right"
                                android:layout_row="2"
                                android:text="Password: " >
                            </TextView>

                            <EditText
                                android:id="@+id/input2"
                                android:layout_column="1"
                                android:layout_columnSpan="2"
                                android:layout_row="2"
                                android:inputType="textPassword"
                                android:ems="8" />

                            <Button
                                android:id="@+id/button1"
                                android:layout_column="2"
                                android:layout_row="3"
                                android:text="Login" />

                        </GridLayout>
                    -The ScrollView or the HorizontalScrollView class 
                        is not a layout manager. It is useful to make views available, 
                        even if they do not fit onto the screen.
                            A scroll view can contain one view,
                        e.g., a layout manager containing more views.
                            If the child view is too large, scroll view allows scrolling the content.


            -Intents 	Messages wiring components together.
            -Resources 	External elements, such as strings, constants and drawable pictures.
                Resource 		Folder 				Description

                Drawables		/res/drawables	Images (e.g., png or jpeg files)or vector drawables or XML files 
                                                which scale automatically with the density of the Android device

                Simple Values	/res/values		Used to define strings, colors, dimensions, styles and 
                                                static arrays of strings or integers via XML files.
                                                    By convention each type is stored in a separate file,
                                                    e.g., strings are defined in the res/values/strings.xml file.

                Layouts			/res/layout		XML files with layout descriptions are used to define the 
                                                user interface for activities and fragments.

                Styles and themes /res/values	Files which define the appearance of your Android application.

                Animations 		/res/animator		Defines animations in XML for the animation API 
                                                which allows to animate arbitrary properties of objects over time.

                Raw data		/res/raw			Arbitrary files saved in their raw form. You access them 
                                                via an InputStream object.

                menus			/res/menu		Defines the actions which can be used in the toolbar of 
                                                the application.

            -Manifest 	Configuration file for the application.
            -Context

                Instances of the class android.content.Context provide the connection to the Android system
                and device the application is running on. 
                It gives access to the system and application resources and services

                For example, you can check the size of the current device display via the Context.

                Activities and services extend the Context class. 
                Therefore, they can be directly used to access the Context.

:Procs:
    prerequisites
        -Java JDK5 or later version
            :opts:
            
                -On Linux, if the SDK is installed in /usr/local/jdk1.6.0_15 
                and you use the C shell, you would put the following code into your .cshrc file.

                setenv PATH /usr/local/jdk1.7.0_75/bin:$PATH
                setenv JAVA_HOME /usr/local/jdk1.7.0_75
            
                -Alternatively, if you use an Integrated Development Environment (IDE) Eclipse,
                then it will know automatically where you have installed your Java.
            :Procs:
                -# install openjdk
                    sudo apt-get install openjdk-7-jdk
                -to check existance,in shell:
                    java -version
                -to check its path
                    $ which java
                    or 
                    $ whereis java
                -to compile
                    $ javac MyFirstJavaClass.java
                -to run your compiled program
                    $ java MyFirstClass
        -Android SDK
            -download android sdk
                wget http://dl.google.com/android/android-sdk_r24.2-linux.tgz

                tar -xvf android-sdk_r24.2-linux.tgz
            - install all sdk packages
                cd android-sdk-linux/tools
                ./android update sdk --no-ui
            -# set path
                vi ~/.zshrc << EOT

                export PATH=${PATH}:$HOME/sdk/android-sdk-linux/platform-tools:$HOME/sdk/android-sdk-linux/tools:$HOME/sdk/android-sdk-linux/build-tools/22.0.1/

                EOT

                source ~/.zshrc
            -ealuating setup
                $ cd ~
                $ android

                This should fire up your Android SDK Manager.
            -evaluating android virtual device manager
                android avd
            -evaluating ADB version
                adb version
        -Java Runtime Environment (JRE) 6
        -Android Studio
        -(Eclispse is optional)
        ....

    -launching android studio:
        - open a terminal, 
        >navigate to the android-studio/bin/ directory
        >and execute studio.sh 
            Select whether you want to import previous Android Studio settings or not
        > then click OK.
    -How to add Android Studio to the launcher?
    
        Creating an Android Project with Android Studio
            In Android Studio: create a new project:
                If you don't have a project opened, 
                    in the Welcome to Android Studio window, 
                    click Start a new Android Studio project.
                If you have a project opened, select File > New Project.
            In the New Project screen, enter the following values:

                Application Name: "My First App"
                Company Domain: "example.com"

            Android Studio fills in the package name and project location for you,
                but you can edit these if you'd like.
            Click Next.
            In the Target Android Devices screen, keep the default values and click Next.

            The Minimum Required SDK is the earliest version of Android that your app supports,
                which is indicated by the API level. 
                To support as many devices as possible, you should set this to the lowest version available 
                that allows your app to provide its core feature set.
                If any feature of your app is possible only on newer versions of Android
                and it's not critical to the core feature set,
                enable that feature only when running on the versions that support it
                
            In the Add an Activity to Mobile screen, select Empty Activity and click Next.
            In the Customize the Activity screen, keep the default values and click Finish. 

        After some processing, Android Studio opens and displays a "Hello World" app with default files.
        You will add functionality to some of these files in the following lessons.

        Now take a moment to review the most important files. 
        First, be sure that the Project window is open (select View > Tool Windows > Project) 
        and the Android view is selected from the drop-down list at the top. 
        You can then see the following files:

        app > java > com.example.myfirstapp > MainActivity.java
            This file appears in Android Studio after the New Project wizard finishes. It contains the class definition for the activity you created earlier. When you build and run the app, the Activity starts and loads the layout file that says "Hello World!"
        app > res > layout > activity_main.xml
            This XML file defines the layout of the activity. It contains a TextView element with the text "Hello world!".
        app > manifests > AndroidManifest.xml
            The manifest file describes the fundamental characteristics of the app and defines each of its components. You'll revisit this file as you follow these lessons and add more components to your app.
        Gradle Scripts > build.gradle
            Android Studio uses Gradle to compile and build your app. There is a build.gradle file for each module of your project, as well as a build.gradle file for the entire project. Usually, you're only interested in the build.gradle file for the module. in this case the app or application module. For more information about this file, see Building Your Project with Gradle.
    - Running android project
        Run on a Real Device
            Set up your device as follows:
                Connect your device to your development machine with a USB cable. If you're developing on Windows, you might need to install the appropriate USB driver for your device. For help installing drivers, see the OEM USB Drivers document.
                Enable USB debugging on your device by going to Settings > Developer options.
                Note: On Android 4.2 and newer, Developer options is hidden by default. To make it available, go to Settings > About phone and tap Build number seven times. Return to the previous screen to find Developer options.

            Run the app from Android Studio as follows:
                In Android Studio, select your project and click Run from the toolbar.
                In the Select Deployment Target window, select your device, and click OK.

            Android Studio installs the app on your connected device and starts it.
            Run on an Emulator

            Before you run your app on an emulator, you need to create an Android Virtual Device (AVD) definition. An AVD definition defines the characteristics of an Android phone, tablet, Android Wear, or Android TV device that you want to simulate in the Android Emulator.

            Create an AVD Definition as follows:
                Launch the Android Virtual Device Manager by selecting Tools > Android > AVD Manager, or by clicking the AVD Manager icon in the toolbar.
                In the Your Virtual Devices screen, click Create Virtual Device.
                In the Select Hardware screen, select a phone device, such as Nexus 6, and then click Next.
                In the System Image screen, choose the desired system image for the AVD and click Next.

                If you don't have a particular system image installed, you can get it by clicking the download link.
                Verify the configuration settings (for your first AVD, leave all the settings as they are), and then click Finish.

            For more information about using AVDs, see Create and Manage Virtual Devices.

            Run the app from Android Studio as follows:

                In Android Studio, select your project and click Run from the toolbar.
                In the Select Deployment Target window, select your emulator and click OK.

            It can take a few minutes for the emulator to start. You may have to unlock the screen. When you do, My First App appears on the emulator screen.

            That's how you build and run your Android app on the emulator!
    -Basic structure of android projects:
        1. src/: 
            This folder contains the Java source files.
        2. gen/:
            Generated Java library, this library is for Android internal use only.
        3. Res/:
                Here we can store resource files such as pictures, XML files for defining layouts, and so forth. 
                Within this folder there are additional folders such as Drawable, Layout, and Values.

            . Drawable: 
                Here we store the various graphic files. We can see three types of drawable folders.
                This is because there are many Android devices with different screen resolutions.
                By default, there are several versions of this folder such as: Drawable-mdpi, 5. drawable-hdpi, and so forth.
                This is required in order to adapt to different screen resolutions.

            . Layout: 
                This is the place for XML layout files. Layout files are XML files which define how various Android objects
                (such as textboxes, buttons, etc.) are organized on the screen.
            . menu
            . Values:
                    XML files which store various string values (titles, labels, etc.).

        
        . assets/
        . bin/
        . libs/
        
        .AndroidManifest.xml:
            This is the Android definition file.
            It contains information about the Android application such as 
            minimum Android version, permission to access Android device capabilities such as
            internet access permission, ability to use phone permission, etc.
        .project.properties
        
    - Android application activity life:callbacks(events)
        :Android system initiates its program with in an Activity 
        starting with a call on onCreate() callback method. 
        There is a sequence of callback methods that start up an activity
            and a sequence of callback methods that tear down an activity .
            -The Activity class defines the following call backs i.e. events.
            You don't need to implement all the callbacks methods.
            :parts{ 
            Callback 	Description
            onCreate() 	This is the first callback and called when the activity is first created.
            onStart() 	This callback is called when the activity becomes visible to the user.
            onResume() 	This is called when the user starts interacting with the application.
            onPause() 	The paused activity does not receive user input and cannot execute any code
                and called when the current activity is being paused and the previous activity is being resumed.
            onStop() 	This callback is called when the activity is no longer visible.
            onDestroy() 	This callback is called before the activity is destroyed by the system.
            onRestart() 	This callback is called when the activity restarts after stopping it.
    -walktrough with example:
        1.main activity class modification
            -Following is the content of the modified main activity file src/com.example.helloworld/MainActivity.java.
            This file includes each of the fundamental life cycle methods. 
            The Log.d() method has been used to generate log messages:

            package com.example.helloworld;

            import android.os.Bundle;
            import android.app.Activity;
            import android.util.Log;

            public class MainActivity extends Activity {
            String msg = "Android : ";
            
            /** Called when the activity is first created. */
            @Override
            public void onCreate(Bundle savedInstanceState) {
                super.onCreate(savedInstanceState);
                setContentView(R.layout.activity_main);
                Log.d(msg, "The onCreate() event");
            }

            /** Called when the activity is about to become visible. */
            @Override
            protected void onStart() {
                super.onStart();
                Log.d(msg, "The onStart() event");
            }

            /** Called when the activity has become visible. */
            @Override
            protected void onResume() {
                super.onResume();
                Log.d(msg, "The onResume() event");
            }

            /** Called when another activity is taking focus. */
            @Override
            protected void onPause() {
                super.onPause();
                Log.d(msg, "The onPause() event");
            }

            /** Called when the activity is no longer visible. */
            @Override
            protected void onStop() {
                super.onStop();
                Log.d(msg, "The onStop() event");
            }

            /** Called just before the activity is destroyed. */
            @Override
            public void onDestroy() {
                super.onDestroy();
                Log.d(msg, "The onDestroy() event");
            }
            }

            An activity class loads all the UI component 
            using the XML file available in res/layout folder of the project.
            Following statement loads UI components from res/layout/activity_main.xml file:

            setContentView(R.layout.activity_main);
        2- AndroidManifest.xml
            Every activity you define for your application must be declared in your AndroidManifest.xml file
            and the main activity for your app must be declared in the manifest with an <intent-filter> 
            that includes the MAIN action and LAUNCHER category as follows:

            <manifest xmlns:android="http://schemas.android.com/apk/res/android"
            package="com.example.helloworld"
            android:versionCode="1"
            android:versionName="1.0" >
            
            <uses-sdk
                android:minSdkVersion="8"
                android:targetSdkVersion="22" />
            
            <application
                android:icon="@drawable/ic_launcher"
                android:label="@string/app_name"
                android:theme="@style/AppTheme" >
                
                <activity
                    android:name=".MainActivity"
                    android:label="@string/title_activity_main" >
                    
                    <intent-filter>
                        <action android:name="android.intent.action.MAIN" />
                        <category android:name="android.intent.category.LAUNCHER"/>
                    </intent-filter>
                    
                </activity>
                
            </application>
            </manifest>

            If either the MAIN action or LAUNCHER category are not declared for one of your activities,
            then your app icon will not appear in the Home screen's list of apps.



        3- Bulding UI
            -Create a Linear Layout
                -open main activity in android studio
                    In Android Studio's >Project window> open app > res > layout > activity_main.xml.

                    This XML file defines the layout of your activity.
                    It contains the default "Hello World" text view.
                    
                    When you open a layout file, you’re first shown the design editor in the Layout Editor. 
                    but you can work directly with the XML.

                    so click the Text tab at the bottom of the window to switch to the text editor.
                    Delete everything and insert the following XML:

                    <?xml version="1.0" encoding="utf-8"?>
                    <LinearLayout
                        xmlns:android="http://schemas.android.com/apk/res/android"
                        xmlns:tools="http://schemas.android.com/tools"
                        android:layout_width="match_parent"
                        android:layout_height="match_parent"
                        android:orientation="horizontal">
                    </LinearLayout>

                -LinearLayout 
                    :is a view group (a subclass of ViewGroup) 
                    that lays out child views in either a vertical or horizontal orientation,
                        as specified by the android:orientation attribute.
                    
                        Each child of a LinearLayout appears on the screen in the order in which it appears in the XML.
            
                    Because the LinearLayout is the root view in the layout,
                    it should fill the entire screen area that's available to the app
                    by setting the width and height to "match_parent".
                    This value declares that the view should expand its width or height 
                    to match the width or height of the parent view.

            -Add a Text Field

                In the activity_main.xml file, within the <LinearLayout> element,
                    add the following <EditText> element:

                <LinearLayout
                    xmlns:android="http://schemas.android.com/apk/res/android"
                    xmlns:tools="http://schemas.android.com/tools"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent"
                    android:orientation="horizontal">

                    <EditText android:id="@+id/edit_message"
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:hint="@string/edit_message" />
                </LinearLayout>

                Don't worry about the error that appears for @string/edit_message; you'll fix that soon.

                Here is a description of the attributes in the <EditText> you added:

                android:id
                    This provides a unique identifier for the view,
                        which you can use to reference the object from your app code,
                        such as to read and manipulate the object (you'll see this in the next lesson).

                    The at sign (@) is required when you're referring to any resource object from XML.
                        It is followed by the resource type (id in this case), a slash, 
                        then the resource name (edit_message).
                    
                    Resource Objects

                        A resource object is a unique integer name that's associated with an app resource,
                        such as a bitmap, layout file, or string.

                        Every resource has a corresponding resource object defined in your project's R.java file. 
                        You can use the object names in the R class to refer to your resources,
                        such as when you need to specify a string value for the android:hint attribute. 
                        You can also create arbitrary resource IDs that you associate with a view using the android:id 
                        attribute, which allows you to reference that view from other code.

                        The SDK tools generate the R.java file each time you compile your app. 
                        You should never modify this file by hand.


                    The plus sign (+) before the resource type is needed only 
                    when you're defining a resource ID for the first time.
                        When you compile the app, the SDK tools use the ID name to create a new resource ID 
                        in your project's R.java file that refers to the EditText element. 
                        With the resource ID declared once this way, other references to the ID do not need the plus sign.
                        Using the plus sign is necessary only when specifying a new resource ID 
                        and not needed for concrete resources such as strings or layouts.
                
                android:layout_width and android:layout_height
                    Instead of using specific sizes for the width and height, the "wrap_content" value specifies that the view should be only as big as needed to fit the contents of the view. If you were to instead use "match_parent", then the EditText element would fill the screen, because it would match the size of the parent LinearLayout. For more information, see the Layouts guide.
                android:hint
                    This is a default string to display when the text field is empty.
                    Instead of using a hard-coded string as the value, the "@string/edit_message" value 
                    refers to a string resource defined in a separate file. 
                    Because this refers to a concrete resource (not just an identifier), 
                    it does not need the plus sign. However, because you haven't defined the string resource yet
                    , you’ll see a compiler error at first. 
                    You'll fix this in the next section by defining the string.

                    Note: This string resource has the same name as the element ID: edit_message.
                    However, references to resources are always scoped by the resource type (such as id or string),
                        so using the same name does not cause collisions.

            -Add String Resources(strings.xml)

                By default, your Android project includes a string resource file at res > values > strings.xml.
                Here, you'll add two new strings.

                    From the Project window, open res > values > strings.xml.
                    Add two strings so that your file looks like this:

                    <?xml version="1.0" encoding="utf-8"?>
                    <resources>
                        <string name="app_name">My First App</string>
                        <string name="edit_message">Enter a message</string>
                        <string name="button_send">Send</string>
                    </resources>

                For text in the user interface, always specify each string as a resource. 
                String resources allow you to manage all UI text in a single location, 
                which makes the text easier to find and update. 
                
                Externalizing the strings also allows you to localize your app to different languages
                by providing alternative definitions for each string resource.

            -Add a Button

                Go back to the activity_main.xml file and add a button after the <EditText>.
                Your file should look like this:

                <LinearLayout
                    xmlns:android="http://schemas.android.com/apk/res/android"
                    xmlns:tools="http://schemas.android.com/tools"
                    android:orientation="horizontal"
                    android:layout_width="match_parent"
                    android:layout_height="match_parent">
                        <EditText android:id="@+id/edit_message"
                            android:layout_width="wrap_content"
                            android:layout_height="wrap_content"
                            android:hint="@string/edit_message" />
                        <Button
                            android:layout_width="wrap_content"
                            android:layout_height="wrap_content"
                            android:text="@string/button_send" />
                </LinearLayout>

                Note: This button doesn't need the android:id attribute,
                    because it won't be referenced from the activity code.
            -Respond to the Send Button
                In the file res > layout > activity_main.xml, 
                add the android:onClick attribute to the <Button> element as shown below:

                <Button
                        android:layout_width="wrap_content"
                        android:layout_height="wrap_content"
                        android:text="@string/button_send"
                        android:onClick="sendMessage" />
                    

                This attribute tells the system to call the sendMessage() method in your activity 
                whenever a user clicks on the button.
                In the file java > com.example.myfirstapp > MainActivity.java, 
                add the sendMessage() method stub as shown below:

                public class MainActivity extends AppCompatActivity {
                    @Override
                    protected void onCreate(Bundle savedInstanceState) {
                            super.onCreate(savedInstanceState);
                            setContentView(R.layout.activity_main);
                    }

                    /** Called when the user clicks the Send button */
                    public void sendMessage(View view) {
                            // Do something in response to button
                    }
                }

                In order for the system to match this method to the method name given to android:onClick,
                the signature must be exactly as shown. 
                Specifically, the method must:
                    -Be public
                    -Have a void return value
                    -Have a View as the only parameter (this will be the View that was clicked)

                Next, you’ll fill in this method to read the contents of the text field 
                and deliver that text to another activity.
            -Build an Intent

                :Intent 
                    is an object that provides runtime binding between separate components
                        (such as two activities). 
                    The Intent represents an app’s "intent to do something."
                    You can use intents for a wide variety of tasks, 
                    but in this walkthrough, your intent starts another activity.

                In MainActivity.java, add the code shown below to sendMessage():

                public class MainActivity extends AppCompatActivity {
                    public final static String EXTRA_MESSAGE = "com.example.myfirstapp.MESSAGE";
                    @Override
                    protected void onCreate(Bundle savedInstanceState) {
                        super.onCreate(savedInstanceState);
                        setContentView(R.layout.activity_main);
                    }

                    /** Called when the user clicks the Send button */
                    public void sendMessage(View view) {
                        Intent intent = new Intent(this, DisplayMessageActivity.class);
                        EditText editText = (EditText) findViewById(R.id.edit_message);
                        String message = editText.getText().toString();
                        intent.putExtra(EXTRA_MESSAGE, message);
                        startActivity(intent);
                    }
                }

                - Android Studio's "import class" functionality
                    by pressing Alt + Enter (or Option + Return on Mac). 
                    Your imports should end up as the following:

                        import android.content.Intent;
                        import android.support.v7.app.AppCompatActivity;
                        import android.os.Bundle;
                        import android.view.View;
                        import android.widget.EditText;

                (An error remains for DisplayMessageActivity, but that's okay; you'll fix that in the next section.)

                -The Intent constructor takes two parameters:

                    A Context as its first parameter 
                        (this is used because the Activity class is a subclass of Context)
                    The Class of the app component to which the system should deliver the Intent
                        (in this case, the activity that should be started).

                    Note: The reference to DisplayMessageActivity will raise an error in Android Studio 
                    because the class doesn’t exist yet. Ignore the error for now; .

                -The putExtra() method 
                    :adds the EditText's value to the intent. 
                    -Extras
                        :An Intent can carry data types as key-value pairs called extras. 
                    
                    Your key is a public constant EXTRA_MESSAGE 
                    because the next activity uses the key to retrive the text value.
                    It's a good practice to define keys for intent extras using your app's package name as a prefix.
                    This ensures the keys are unique, in case your app interacts with other apps.

                The startActivity() method 
                    starts an instance of the DisplayMessageActivity specified by the Intent. 
                    Now you need to create the class.

            -Create the Second Activity
                    In the Project window > right-click the app folder > select New > Activity > Empty Activity.
                    In the Configure Activity window, 
                    enter "DisplayMessageActivity" for Activity Name and click Finish

                Android Studio automatically does three things:

                    -Creates the class DisplayMessageActivity.java 
                        with an implementation of the required onCreate() method.
                    -Creates the corresponding layout file activity_display_message.xml
                    -Adds the required <activity> element in AndroidManifest.xml. 

                If you run the app and click the Send button on the first activity, 
                the second activity starts but is empty. 
                This is because the second activity uses the default empty layout provided by the template.
            -Display the Message

                Now you will modify the second activity to display the message 
                that was passed by the first activity.

                In DisplayMessageActivity.java,
                    add the following code to the onCreate() method:

                    @Override
                    protected void onCreate(Bundle savedInstanceState) {
                        super.onCreate(savedInstanceState);
                        setContentView(R.layout.activity_display_message);

                        Intent intent = getIntent();
                        String message = intent.getStringExtra(MainActivity.EXTRA_MESSAGE);
                        TextView textView = new TextView(this);
                        textView.setTextSize(40);
                        textView.setText(message);

                        ViewGroup layout = (ViewGroup) findViewById(R.id.activity_display_message);
                        layout.addView(textView);
                    }

                    Press Alt + Enter (or Option + Return on Mac) to import missing classes.
                        Your imports should end up as the following:

                        import android.content.Intent;
                        import android.support.v7.app.AppCompatActivity;
                        import android.os.Bundle;
                        import android.view.ViewGroup;
                        import android.widget.TextView;

                    
                    The call getIntent() 
                        grabs the intent that started the activity. 
                        Every Activity is invoked by an Intent, regardless of how the user navigated there. 
                        The call getStringExtra() retrieves the data from the first activity.
                    You programmatically create a TextView and set its size and message.
                    You add the TextView to the layout identified by R.id.activity_display_message. 
                    You cast the layout to ViewGroup because it is the superclass of all layouts 
                    and contains the addView() method.

                Note: The XML layout generated by previous versions of Android Studio might not include 
                the android:id attribute. 
                The call findViewById() will fail if the layout does not have the android:id attribute. 
                If this is the case, open activity_display_message.xml 
                and add the attribute android:id="@+id/activity_display_message" to the layout element.

            -You can now run the app. 
                When it opens, type a message in the text field, and click Send. 
                The second activity replaces the first one on the screen, 
                showing the message you entered in the first activity.

                That's it, you've built your first Android app!
    -Building a Dynamic UI with Fragments
        To create a dynamic and multi-pane user interface on Android,
            you need to encapsulate UI components and activity behaviors into modules 
            that you can swap into and out of your activities. 
            You can create these modules with the Fragment class, 
            which behaves somewhat like a nested activity
            that can define its own layout and manage its own lifecycle.
            
        When a fragment specifies its own layout, it can be configured in different combinations 
        with other fragments inside an activity 
        to modify your layout configuration for different screen sizes
            (a small screen might show one fragment at a time, but a large screen can show two or more).

        This class shows you how to create a dynamic user experience with fragments 
        and optimize your app's user experience for devices with different screen sizes, 
        all while continuing to support devices running versions as old as Android 1.6.

        Creating a Fragment
            You can think of a fragment as a modular section of an activity,
                which has its own lifecycle, receives its own input events, 
                and which you can add or remove while the activity is running
                (sort of like a "sub activity" that you can reuse in different activities).
                This lesson shows how to extend the Fragment class using the Support Library 
                so your app remains compatible with devices running system versions as low as Android 1.6.

            set up your Android project to use the Support Library:
                If you have not used the Support Library before,
                set up your project to use the v4 library by following the Support Library Setup document. 
                However, you can also include the app bar in your activities by
                instead using the v7 appcompat library, 
                which is compatible with Android 2.1 (API level 7) and also includes the Fragment APIs.
            Create a Fragment Class

                To create a fragment, extend the Fragment class, 
                then override key lifecycle methods to insert your app logic, 
                similar to the way you would with an Activity class.

                One difference when creating a Fragment is that you must use the onCreateView() callback 
                to define the layout. 
                In fact, this is the only callback you need in order to get a fragment running. 
                For example, here's a simple fragment that specifies its own layout:

                    import android.os.Bundle;
                    import android.support.v4.app.Fragment;
                    import android.view.LayoutInflater;
                    import android.view.ViewGroup;

                    public class ArticleFragment extends Fragment {
                        @Override
                        public View onCreateView(LayoutInflater inflater, ViewGroup container,
                            Bundle savedInstanceState) {
                            // Inflate the layout for this fragment
                            return inflater.inflate(R.layout.article_view, container, false);
                        }
                    }

                Just like an activity, a fragment should implement other lifecycle callbacks 
                that allow you to manage its state as it is added or removed from the activity 
                and as the activity transitions between its lifecycle states. 
                
                For instance, when the activity's onPause() method is called, 
                any fragments in the activity also receive a call to onPause().

        
            Add a Fragment to an Activity using XML

                While fragments are reusable, modular UI components,
                each instance of a Fragment class must be associated with a parent FragmentActivity. 
                You can achieve this association by defining each fragment within your activity layout XML file.

                Note: FragmentActivity is a special activity provided in the Support Library
                to handle fragments on system versions older than API level 11. 
                If the lowest system version you support is API level 11 or higher, 
                then you can use a regular Activity.

                Here is an example layout file that adds two fragments to an activity 
                when the device screen is considered "large"
                (specified by the large qualifier in the directory name).

                    res/layout-large/news_articles.xml

                    <LinearLayout xmlns:android="http://schemas.android.com/apk/res/android"
                        android:orientation="horizontal"
                        android:layout_width="fill_parent"
                        android:layout_height="fill_parent">

                        <fragment android:name="com.example.android.fragments.HeadlinesFragment"
                                    android:id="@+id/headlines_fragment"
                                    android:layout_weight="1"
                                    android:layout_width="0dp"
                                    android:layout_height="match_parent" />

                        <fragment android:name="com.example.android.fragments.ArticleFragment"
                                    android:id="@+id/article_fragment"
                                    android:layout_weight="2"
                                    android:layout_width="0dp"
                                    android:layout_height="match_parent" />

                    </LinearLayout>

        

                Then apply the layout to your activity:

                    import android.os.Bundle;
                    import android.support.v4.app.FragmentActivity;

                    public class MainActivity extends FragmentActivity {
                        @Override
                        public void onCreate(Bundle savedInstanceState) {
                            super.onCreate(savedInstanceState);
                            setContentView(R.layout.news_articles);
                        }
                    }

                If you're using the v7 appcompat library, your activity should instead extend AppCompatActivity, 
                which is a subclass of FragmentActivity.
                

                Note: When you add a fragment to an activity layout by defining the fragment in the layout XML file, 
                you cannot remove the fragment at runtime. 
                If you plan to swap your fragments in and out during user interaction, 
                you must add the fragment to the activity when the activity first starts.
        Building a Flexible UI
            When designing your application to support a wide range of screen sizes, you can reuse your fragments in different layout configurations to optimize the user experience based on the available screen space.
            For example, on a handset device it might be appropriate to display just one fragment at a time for a single-pane user interface. Conversely, you may want to set fragments side-by-side on a tablet which has a wider screen size to display more information to the user.
            Figure 1. Two fragments, displayed in different configurations for the same activity on different screen sizes. On a large screen, both fragments fit side by side, but on a handset device, only one fragment fits at a time so the fragments must replace each other as the user navigates.
            The FragmentManager class provides methods that allow you to add, remove, and replace fragments to an activity at runtime in order to create a dynamic experience.
            Add a Fragment to an Activity at Runtime

            Rather than defining the fragments for an activity in the layout file—as shown in the previous lesson with the <fragment> element—you can add a fragment to the activity during the activity runtime. This is necessary if you plan to change fragments during the life of the activity.

            To perform a transaction such as add or remove a fragment, you must use the FragmentManager to create a FragmentTransaction, which provides APIs to add, remove, replace, and perform other fragment transactions.

            If your activity allows the fragments to be removed and replaced, you should add the initial fragment(s) to the activity during the activity's onCreate() method.

            An important rule when dealing with fragments—especially when adding fragments at runtime—is that your activity layout must include a container View in which you can insert the fragment.

            The following layout is an alternative to the layout shown in the previous lesson that shows only one fragment at a time. In order to replace one fragment with another, the activity's layout includes an empty FrameLayout that acts as the fragment container.

            Notice that the filename is the same as the layout file in the previous lesson, but the layout directory does not have the large qualifier, so this layout is used when the device screen is smaller than large because the screen does not fit both fragments at the same time.

            res/layout/news_articles.xml:

            <FrameLayout xmlns:android="http://schemas.android.com/apk/res/android"
                android:id="@+id/fragment_container"
                android:layout_width="match_parent"
                android:layout_height="match_parent" />

            Inside your activity, call getSupportFragmentManager() to get a FragmentManager using the Support Library APIs. Then call beginTransaction() to create a FragmentTransaction and call add() to add a fragment.

            You can perform multiple fragment transaction for the activity using the same FragmentTransaction. When you're ready to make the changes, you must call commit().

            For example, here's how to add a fragment to the previous layout:

            import android.os.Bundle;
            import android.support.v4.app.FragmentActivity;

            public class MainActivity extends FragmentActivity {
                @Override
                public void onCreate(Bundle savedInstanceState) {
                    super.onCreate(savedInstanceState);
                    setContentView(R.layout.news_articles);

                    // Check that the activity is using the layout version with
                    // the fragment_container FrameLayout
                    if (findViewById(R.id.fragment_container) != null) {

                            // However, if we're being restored from a previous state,
                            // then we don't need to do anything and should return or else
                            // we could end up with overlapping fragments.
                            if (savedInstanceState != null) {
                                return;
                            }

                            // Create a new Fragment to be placed in the activity layout
                            HeadlinesFragment firstFragment = new HeadlinesFragment();

                            // In case this activity was started with special instructions from an
                            // Intent, pass the Intent's extras to the fragment as arguments
                            firstFragment.setArguments(getIntent().getExtras());

                            // Add the fragment to the 'fragment_container' FrameLayout
                            getSupportFragmentManager().beginTransaction()
                                    .add(R.id.fragment_container, firstFragment).commit();
                    }
                }
            }

            Because the fragment has been added to the FrameLayout container at runtime—instead of defining it in the activity's layout with a <fragment> element—the activity can remove the fragment and replace it with a different one.
            Replace One Fragment with Another

            The procedure to replace a fragment is similar to adding one, but requires the replace() method instead of add().

            Keep in mind that when you perform fragment transactions, such as replace or remove one, it's often appropriate to allow the user to navigate backward and "undo" the change. To allow the user to navigate backward through the fragment transactions, you must call addToBackStack() before you commit the FragmentTransaction.

            Note: When you remove or replace a fragment and add the transaction to the back stack, the fragment that is removed is stopped (not destroyed). If the user navigates back to restore the fragment, it restarts. If you do not add the transaction to the back stack, then the fragment is destroyed when removed or replaced.

            Example of replacing one fragment with another:

            // Create fragment and give it an argument specifying the article it should show
            ArticleFragment newFragment = new ArticleFragment();
            Bundle args = new Bundle();
            args.putInt(ArticleFragment.ARG_POSITION, position);
            newFragment.setArguments(args);

            FragmentTransaction transaction = getSupportFragmentManager().beginTransaction();

            // Replace whatever is in the fragment_container view with this fragment,
            // and add the transaction to the back stack so the user can navigate back
            transaction.replace(R.id.fragment_container, newFragment);
            transaction.addToBackStack(null);

            // Commit the transaction
            transaction.commit();

            The addToBackStack() method takes an optional string parameter that specifies a unique name for the transaction. The name isn't needed unless you plan to perform advanced fragment operations using the FragmentManager.BackStackEntry APIs.
        Communicating with Other Fragments
            In order to reuse the Fragment UI components, you should build each as a completely self-contained, modular component that defines its own layout and behavior. Once you have defined these reusable Fragments, you can associate them with an Activity and connect them with the application logic to realize the overall composite UI.

                Often you will want one Fragment to communicate with another, for example to change the content based on a user event. All Fragment-to-Fragment communication is done through the associated Activity. Two Fragments should never communicate directly.
                Define an Interface

                To allow a Fragment to communicate up to its Activity, you can define an interface in the Fragment class and implement it within the Activity. The Fragment captures the interface implementation during its onAttach() lifecycle method and can then call the Interface methods in order to communicate with the Activity.

                Here is an example of Fragment to Activity communication:

                public class HeadlinesFragment extends ListFragment {
                    OnHeadlineSelectedListener mCallback;

                    // Container Activity must implement this interface
                    public interface OnHeadlineSelectedListener {
                        public void onArticleSelected(int position);
                    }

                    @Override
                    public void onAttach(Activity activity) {
                        super.onAttach(activity);

                        // This makes sure that the container activity has implemented
                        // the callback interface. If not, it throws an exception
                        try {
                                mCallback = (OnHeadlineSelectedListener) activity;
                        } catch (ClassCastException e) {
                                throw new ClassCastException(activity.toString()
                                        + " must implement OnHeadlineSelectedListener");
                        }
                    }

                    ...
                }

                Now the fragment can deliver messages to the activity by calling the onArticleSelected() method (or other methods in the interface) using the mCallback instance of the OnHeadlineSelectedListener interface.

                For example, the following method in the fragment is called when the user clicks on a list item. The fragment uses the callback interface to deliver the event to the parent activity.

                    @Override
                    public void onListItemClick(ListView l, View v, int position, long id) {
                        // Send the event to the host activity
                        mCallback.onArticleSelected(position);
                    }

                Implement the Interface

                In order to receive event callbacks from the fragment, the activity that hosts it must implement the interface defined in the fragment class.

                For example, the following activity implements the interface from the above example.

                public static class MainActivity extends Activity
                        implements HeadlinesFragment.OnHeadlineSelectedListener{
                    ...

                    public void onArticleSelected(int position) {
                        // The user selected the headline of an article from the HeadlinesFragment
                        // Do something here to display that article
                    }
                }

                Deliver a Message to a Fragment

                The host activity can deliver messages to a fragment by capturing the Fragment instance with findFragmentById(), then directly call the fragment's public methods.

                For instance, imagine that the activity shown above may contain another fragment that's used to display the item specified by the data returned in the above callback method. In this case, the activity can pass the information received in the callback method to the other fragment that will display the item:

                public static class MainActivity extends Activity
                        implements HeadlinesFragment.OnHeadlineSelectedListener{
                    ...

                    public void onArticleSelected(int position) {
                        // The user selected the headline of an article from the HeadlinesFragment
                        // Do something here to display that article

                        ArticleFragment articleFrag = (ArticleFragment)
                                    getSupportFragmentManager().findFragmentById(R.id.article_fragment);

                        if (articleFrag != null) {
                                // If article frag is available, we're in two-pane layout...

                                // Call a method in the ArticleFragment to update its content
                                articleFrag.updateArticleView(position);
                        } else {
                                // Otherwise, we're in the one-pane layout and must swap frags...

                                // Create fragment and give it an argument for the selected article
                                ArticleFragment newFragment = new ArticleFragment();
                                Bundle args = new Bundle();
                                args.putInt(ArticleFragment.ARG_POSITION, position);
                                newFragment.setArguments(args);

                                FragmentTransaction transaction = getSupportFragmentManager().beginTransaction();

                                // Replace whatever is in the fragment_container view with this fragment,
                                // and add the transaction to the back stack so the user can navigate back
                                transaction.replace(R.id.fragment_container, newFragment);
                                transaction.addToBackStack(null);

                                // Commit the transaction
                                transaction.commit();
                        }
                    }
                }
        -Saving Data
            Most Android apps need to save data, even if only to save information about the app state during onPause() so the user's progress is not lost. Most non-trivial apps also need to save user settings, and some apps must manage large amounts of information in files and databases. This class introduces you to the principal data storage options in Android, including:

            Saving key-value pairs of simple data types in a shared preferences file
            Saving arbitrary files in Android's file system
            Using databases managed by SQLite
            -Saving Key-Value Sets
                If you have a relatively small collection of key-values that you'd like to save, you should use the SharedPreferences APIs. A SharedPreferences object points to a file containing key-value pairs and provides simple methods to read and write them. Each SharedPreferences file is managed by the framework and can be private or shared.

                Note: The SharedPreferences APIs are only for reading and writing key-value pairs and you should not confuse them with the Preference APIs, which help you build a user interface for your app settings (although they use SharedPreferences as their implementation to save the app settings). For information about using the Preference APIs, see the Settings guide.
                Get a Handle to a SharedPreferences

                You can create a new shared preference file or access an existing one by calling one of two methods:

                    getSharedPreferences() — Use this if you need multiple shared preference files identified by name, which you specify with the first parameter. You can call this from any Context in your app.
                    getPreferences() — Use this from an Activity if you need to use only one shared preference file for the activity. Because this retrieves a default shared preference file that belongs to the activity, you don't need to supply a name.

                For example, the following code is executed inside a Fragment. It accesses the shared preferences file that's identified by the resource string R.string.preference_file_key and opens it using the private mode so the file is accessible by only your app.

                Context context = getActivity();
                SharedPreferences sharedPref = context.getSharedPreferences(
                        getString(R.string.preference_file_key), Context.MODE_PRIVATE);

                When naming your shared preference files, you should use a name that's uniquely identifiable to your app, such as "com.example.myapp.PREFERENCE_FILE_KEY"

                Alternatively, if you need just one shared preference file for your activity, you can use the getPreferences() method:

                SharedPreferences sharedPref = getActivity().getPreferences(Context.MODE_PRIVATE);

                Caution: If you create a shared preferences file with MODE_WORLD_READABLE or MODE_WORLD_WRITEABLE, then any other apps that know the file identifier can access your data.
                Write to Shared Preferences

                To write to a shared preferences file, create a SharedPreferences.Editor by calling edit() on your SharedPreferences.

                Pass the keys and values you want to write with methods such as putInt() and putString(). Then call commit() to save the changes. For example:

                SharedPreferences sharedPref = getActivity().getPreferences(Context.MODE_PRIVATE);
                SharedPreferences.Editor editor = sharedPref.edit();
                editor.putInt(getString(R.string.saved_high_score), newHighScore);
                editor.commit();

                Read from Shared Preferences

                To retrieve values from a shared preferences file, call methods such as getInt() and getString(), providing the key for the value you want, and optionally a default value to return if the key isn't present. For example:

                SharedPreferences sharedPref = getActivity().getPreferences(Context.MODE_PRIVATE);
                int defaultValue = getResources().getInteger(R.string.saved_high_score_default);
                long highScore = sharedPref.getInt(getString(R.string.saved_high_score), defaultValue);
        -Saving Files
            Android uses a file system that's similar to disk-based file systems on other platforms. This lesson describes how to work with the Android file system to read and write files with the File APIs.

            A File object is suited to reading or writing large amounts of data in start-to-finish order without skipping around. For example, it's good for image files or anything exchanged over a network.

            This lesson shows how to perform basic file-related tasks in your app. The lesson assumes that you are familiar with the basics of the Linux file system and the standard file input/output APIs in java.io.
            Choose Internal or External Storage

            All Android devices have two file storage areas: "internal" and "external" storage. These names come from the early days of Android, when most devices offered built-in non-volatile memory (internal storage), plus a removable storage medium such as a micro SD card (external storage). Some devices divide the permanent storage space into "internal" and "external" partitions, so even without a removable storage medium, there are always two storage spaces and the API behavior is the same whether the external storage is removable or not. The following lists summarize the facts about each storage space.

            Internal storage:

                It's always available.
                Files saved here are accessible by only your app.
                When the user uninstalls your app, the system removes all your app's files from internal storage.

            Internal storage is best when you want to be sure that neither the user nor other apps can access your files.

            External storage:

                It's not always available, because the user can mount the external storage as USB storage and in some cases remove it from the device.
                It's world-readable, so files saved here may be read outside of your control.
                When the user uninstalls your app, the system removes your app's files from here only if you save them in the directory from getExternalFilesDir().

            External storage is the best place for files that don't require access restrictions and for files that you want to share with other apps or allow the user to access with a computer.

                            Note: Before Android N, internal files could be made accessible to other apps by means of relaxing file system permissions. This is no longer the case. If you wish to make the content of a private file accessible to other apps, your app may use the FileProvider. See Sharing Files.

                            Tip: Although apps are installed onto the internal storage by default, you can specify the android:installLocation attribute in your manifest so your app may be installed on external storage. Users appreciate this option when the APK size is very large and they have an external storage space that's larger than the internal storage. For more information, see App Install Location.
                            Obtain Permissions for External Storage

                            To write to the external storage, you must request the WRITE_EXTERNAL_STORAGE permission in your manifest file:

                            <manifest ...>
                                <uses-permission android:name="android.permission.WRITE_EXTERNAL_STORAGE" />
                                ...
                            </manifest>

                            Caution: Currently, all apps have the ability to read the external storage without a special permission. However, this will change in a future release. If your app needs to read the external storage (but not write to it), then you will need to declare the READ_EXTERNAL_STORAGE permission. To ensure that your app continues to work as expected, you should declare this permission now, before the change takes effect.

                            <manifest ...>
                                <uses-permission android:name="android.permission.READ_EXTERNAL_STORAGE" />
                                ...
                            </manifest>

                            However, if your app uses the WRITE_EXTERNAL_STORAGE permission, then it implicitly has permission to read the external storage as well.

                            You don’t need any permissions to save files on the internal storage. Your application always has permission to read and write files in its internal storage directory.
                            Save a File on Internal Storage

                            When saving a file to internal storage, you can acquire the appropriate directory as a File by calling one of two methods:

                            getFilesDir()
                                Returns a File representing an internal directory for your app.
                            getCacheDir()
                                Returns a File representing an internal directory for your app's temporary cache files. Be sure to delete each file once it is no longer needed and implement a reasonable size limit for the amount of memory you use at any given time, such as 1MB. If the system begins running low on storage, it may delete your cache files without warning.

                            To create a new file in one of these directories, you can use the File() constructor, passing the File provided by one of the above methods that specifies your internal storage directory. For example:

                            File file = new File(context.getFilesDir(), filename);

                            Alternatively, you can call openFileOutput() to get a FileOutputStream that writes to a file in your internal directory. For example, here's how to write some text to a file:

                            String filename = "myfile";
                            String string = "Hello world!";
                            FileOutputStream outputStream;

                            try {
                            outputStream = openFileOutput(filename, Context.MODE_PRIVATE);
                            outputStream.write(string.getBytes());
                            outputStream.close();
                            } catch (Exception e) {
                            e.printStackTrace();
                            }

                            Or, if you need to cache some files, you should instead use createTempFile(). For example, the following method extracts the file name from a URL and creates a file with that name in your app's internal cache directory:

                            public File getTempFile(Context context, String url) {
                                File file;
                                try {
                                    String fileName = Uri.parse(url).getLastPathSegment();
                                    file = File.createTempFile(fileName, null, context.getCacheDir());
                                } catch (IOException e) {
                                    // Error while creating file
                                }
                                return file;
                            }

                            Note: Your app's internal storage directory is specified by your app's package name in a special location of the Android file system. Technically, another app can read your internal files if you set the file mode to be readable. However, the other app would also need to know your app package name and file names. Other apps cannot browse your internal directories and do not have read or write access unless you explicitly set the files to be readable or writable. So as long as you use MODE_PRIVATE for your files on the internal storage, they are never accessible to other apps.
                            Save a File on External Storage

                            Because the external storage may be unavailable—such as when the user has mounted the storage to a PC or has removed the SD card that provides the external storage—you should always verify that the volume is available before accessing it. You can query the external storage state by calling getExternalStorageState(). If the returned state is equal to MEDIA_MOUNTED, then you can read and write your files. For example, the following methods are useful to determine the storage availability:

                            /* Checks if external storage is available for read and write */
                            public boolean isExternalStorageWritable() {
                                String state = Environment.getExternalStorageState();
                                if (Environment.MEDIA_MOUNTED.equals(state)) {
                                    return true;
                                }
                                return false;
                            }

                            /* Checks if external storage is available to at least read */
                            public boolean isExternalStorageReadable() {
                                String state = Environment.getExternalStorageState();
                                if (Environment.MEDIA_MOUNTED.equals(state) ||
                                    Environment.MEDIA_MOUNTED_READ_ONLY.equals(state)) {
                                    return true;
                                }
                                return false;
                            }

                            Although the external storage is modifiable by the user and other apps, there are two categories of files you might save here:

                            Public files
                                Files that should be freely available to other apps and to the user. When the user uninstalls your app, these files should remain available to the user.

                                For example, photos captured by your app or other downloaded files.
                            Private files
                                Files that rightfully belong to your app and should be deleted when the user uninstalls your app. Although these files are technically accessible by the user and other apps because they are on the external storage, they are files that realistically don't provide value to the user outside your app. When the user uninstalls your app, the system deletes all files in your app's external private directory.

                                For example, additional resources downloaded by your app or temporary media files.

                            If you want to save public files on the external storage, use the getExternalStoragePublicDirectory() method to get a File representing the appropriate directory on the external storage. The method takes an argument specifying the type of file you want to save so that they can be logically organized with other public files, such as DIRECTORY_MUSIC or DIRECTORY_PICTURES. For example:

                            public File getAlbumStorageDir(String albumName) {
                                // Get the directory for the user's public pictures directory.
                                File file = new File(Environment.getExternalStoragePublicDirectory(
                                            Environment.DIRECTORY_PICTURES), albumName);
                                if (!file.mkdirs()) {
                                    Log.e(LOG_TAG, "Directory not created");
                                }
                                return file;
                            }

                            If you want to save files that are private to your app, you can acquire the appropriate directory by calling getExternalFilesDir() and passing it a name indicating the type of directory you'd like. Each directory created this way is added to a parent directory that encapsulates all your app's external storage files, which the system deletes when the user uninstalls your app.

                            For example, here's a method you can use to create a directory for an individual photo album:

                            public File getAlbumStorageDir(Context context, String albumName) {
                                // Get the directory for the app's private pictures directory.
                                File file = new File(context.getExternalFilesDir(
                                            Environment.DIRECTORY_PICTURES), albumName);
                                if (!file.mkdirs()) {
                                    Log.e(LOG_TAG, "Directory not created");
                                }
                                return file;
                            }

                            If none of the pre-defined sub-directory names suit your files, you can instead call getExternalFilesDir() and pass null. This returns the root directory for your app's private directory on the external storage.

                            Remember that getExternalFilesDir() creates a directory inside a directory that is deleted when the user uninstalls your app. If the files you're saving should remain available after the user uninstalls your app—such as when your app is a camera and the user will want to keep the photos—you should instead use getExternalStoragePublicDirectory().

                            Regardless of whether you use getExternalStoragePublicDirectory() for files that are shared or getExternalFilesDir() for files that are private to your app, it's important that you use directory names provided by API constants like DIRECTORY_PICTURES. These directory names ensure that the files are treated properly by the system. For instance, files saved in DIRECTORY_RINGTONES are categorized by the system media scanner as ringtones instead of music.
                            Query Free Space

                            If you know ahead of time how much data you're saving, you can find out whether sufficient space is available without causing an IOException by calling getFreeSpace() or getTotalSpace(). These methods provide the current available space and the total space in the storage volume, respectively. This information is also useful to avoid filling the storage volume above a certain threshold.

                            However, the system does not guarantee that you can write as many bytes as are indicated by getFreeSpace(). If the number returned is a few MB more than the size of the data you want to save, or if the file system is less than 90% full, then it's probably safe to proceed. Otherwise, you probably shouldn't write to storage.

                            Note: You aren't required to check the amount of available space before you save your file. You can instead try writing the file right away, then catch an IOException if one occurs. You may need to do this if you don't know exactly how much space you need. For example, if you change the file's encoding before you save it by converting a PNG image to JPEG, you won't know the file's size beforehand.
                            Delete a File

                            You should always delete files that you no longer need. The most straightforward way to delete a file is to have the opened file reference call delete() on itself.

                            myFile.delete();

                            If the file is saved on internal storage, you can also ask the Context to locate and delete a file by calling deleteFile():

                            myContext.deleteFile(fileName);

                            Note: When the user uninstalls your app, the Android system deletes the following:

                                All files you saved on internal storage
                                All files you saved on external storage using getExternalFilesDir().

                            However, you should manually delete all cached files created with getCacheDir() on a regular basis and also regularly delete other files you no longer need.
                        -Saving Data in SQL Databases
                            Saving data to a database is ideal for repeating or structured data, such as contact information. This class assumes that you are familiar with SQL databases in general and helps you get started with SQLite databases on Android. The APIs you'll need to use a database on Android are available in the android.database.sqlite package.
                            Define a Schema and Contract

                            One of the main principles of SQL databases is the schema: a formal declaration of how the database is organized. The schema is reflected in the SQL statements that you use to create your database. You may find it helpful to create a companion class, known as a contract class, which explicitly specifies the layout of your schema in a systematic and self-documenting way.

                            A contract class is a container for constants that define names for URIs, tables, and columns. The contract class allows you to use the same constants across all the other classes in the same package. This lets you change a column name in one place and have it propagate throughout your code.

                            A good way to organize a contract class is to put definitions that are global to your whole database in the root level of the class. Then create an inner class for each table that enumerates its columns.

                            Note: By implementing the BaseColumns interface, your inner class can inherit a primary key field called _ID that some Android classes such as cursor adaptors will expect it to have. It's not required, but this can help your database work harmoniously with the Android framework.

                            For example, this snippet defines the table name and column names for a single table:

                            public final class FeedReaderContract {
                                // To prevent someone from accidentally instantiating the contract class,
                                // make the constructor private.
                                private FeedReaderContract() {}

                                /* Inner class that defines the table contents */
                                public static class FeedEntry implements BaseColumns {
                                    public static final String TABLE_NAME = "entry";
                                    public static final String COLUMN_NAME_TITLE = "title";
                                    public static final String COLUMN_NAME_SUBTITLE = "subtitle";
                                }
                            }

                            Create a Database Using a SQL Helper

                            Once you have defined how your database looks, you should implement methods that create and maintain the database and tables. Here are some typical statements that create and delete a table:

                            private static final String TEXT_TYPE = " TEXT";
                            private static final String COMMA_SEP = ",";
                            private static final String SQL_CREATE_ENTRIES =
                                "CREATE TABLE " + FeedEntry.TABLE_NAME + " (" +
                                FeedEntry._ID + " INTEGER PRIMARY KEY," +
                                FeedEntry.COLUMN_NAME_TITLE + TEXT_TYPE + COMMA_SEP +
                                FeedEntry.COLUMN_NAME_SUBTITLE + TEXT_TYPE + " )";

                            private static final String SQL_DELETE_ENTRIES =
                                "DROP TABLE IF EXISTS " + FeedEntry.TABLE_NAME;

                            Just like files that you save on the device's internal storage, Android stores your database in private disk space that's associated application. Your data is secure, because by default this area is not accessible to other applications.

                            A useful set of APIs is available in the SQLiteOpenHelper class. When you use this class to obtain references to your database, the system performs the potentially long-running operations of creating and updating the database only when needed and not during app startup. All you need to do is call getWritableDatabase() or getReadableDatabase().

                            Note: Because they can be long-running, be sure that you call getWritableDatabase() or getReadableDatabase() in a background thread, such as with AsyncTask or IntentService.

                            To use SQLiteOpenHelper, create a subclass that overrides the onCreate(), onUpgrade() and onOpen() callback methods. You may also want to implement onDowngrade(), but it's not required.

                            For example, here's an implementation of SQLiteOpenHelper that uses some of the commands shown above:

                            public class FeedReaderDbHelper extends SQLiteOpenHelper {
                                // If you change the database schema, you must increment the database version.
                                public static final int DATABASE_VERSION = 1;
                                public static final String DATABASE_NAME = "FeedReader.db";

                                public FeedReaderDbHelper(Context context) {
                                    super(context, DATABASE_NAME, null, DATABASE_VERSION);
                                }
                                public void onCreate(SQLiteDatabase db) {
                                    db.execSQL(SQL_CREATE_ENTRIES);
                                }
                                public void onUpgrade(SQLiteDatabase db, int oldVersion, int newVersion) {
                                    // This database is only a cache for online data, so its upgrade policy is
                                    // to simply to discard the data and start over
                                    db.execSQL(SQL_DELETE_ENTRIES);
                                    onCreate(db);
                                }
                                public void onDowngrade(SQLiteDatabase db, int oldVersion, int newVersion) {
                                    onUpgrade(db, oldVersion, newVersion);
                                }
                            }

                            To access your database, instantiate your subclass of SQLiteOpenHelper:

                            FeedReaderDbHelper mDbHelper = new FeedReaderDbHelper(getContext());

                            Put Information into a Database

                            Insert data into the database by passing a ContentValues object to the insert() method:

                            // Gets the data repository in write mode
                            SQLiteDatabase db = mDbHelper.getWritableDatabase();

                            // Create a new map of values, where column names are the keys
                            ContentValues values = new ContentValues();
                            values.put(FeedEntry.COLUMN_NAME_TITLE, title);
                            values.put(FeedEntry.COLUMN_NAME_SUBTITLE, subtitle);

                            // Insert the new row, returning the primary key value of the new row
                            long newRowId = db.insert(FeedEntry.TABLE_NAME, null, values);

                            The first argument for insert() is simply the table name.

                            The second argument tells the framework what to do in the event that the ContentValues is empty (i.e., you did not put any values). If you specify the name of a column, the framework inserts a row and sets the value of that column to null. If you specify null, like in this code sample, the framework does not insert a row when there are no values.
                            Read Information from a Database

                            To read from a database, use the query() method, passing it your selection criteria and desired columns. The method combines elements of insert() and update(), except the column list defines the data you want to fetch, rather than the data to insert. The results of the query are returned to you in a Cursor object.

                            SQLiteDatabase db = mDbHelper.getReadableDatabase();

                            // Define a projection that specifies which columns from the database
                            // you will actually use after this query.
                            String[] projection = {
                                FeedEntry._ID,
                                FeedEntry.COLUMN_NAME_TITLE,
                                FeedEntry.COLUMN_NAME_SUBTITLE
                                };

                            // Filter results WHERE "title" = 'My Title'
                            String selection = FeedEntry.COLUMN_NAME_TITLE + " = ?";
                            String[] selectionArgs = { "My Title" };

                            // How you want the results sorted in the resulting Cursor
                            String sortOrder =
                                FeedEntry.COLUMN_NAME_SUBTITLE + " DESC";

                            Cursor c = db.query(
                                FeedEntry.TABLE_NAME,                     // The table to query
                                projection,                               // The columns to return
                                selection,                                // The columns for the WHERE clause
                                selectionArgs,                            // The values for the WHERE clause
                                null,                                     // don't group the rows
                                null,                                     // don't filter by row groups
                                sortOrder                                 // The sort order
                                );

                            To look at a row in the cursor, use one of the Cursor move methods, which you must always call before you begin reading values. Generally, you should start by calling moveToFirst(), which places the "read position" on the first entry in the results. For each row, you can read a column's value by calling one of the Cursor get methods, such as getString() or getLong(). For each of the get methods, you must pass the index position of the column you desire, which you can get by calling getColumnIndex() or getColumnIndexOrThrow(). For example:

                            cursor.moveToFirst();
                            long itemId = cursor.getLong(
                                cursor.getColumnIndexOrThrow(FeedEntry._ID)
                            );

                            Delete Information from a Database

                            To delete rows from a table, you need to provide selection criteria that identify the rows. The database API provides a mechanism for creating selection criteria that protects against SQL injection. The mechanism divides the selection specification into a selection clause and selection arguments. The clause defines the columns to look at, and also allows you to combine column tests. The arguments are values to test against that are bound into the clause. Because the result isn't handled the same as a regular SQL statement, it is immune to SQL injection.

                            // Define 'where' part of query.
                            String selection = FeedEntry.COLUMN_NAME_TITLE + " LIKE ?";
                            // Specify arguments in placeholder order.
                            String[] selectionArgs = { "MyTitle" };
                            // Issue SQL statement.
                            db.delete(FeedEntry.TABLE_NAME, selection, selectionArgs);

                            Update a Database

                            When you need to modify a subset of your database values, use the update() method.

                            Updating the table combines the content values syntax of insert() with the where syntax of delete().

                            SQLiteDatabase db = mDbHelper.getReadableDatabase();

                            // New value for one column
                            ContentValues values = new ContentValues();
                            values.put(FeedEntry.COLUMN_NAME_TITLE, title);

                            // Which row to update, based on the title
                            String selection = FeedEntry.COLUMN_NAME_TITLE + " LIKE ?";
                            String[] selectionArgs = { "MyTitle" };

                            int count = db.update(
                                FeedReaderDbHelper.FeedEntry.TABLE_NAME,
                                values,
                                selection,
                                selectionArgs);
                        -Getting a Result from an Activity
                            Starting another activity doesn't have to be one-way. You can also start another activity and receive a result back. To receive a result, call startActivityForResult() (instead of startActivity()).

                            For example, your app can start a camera app and receive the captured photo as a result. Or, you might start the People app in order for the user to select a contact and you'll receive the contact details as a result.

                            Of course, the activity that responds must be designed to return a result. When it does, it sends the result as another Intent object. Your activity receives it in the onActivityResult() callback.

                            Note: You can use explicit or implicit intents when you call startActivityForResult(). When starting one of your own activities to receive a result, you should use an explicit intent to ensure that you receive the expected result.
                            Start the Activity

                            There's nothing special about the Intent object you use when starting an activity for a result, but you do need to pass an additional integer argument to the startActivityForResult() method.

                            The integer argument is a "request code" that identifies your request. When you receive the result Intent, the callback provides the same request code so that your app can properly identify the result and determine how to handle it.

                            For example, here's how to start an activity that allows the user to pick a contact:

                            static final int PICK_CONTACT_REQUEST = 1;  // The request code
                            ...
                            private void pickContact() {
                                Intent pickContactIntent = new Intent(Intent.ACTION_PICK, Uri.parse("content://contacts"));
                                pickContactIntent.setType(Phone.CONTENT_TYPE); // Show user only contacts w/ phone numbers
                                startActivityForResult(pickContactIntent, PICK_CONTACT_REQUEST);
                            }

                            Receive the Result

                            When the user is done with the subsequent activity and returns, the system calls your activity's onActivityResult() method. This method includes three arguments:

                                The request code you passed to startActivityForResult().
                                A result code specified by the second activity. This is either RESULT_OK if the operation was successful or RESULT_CANCELED if the user backed out or the operation failed for some reason.
                                An Intent that carries the result data.

                            For example, here's how you can handle the result for the "pick a contact" intent:

                            @Override
                            protected void onActivityResult(int requestCode, int resultCode, Intent data) {
                                // Check which request we're responding to
                                if (requestCode == PICK_CONTACT_REQUEST) {
                                    // Make sure the request was successful
                                    if (resultCode == RESULT_OK) {
                                            // The user picked a contact.
                                            // The Intent's data Uri identifies which contact was selected.

                                            // Do something with the contact here (bigger example below)
                                    }
                                }
                            }

                            In this example, the result Intent returned by Android's Contacts or People app provides a content Uri that identifies the contact the user selected.

                            In order to successfully handle the result, you must understand what the format of the result Intent will be. Doing so is easy when the activity returning a result is one of your own activities. Apps included with the Android platform offer their own APIs that you can count on for specific result data. For instance, the People app always returns a result with the content URI that identifies the selected contact, and the Camera app returns a Bitmap in the "data" extra (see the class about Capturing Photos).
                            Bonus: Read the contact data

                            The code above showing how to get a result from the People app doesn't go into details about how to actually read the data from the result, because it requires more advanced discussion about content providers. However, if you're curious, here's some more code that shows how to query the result data to get the phone number from the selected contact:

                            @Override
                            protected void onActivityResult(int requestCode, int resultCode, Intent data) {
                                // Check which request it is that we're responding to
                                if (requestCode == PICK_CONTACT_REQUEST) {
                                    // Make sure the request was successful
                                    if (resultCode == RESULT_OK) {
                                            // Get the URI that points to the selected contact
                                            Uri contactUri = data.getData();
                                            // We only need the NUMBER column, because there will be only one row in the result
                                            String[] projection = {Phone.NUMBER};

                                            // Perform the query on the contact to get the NUMBER column
                                            // We don't need a selection or sort order (there's only one result for the given URI)
                                            // CAUTION: The query() method should be called from a separate thread to avoid blocking
                                            // your app's UI thread. (For simplicity of the sample, this code doesn't do that.)
                                            // Consider using CursorLoader to perform the query.
                                            Cursor cursor = getContentResolver()
                                                    .query(contactUri, projection, null, null, null);
                                            cursor.moveToFirst();

                                            // Retrieve the phone number from the NUMBER column
                                            int column = cursor.getColumnIndex(Phone.NUMBER);
                                            String number = cursor.getString(column);

                                            // Do something with the phone number...
                                    }
                                }
                            }

                            Note: Before Android 2.3 (API level 9), performing a query on the Contacts Provider (like the one shown above) requires that your app declare the READ_CONTACTS permission (see Security and Permissions). However, beginning with Android 2.3, the Contacts/People app grants your app a temporary permission to read from the Contacts Provider when it returns you a result. The temporary permission applies only to the specific contact requested, so you cannot query a contact other than the one specified by the intent's Uri, unless you do declare the READ_CONTACTS permission.
                            Previous
                :res: http://www.vogella.com/tutorials/Android/article.html
```                
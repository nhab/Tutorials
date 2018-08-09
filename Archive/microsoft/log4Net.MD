```
Log4net is an open source library that allows .NET applications to log output to a variety of sources (e.g., The console, SMTP or files). 
Log4net is a port of the popular log4J library used in Java.
:termoprocs{
    1.configuration
        -The configuration is typically done in the app.config or web.config file
            Root
                You need this section.
                These are the loggers that inherit information from your base logger (root). 
                The only other thing that the root section houses is the minimum level to log. 
                Since everything inherits from the root, no appenders will log information below that specified here. 
                This is an easy way to quickly control the logging level in your application.
                Here is an example with a default level of INFO (which means DEBUG messages will be ignored) 
                and a reference to two appenders that should be enabled under root:

                <root>
                <level value="INFO"/>
                <appender-ref ref="FileAppender"/>
                <appender-ref ref="ConsoleAppender" />
                </root>

            Additional Loggers

                Sometimes you will want to know more about a particular part of your application. 
                log4net anticipated this by allowing you to specify additional logger references beyond just the root logger. 
                For example, here is an additional logger that I have placed in our config file to log to the console messages that occur inside the OtherClass class object:
        
                <logger name="Log4NetTest.OtherClass">
                <level value="DEBUG"/>
                <appender-ref ref="ConsoleAppender"/>
                </logger>

                Note that the logger name is the full name of the class including the namespace. If you wanted to monitor an entire namespace, it would be as simple as listing just the namespace you wanted to monitor. I would recommend against trying to re-use appenders in multiple loggers. It can be done, but you can get some unpredictable results.
            ConfigSections

                In a config file where there will (potentially) be more information stored beyond just the log4net configuration information, 
                you will need to specify a section to identify where the log4net configuration is housed. 
                Here is a sample section that specifies that the configuration information will be stored under the XML tag "log4net":
            

                <configSections>
                <section name="log4net" 
                type="log4net.Config.Log4NetConfigurationSectionHandler, log4net"/>
                </configSections>

            Appender (General)
                An appender is the name for what logs the information. 
                It specifies where the information will be logged, how it will be logged, and under what circumstances the information will be logged. 
                While each appender has different parameters based upon where the data will be going, there are some common elements.
                The first is the name and type of the appender. 
                Each appender must be named (anything you want) and have a type assigned to it (specific to the type of appender desired). 
                Here is an example of an appender entry:

                <appender name="ConsoleAppender" type="log4net.Appender.ConsoleAppender">

            Layout
                Inside of each appender must be a layout section. This may be a bit different depending on the type of appender being used, but the basics are the same. You need a type that specifies how the data will be written. There are multiple options, but the one that I suggest you use is the pattern layout type. This will allow you to specify how you want your data written to the data repository. If you specify the pattern layout type, you will need a sub-tag that specifies a conversion pattern. This is the pattern by which your data should be written to the data repository. I will give a more detailed description of your options for the conversion patterns, but for now, here is an example of the layout tag with the pattern layout specified:
                Hide   Copy Code

                <layout type="log4net.Layout.PatternLayout">
                    <conversionPattern value="%date [%thread] %-5level %logger [%ndc] 
                - %message%newline"/>
                </layout>

            Conversion Patterns

                As I mentioned above, the conversion pattern entry is used for the pattern layout to tell the appender how to store the information. There are many different keywords that can be used in these patterns, as well as string literals. Here I will specify what I think are the most useful and important ones. The full list can be found in the log4net documentation.

                %date - Outputs the date using the local time zone information. This date can be formatted using the curly braces and a layout pattern such as %date{MMMM dd, yyyy HH:mm:ss, fff} to output the value of "January 01, 2011 14:15:43, 767". However, it is suggested that you use one of the log4net date formatters (ABSOLUTE, DATE, or ISO8601) since they offer better performance.
                %utcdate - This is the same as the %date modifier, but it outputs in universal time. The modifiers for date/time all work the same way.
                %exception - If an exception is passed in, it will be entered and a new line will be placed after the exception. If no exception is passed in, this entry will be ignored and no new line will be put in. This is usually placed at the end of a log entry, and usually a new line is placed before the exception as well.
                %level - This is the level you specified for the event (DEBUG, INFO, WARN, etc.).
                %message - This is the message you passed into the log event.
                %newline - This is a new line entry. Based upon the platform you are using the application on, this will be translated into the appropriate new line character(s). This is the preferred method to enter a new line and it has no performance problems compared to the platform-specific operators.
                %timestamp - This is the number of milliseconds since the start of the application.
                %thread - This will give you the name of the thread that the entry was made on (or the number if the thread is not named).

                Beyond these are a few more that can be very useful but should be used with caution. They have negative performance implications and should be used with caution. The list includes:

                %identity - This is the user name of the current user using the Principal.Identity.Name method.
                %location - Especially useful if you are running in Debug mode, this tells you where the log method was called (line number, method, etc.). However, the amount of information will decrease as you operate in Release mode depending on what the system can access from the compiled code.
                %line - This is the line number of the code entry (see the note above on the location issues).
                %method - This is the method that calls the log entry (see the note above on the location issues).
                %username - This outputs the value of the WindowsIdentity property.

                You may notice that some config files have letters instead of names. These have been depreciated in favor of whole word entries like I have specified above. Also, while I won't cover it in depth here, note that each of these entries can be formatted to fit a certain width. Spaces can be added (to either side) and values can be truncated in order to fit inside of fixed-width columns. The basic syntax is to place a numeric value or values between the % sign and the name. Here are the modifiers:

                X - Specifies the minimum number of characters. Anything that has fewer characters will have spaces placed on the left of the value to equal 20 characters including the message. For example, %10message will give you " hi".
                -X - Same as above, only the spaces will be placed on the right. For example, %-10message will give you "hi ".
                .X - Specifies the maximum number of characters. The important thing to note is that this will truncate the beginning of the string, not the end. For example, %.10message will give me "rror entry" if the string passed in was "Error entry".

                You can put all of this together with something like this: "%10.20message", which would specify that if the message isn't ten characters long, put spaces on the left to fill it out to ten characters, but if the message is more than 20 characters long, cut off the beginning to make it only 20 characters.
            Filters

                Filters are another big part of any appender. With a filter, you can specify which level(s) to log and you can even look for keywords in the message. Filters can be mixed and matched, but you need to be careful when doing so. When a message fits inside the criteria for a filter, it is logged and the processing of the filter is finished. This is the biggest gotcha of a filter. Therefore, ordering of the filters becomes very important if you are doing a complex filter.
                StringMatchFilter

                The string match filter looks to find a specific string inside of the information being logged. You can have multiple string match filters specified. They work like OR statements in a query. The filter will look for the first string, then the second, etc., until a match is found. However, the important thing to note here is that not finding a match to a specified string does not exclude an entry (since it may proceed to the next string match filter). This means, however, that you may encounter a time where there are no matches found. In that case, the default action is to log the entry. So, at the end of a string match filter set, it is necessary to include a deny all filter (see below) to deny the entry from being logged if a match has not been made. Here is an example of how to filter for entries that have test in their message:
            

                <filter type="log4net.Filter.StringMatchFilter">
                <stringToMatch value="test" />
                </filter>

            LevelRangeFilter

                A level range filter tells the system to only log entries that are inside of the range specified. This range is inclusive, so in the below example, events with a level of INFO, WARN, ERROR, or FATAL will be logged, but DEBUG events will be ignored. You do not need the deny all filter after this entry since the deny is implied.
            
                <filter type="log4net.Filter.LevelRangeFilter">
                <levelMin value="INFO" />
                <levelMax value="FATAL" />
                </filter>

            LevelMatchFilter

                The level match filter works like the level range filter, only it specifies one and only one level to capture. However, it does not have the deny built into it so you will need to specify the deny all filter after listing this filter.
                
                <filter type="log4net.Filter.LevelMatchFilter">
                <levelToMatch value="ERROR"/>
                </filter>

            DenyAllFilter

                Here is the entry that, if forgotten, will probably ensure that your appender does not work as intended. The only purpose of this entry is to specify that no log entry should be made. If this were the only filter entry, then nothing would be logged. However, its true purpose is to specify that nothing more should be logged (remember, anything that has already been matched has been logged).
                

                <filter type="log4net.Filter.DenyAllFilter" />

            Appenders

                Each type of appender has its own set of syntax based upon where the data is going. The most unusual ones are the ones that log to databases. I will list a few of the ones that I think are most common. However, given the above information, you should be able to use the examples given online without any problems. The log4net site has some great examples of the different appenders. As I have said before, I used the log4net documentation extensively and this area was no exception. I usually copy their example and then modify it for my own purposes.
                Console Appender

                I use this appender for testing usually, but it can be useful in production as well. It writes to the output window, or the command window if you are using a console application. This particular filter outputs a value like "2010-12-26 15:41:03,581 [10] WARN Log4NetTest.frmMain - This is a WARN test." It will include a new line at the end.
            

                <appender name="ConsoleAppender" type="log4net.Appender.ConsoleAppender">
                <layout type="log4net.Layout.PatternLayout">
                <conversionPattern value="%date{ABSOLUTE} 
                [%thread] %level %logger - %message%newline"/>
                </layout>
                <filter type="log4net.Filter.StringMatchFilter">
                <stringToMatch value="test" />
                </filter>
                <filter type="log4net.Filter.DenyAllFilter" />
                </appender>

            File Appender

                This appender will write to a text file. The big differences to note here are that we have to specify the name of the text file (in this case, it is a file named mylogfile.txt that will be stored in the same location as the executable), we have specified that we should append to the file (instead of overwriting it), and we have specified that the FileAppender should use the Minimal Lock which will make the file usable by multiple appenders.
                

                <appender name="FileAppender" type="log4net.Appender.FileAppender">
                <file value="mylogfile.txt" />
                <appendToFile value="true" />
                <lockingModel type="log4net.Appender.FileAppender+MinimalLock" />
                <layout type="log4net.Layout.PatternLayout">
                <conversionPattern value="%date [%thread] %level %logger - %message%newline" />
                </layout>
                <filter type="log4net.Filter.LevelRangeFilter">
                <levelMin value="INFO" />
                <levelMax value="FATAL" />
                </filter>
                </appender>

            Rolling File Appender

                This is an appender that should be used in place of the file appender whenever possible. The purpose of the rolling file appender is to perform the same functions as the file appender but with the additional option to only store a certain amount of data before starting a new log file. This way, you won't need to worry about the logs on a system filling up over time. Even a small application could overwhelm a file system given enough time writing to a text file if the rolling option were not used. In this example, I am logging in a similar fashion to the file appender above, but I am specifying that the log file should be capped at 10MB and that I should keep up to 5 archive files before I start deleting them (oldest gets deleted first). The archives will be named with the same name as the file, only with a dot and the number after it (example: mylogfile.txt.2 would be the second log file archive). The staticLogFileName entry ensures that the current log file will always be named what I specified in the file tag (in my case, mylogfile.txt).
                Hide   Copy Code

                <appender name="RollingFileAppender" type="log4net.Appender.RollingFileAppender">
                <file value="mylogfile.txt" />
                <appendToFile value="true" />
                <rollingStyle value="Size" />
                <maxSizeRollBackups value="5" />
                <maximumFileSize value="10MB" />
                <staticLogFileName value="true" />
                <layout type="log4net.Layout.PatternLayout">
                <conversionPattern value="%date [%thread] %level %logger - %message%newline" />
                </layout>
                </appender>

            ADO.NET Appender

                Here is the tricky one. This specific example writes to SQL, but you can write to just about any database you want using this pattern. Note that the connectionType is basically a connection string, so modifying it is simple. The commandText specified is a simple query. You can modify it to any type of INSERT query that you want (or Stored Procedure). Notice that each parameter is specified below and mapped to a log4net variable. The size can be specified to limit the information placed into the parameter. This appender is a direct copy from the log4net example. I take no credit for it. I simply use it as an example of what can be done.

                Quick note: If you find that your ADO.NET appender is not working, check the bufferSize value. This value contains the number of log statements that log4net will cache before writing them all to SQL. The example on the log4net website has a bufferSize of 100, which means you will probably freak out in testing when nothing is working. Change the bufferSize value to 1 to make the logger write every statement when it comes in.

                For this example and more, go to the following URL: http://logging.apache.org/log4net/release/config-examples.html.
                Hide   Shrink   Copy Code

                <appender name="AdoNetAppender" type="log4net.Appender.AdoNetAppender">
                <bufferSize value="100" />
                <connectionType value="System.Data.SqlClient.SqlConnection, 
                System.Data, Version=1.0.3300.0, Culture=neutral, PublicKeyToken=b77a5c561934e089" />
                <connectionString value="data source=[database server];
                initial catalog=[database name];integrated security=false;
                persist security info=True;User ID=[user];Password=[password]" />
                <commandText value="INSERT INTO Log ([Date],[Thread],[Level],[Logger],
                [Message],[Exception]) VALUES (@log_date, @thread, @log_level, 
                @logger, @message, @exception)" />
                <parameter>
                <parameterName value="@log_date" />
                <dbType value="DateTime" />
                <layout type="log4net.Layout.RawTimeStampLayout" />
                </parameter>
                <parameter>
                <parameterName value="@thread" />
                <dbType value="String" />
                <size value="255" />
                <layout type="log4net.Layout.PatternLayout">
                    <conversionPattern value="%thread" />
                </layout>
                </parameter>
                <parameter>
                <parameterName value="@log_level" />
                <dbType value="String" />
                <size value="50" />
                <layout type="log4net.Layout.PatternLayout">
                    <conversionPattern value="%level" />
                </layout>
                </parameter>
                <parameter>
                <parameterName value="@logger" />
                <dbType value="String" />
                <size value="255" />
                <layout type="log4net.Layout.PatternLayout">
                    <conversionPattern value="%logger" />
                </layout>
                </parameter>
                <parameter>
                <parameterName value="@message" />
                <dbType value="String" />
                <size value="4000" />
                <layout type="log4net.Layout.PatternLayout">
                    <conversionPattern value="%message" />
                </layout>
                </parameter>
                <parameter>
                <parameterName value="@exception" />
                <dbType value="String" />
                <size value="2000" />
                <layout type="log4net.Layout.ExceptionLayout" />
                </parameter>
                </appender>
    2.the setup
        Once you have a reference to the log4net DLL in your application, there are three lines of code that you need to know about. The first is a one-time entry that needs to be placed outside of your class. I usually put it right below my using statements in the Program.cs file. You can copy and paste this code since it will probably never need to change (unless you do something unusual with your config file). Here is the code:
        

        [assembly: log4net.Config.XmlConfigurator(Watch = true)]

        The next entry is done once per class. It creates a variable (in this case called "log") that will be used to call the log4net methods. This code is also code that you can copy and paste (unless you are using the Compact Framework). It does a System.Reflection call to get the current class information. This is useful because it allows us to use this code all over but have the specific information passed into it in each class. Here is the code:
        
        private static readonly log4net.ILog log = log4net.LogManager.GetLogger
        (System.Reflection.MethodBase.GetCurrentMethod().DeclaringType);

        The final code piece is the actual call to log some piece of information. This can be done using the following code:
        
        log.Info("Info logging");

        Notice that you can add an optional parameter at the end to include the exception that should be logged. Include the entire exception object if you want to use this option. The call is very similar, and it looks like this:
        
        log.Error("This is my error", ex);

        ex is the exception object. Remember that you need to use the %exception pattern variable in your appender to actually capture this exception information.
    3.the call
    -Getting Away from app.config/web.config
        You may come across a time when you want to use a separate file to store the log4net configuration information. In fact, you might find this to be the optimal way to store the configuration information, since you could keep copies of your different standard configurations on hand to drop into your projects. This could cut down on development time and allow you to standardize your logging information. To set this up, you need to change only two parts of your app. The first thing you need to do is save the configuration in a different file. The format will be the same, as will how it is laid out. The only thing that will really change in the layout is that it isn't in the middle of your app.config or web.config file. The second change you need to make is in that one setup call in your application. You need to add information on where the file is, like so:
        Hide   Copy Code

        [assembly: log4net.Config.XmlConfigurator(ConfigFile = 
                    "MyStandardLog4Net.config", Watch = true)]

        There is also the possibility of simply choosing a different extension for this file by using "ConfigFileExtension" instead of "ConfigFile" in the line above. If you do that, you need to name your config file to be your assembly name (including extension), and it needs to have the extension you specify. Here is an example with a more visual explanation:
        Hide   Copy Code

        [assembly: log4net.Config.XmlConfigurator(ConfigFileExtension = "mylogger", Watch = true)]

        In the above example, if our application was test.exe, then the configuration file for log4net should be named text.exe.mylogger.
```
```
:a collection of application blocks deals with common  cross-cutting  enterprise development challenges.						
:Termoprocs{(application blocks)
    -logging
        :  writing to the Windows Event Log, an e-mail message, a database, Windows Message Queuing, a text file.
        :{
            Logger 
                    :is a static class which provides typical APIs for writing logs.
                    There are many overloaded APIs according to which logs can be routed to the respective logging target. 
            Log Entry
                :Represents a log message.
                    Contains the common properties that are required for all log messages
                    like Priority, Severity, and Category etc… 
                :Procs: 
                    -Creating the Log Entry
                    :{
                        -The user creates a LogWriter instance, 
                            and invokes one of the Write method overloads.
                        -Alternatively, the user can create a new LogEntry explicitly,
                            populate it with the required information,
                            and use a LogWriter to pass it to the Logging block for processing.

                    -Filtering the Log Entry
                        The Logging block filters the LogEntry ( based on your configuration settings ) 
                        for message priority, or categories you added to the LogEntry when you created it. 
                        It also checks to see if logging is enabled. 
                        These filters can prevent any further processing of the log entries.
                        This is useful, for example, when you want to allow administrators to enable and disable additional debug information logging
                        without requiring them to restart the application.

                    -Formatting the Log Entry
                        Each trace listener can use a log formatter to format the information contained in the log entry. 
                        The block contains log message formatters, and you can create your own formatter if required. 
                        The text formatter uses a template containing placeholders that makes it easy to generate the required format for log entries.

            -Log Writer:
                    The log writer is the main entry point for creating log entries 
                    and writing them to our chosen logging targets. 
                    It creates an instance of a log entry containing the information to be logged, 
                    and interacts with the other objects that filter the log entry,
                    assign it to one or more categories, format it, and dispatch it to the appropriate targets. 

            -Log Filters:
                    Log filters can block or allow a log entry based on a number of features. 
                    Each log entry is assigned to one or more categories (the default is the General category), 
                    and the category log filter can use these categories to pass or block a log entry. 
                    In addition, two special log filters can block all logging, or block log entries with a priority lower than a specified value. 
                    We define the categories, priorities, and the settings for the log filters in the configuration for the block.
                    
            -Trace Sources:
                    Trace sources are effectively a set of buckets into which the block places all log entries that have not been blocked by a log filter.
                    We use these buckets to define where log entries will be dispatched to—
                    we can think of them as being the source of 		the log entries that will actually be dispatched to the target destinations.
                :{	There are two basic types of trace sources:
                    -Category Sources: 
                        There is a trace source for each category we define in the configuration of the block.
                    Special Sources:
                            :{There are three built-in trace sources:
                                -one that receives all log entries, 
                                -one that receives log entries when an error occurs during processing or dispatching of the log entry, 
                                -and one that receives all log entries that do not match any configured category.
                :procs:
                    Selecting Trace Sources
                        Trace sources act as the link between the log entries and the log targets.
                        There is a trace source for each category you define in the logging block configuration; 
                        
                        plus, there are three built-in trace sources that capture all log entries,
                        unprocessed entries that do not match any category, 
                        and entries that cannot be processed due to an error while logging (such as an error while writing to the target log).
            Trace Listeners
                    :
                    Trace listeners represent the targets for our log entries,
                    and we configure one for each type of target (such as the Windows® Event Log, a disk file, and an e-mail message)
                    to which we want to send the log entries.
                        Trace listeners listen for log entries arriving in the trace source buckets,
                        format each log entry as required, and dispatch it to the target configured for that trace source. 
                        Our configuration maps each trace source (each category source we define plus the three special sources) to one or more trace listeners.
                        this allows us to dispatch each log entry to zero, one, or more targets (such as sending it as e-mail as well as writing it to the Windows Event Log). 
                :procs
                    Selecting Trace Listeners
                        Each trace source has one or more trace listeners defined. 
                        These listeners are responsible for taking the log entry,
                        passing it through a separate log formatter 
                        that translates the content into a suitable format, 
                        and passing it to the target log. 
                        
                        Several trace listeners are provided with the block, and you can create your own if required.

            Logging Categories
                Categories allow you to specify the target(s) for log entries processed by the block.
                You can define categories that relate to one or more targets. 
                
                For example, you might create a category named General containing trace listeners
                that write to text files and XML files, 
                and a category named Auditing for administrative information 
                that is configured to use trace listeners that write to one or more databases.
                Then you can assign a log entry to one or more categories, effectively mapping it to multiple targets.
                    The three log sources (all events log source, not processed log source, and errors log source) are themselves categories for which you can define trace listeners.

            Log Formatters:
                : Each trace listener we add to our configuration can use a log formatter 
                to convert the data in the log entry from a series of properties into format suitable for sending to the log target. 
                The block contains a text formatter that we can configure with trace listeners that dispatch log entries to targets 
                such as disk files, e-mail, or Windows Event Log; 
                and a binary formatter that serializes the log entry data into a format suitable for transmission to targets such as Windows Message Queuing (MSMQ).
                The text formatter is configurable so that we can modify the format and content of the text message,
                including using placeholders for the values of the properties of the log entry.

    -segment logging
        The Semantic Logging Application Block enables you to use the EventSouce class to write strongly typed log messages from your application.
        This enables you to write log messages with a consistent structure and format and to collect and process log messages out-of-process.

    -data access
        It includes support for both stored procedures and in-line SQL, 
        can expose the data as a sequence of objects for client-side querying, 
        and provides access to the most frequently used features of ADO.NET in simple-to-use classes.
    -validation
    -Exception handling
    -transient fault handling
            
            When cloud-based applications use other cloud-based services,
            errors can occur because of temporary conditions
            such as intermittent service, infrastructure-level faults, or network issues. 
            Very often, if you retry the operation a short time later 					 (maybe only a few milliseconds later) 
            the operation may succeed.
            These types of error conditions are referred to as transient faults.
            Transient faults typically occur very infrequently, and in most cases, only a few retries are necessary for the operation to succeed.
    
    -dependency
    -Dependency Injection in Enterprise Library
        :{
            -Loading configuration information into a Unity container
            -Viewing the registrations in the container
            -Populating entire object graphs at application startup
            -Maintaining a reference to the container in request-based applications
            -Using an alternative service locator or dependency injection container


        Loading Configuration Information into a Unity Container

            Unity does not automatically load configuration information when it starts.
            This is intentional; it means that you can load configuration information into one or more new or existing containers, 
            including containers that you create as a hierarchy of parent and child containers.

            This also means that you can exert considerable control over how requests for types are handled. 
            For example, you can use multiple containers to specify dependencies for different parts of your application,
            while allowing requests that cannot be satisfied in a child container to pass up through the hierarchy of parent containers until a suitable registration is found.

            It also means that you can load configuration information from different sources. A typical example is loading configuration from a file other than App.config or Web.config, or by adding registrations programmatically by—for example—reading them from a database and applying them to the container.

            The Unity container class exposes the LoadConfiguration method that you can use to populate a container. You can call this method with no parameters to read a <unity> section from the current application configuration file (App.config or Web.config), as demonstrated in Chapter 1 of this guide. Alternatively, you can provide the method with a UnityConfigurationSection instance that contains the configuration information. The following code opens a configuration file using the methods of the Microsoft® .NET Framework configuration system, casts it to a UnityConfigurationSection type, and loads the registrations in the <container> section that has the name MyContainerName into a new Unity container.

            // Read a specified config file using the .NET configuration system.
            ExeConfigurationFileMap map = new ExeConfigurationFileMap();
            map.ExeConfigFilename = @"c:\configfiles\myunityconfig.config";
            System.Configuration.Configuration config 
                            = ConfigurationManager.OpenMappedExeConfiguration(map,
                                            ConfigurationUserLevel.None);
            // Get the unity configuration section.
            UnityConfigurationSection section
            = (UnityConfigurationSection)config.GetSection("unity");

            // Create and populate a new UnityContainer with the configuration information.
            IUnityContainer theContainer = new UnityContainer();
            theContainer.LoadConfiguration(section, "MyContainerName");

            You can define multiple containers within the <unity> section of a configuration file providing each has a unique name, and load each one into a separate container at run time. If you do not assign a name to a container in the configuration file, it becomes the default container, and you can load it by omitting the name parameter in the LoadConfiguration method.

            To load a container programmatically in this way, you must add the System.Configuration.dll assembly and the Microsoft.Practices.Unity.Configuration.dll assembly to your project. You should also import the following namespaces:

            Microsoft.Practices.EnterpriseLibrary.Common.Configuration.Unity
            Microsoft.Practices.Unity

        Viewing Registrations in the Container

            Sometimes you may find that your application throws an error indicating that it cannot resolve a specific type. The error messages that Unity returns are detailed, and should help you to find the problem quickly. However, you may find it useful to be able to browse the contents of the container to see the registrations and mappings it contains.

            The Unity container exposes the Registrations property, which returns a collection of ContainerRegistration instances; one for each registration or type mapping in the container. The following example code shows how you can extract details for each registration: the registered type, the type it maps to (if any), the name of the registration (if it is not a default registration), and the lifetime manager type.

            foreach (ContainerRegistration item in theContainer.Registrations)
            {
            regType = item.RegisteredType.Name;
            mapTo = item.MappedToType.Name;
            regName = item.Name ?? "[default]";
            lifetime = item.LifetimeManagerType.Name;
            if (mapTo != regType)
            {
            mapTo = " -> " + mapTo;
            }
            else
            {
            mapTo = string.Empty;
            }
            lifetime = lifetime.Substring(0, lifetime.Length - "LifetimeManager".Length);
            // Display details of the registration as appropriate.
            }

        Populating Entire Object Graphs at Application Startup

            After you populate the container with your configuration information, both the Enterprise Library information and the registrations and mappings for your own custom types, you can resolve these custom types with all of their dependencies populated through dependency injection. You can define dependencies in three ways:

            As one or more parameters of a constructor in the target class. Unity will create instances of the appropriate types and populate the constructor parameters when the target object is instantiated. This is the approach you will typically use. For example, you can have Unity automatically create and pass into your constructor an instance of a LogWriter or an ExceptionManager, store the reference in a class variable or field, and use it within that class.
            As one or more properties of the target class. Unity will create an instance of the type defined by the property or in configuration and set that instance as the value of the property when the class is resolved through the container.
            As one or more parameters of a method in the target class. Unity will create instances of the appropriate types and populate the method parameters when the target object is instantiated, and then call that method. You can store the references passed in the parameters in a class variable or field for use within that class. This approach is typically used when you have an Initialize or similar method that should execute when the class is instantiated. 

            By taking advantage of this capability to populate an entire object graph, you may decide to have the container create and inject instances of the appropriate types for all of the dependencies defined in your entire application when it starts up (or, at least, a significant proportion of it).

            While this may seem to be a strange concept, it means that you do not need to hold onto a reference to the container after you perform this initial population of dependencies. That doesn’t mean you cannot hold onto the container reference as well, but resolving all of the required types at startup can improve run-time performance at the cost of slightly increased startup time. Of course, this also requires additional memory and resources to hold all of the resolved instances, and you must balance this against the expected improvement in run-time performance.

            You can populate all of your dependencies by resolving the main form or startup class through the container. The container will automatically create the appropriate instances of the objects required by each class and inject them into the parameters and properties. However, it does rely on the container being able to create and return instances of types that are not registered in the container. The Unity container can do this. If you use an alternative container, you may need to preregister all of the types in your application, including the main form or startup class.

            Typically, this approach to populating an entire application object graph is best suited to applications built using form-based or window-based technologies such as Windows® Presentation Foundation (WPF), Windows Forms, console applications, and Microsoft Silverlight® (using the version of Unity specifically designed for use in Silverlight applications).

            For information about how you can resolve the main form, window, or startup class of your application, together with example code, see the documentation installed with Enterprise Library
        Maintaining a Container Reference in Request-Based Applications

            When using the default Unity DI mechanism with Enterprise Library, all you need to do is initialize the container once on your application, and then use it to resolve (or obtain) instances of Enterprise Library objects or your own classes and objects. Initializing the container requires just the following single line of code.

            // Create and populate the default container with application configuration.
            var container = new UnityContainer()
                            .AddNewExtension<EnterpriseLibraryCoreExtension>();

            However, to use the container to resolve types throughout your application, you must hold a reference to it. You can store the container in a global variable in a Windows Forms or WPF application, in the Application dictionary of an ASP.NET application, or in a custom extension to the InstanceContext of a Windows Communication Foundation (WCF) service.

        Using an Alternative Service Locator or Container

            Enterprise Library, by default, uses the Unity dependency injection mechanism to create instances of Enterprise Library objects. 
            If you are already using, or plan to use, a different dependency injection container in your application 
            you may be able to use it to create Enterprise Library objects instead of using Unity.

            For this to work, you can obtain or write your own configurator that can load the container with the Enterprise Library configuration information you specify, 
            or create a type that implements the IServiceLocator interface and can expose the configuration information.

            The default behavior of Enterprise Library is to
                    create a new Unity container,
                    create a new configurator for the container, 
                    and then read the configuration information from the application's default configuration file (App.config or Web.config). 
                    
            The following code extract shows the process that occurs.

                var container = new UnityContainer();
                var configurator = new UnityContainerConfigurator(container);

                // Read the configuration files and set up the container.
                EnterpriseLibraryContainer.ConfigureContainer(configurator, 
                                    ConfigurationSourceFactory.Create());
                // The container is now ready to resolve Enterprise Library objects

            The task of the configurator is to translate the configuration file information into a series of registrations within the container. 
            Enterprise Library contains only the UnityContainerConfigurator, though you can write your own to suit your chosen container, or obtain one from a third party.

            An alternative approach is to create a custom implementation of the IServiceLocator interface that may not use a configurator, 
            but can read the application configuration and return the appropriate fully populated Enterprise Library objects on demand.

            See http://commonservicelocator.codeplex.com for more information about the IServiceLocator interface.

            To keep up with discussions regarding alternate configuration options for Enterprise Library, see the forums on CodePlex at http://www.codeplex.com/entlib/Thread/List.aspx.
    -Unity Block
            :
            is a  dependency injection container
            that supports :
                - constructor injection
                - property injection
                - method call injection.
            
            You can use it with Enterprise Library to generate both 
                Enterprise Library objects 
                and your own custom business objects.
        :cons:
            -It provides simplified object creation, 
                especially for hierarchical object structures and dependencies, which simplifies application code.

            -It supports abstraction of requirements;
                this allows developers to specify dependencies at run time or in configuration
                and simplify management of crosscutting concerns.
                
            -It increases flexibility by deferring component configuration to the container.
            -It has a service location capability; 
                this allows clients to store or cache the container. 
                This is especially useful in ASP.NET Web applications 
                where developers can persist the container in the ASP.NET session or application.
        :Terms:
            injecting dependencies 
                means that the dependency is pushed into the class from the outside
                all that means is that you shouldn't instantiate dependencies
                using the new operator from inside of the class 
                instead take it as a constructor	parameter or via a setter
                you don`t need a container to do it
                but they make your life easier 

            dependency injection (DI) container
                    is an object that knows how to instantiate and configure objects and all their dependent objects.
            The Unity Container (Unity) 
                is a lightweight, extensible dependency injection container.
                It facilitates building loosely coupled applications 
                :cons{
                    -Simplified object creation, especially for hierarchical object structures and dependencies
                    -Abstraction of requirements; 
                        this allows developers to specify dependencies at run time or in configuration and simplify management of crosscutting concerns
                    -Increased flexibility by deferring component configuration to the container
                    -Service location capability; this allows clients to store or cache the container
                    -Instance and type interception
                    -Registration by convention
                :processes:
                    Setting Up the Unity Container
                        :OPTS{by populating it with registered mappings:
                            -Provide an XML format configuration file 
                                that adheres to the schema shown in Source Schema for the Unity Application Block.
                            -Use the methods of the container 
                                to add specific registration entries for default and named mappings.
                            -Use the container configuration API 
                                to provide a custom configuration for the container.
                        Register mappings for a Unity container:
                            :OPT{
                                RegisterType.
                                    This method registers a type with the container.
                                    At the appropriate time, the container will build an instance of the type you specify.
                                    This could be in response to dependency injection
                                    through class attributes or when you call the Resolve method. 
                                    The lifetime of the object it builds will correspond to the lifetime you specify in the parameters of the method.
                                    If you do not specify a value for the lifetime, 
                                    the type is registered for a transient lifetime,
                                    which means that a new instance will be created on each call to Resolve.
                                RegisterInstance.
                                    This method registers with the container an existing instance of a type that you specify
                                    , with the lifetime that you specify. 
                                    The container will return the existing instance during that lifetime. 
                                    If you do not specify a value for the lifetime, 
                                    the instance will have the default container-controlled lifetime. 
                                    It will return a reference to the original object on each call to Resolve.
                        To register a mapping for an interface or class to a concrete type
                            1.Create a new instance of the UnityContainer class or use a reference to an existing instance.
                                To create a new instance, you can use the "new" operator. 
                            IUnityContainer myContainer = new UnityContainer();

                            2.If you want to use a child container nested within an existing container, call the CreateChildContainer method of the parent container. 
                            For more details about using nested containers, see Using Container Hierarchies.
                            IUnityContainer childCtr = myContainer.CreateChildContainer();

                            3.Call the RegisterType method of the container in which you want to register a mapping or a type.
                                Specify the registered type as an interface or object type and the target type you want returned in response to a query for that type. 
                                The target type must implement the interface, or inherit from the class, that you specify as the registered type.
                                The following code creates a default (un-named) mapping using an interface as the dependency key. 
                            myContainer.RegisterType<IMyService, CustomerService>();

                            4.If you want to map a class or object type to a more specific class that inherits from it, 
                            use the same syntax but provide the inherited object as the registered type, as shown in this code. 
                            myContainer.RegisterType<MyServiceBase, DataService>();

                            5.If you want to create more than one registration or mapping for the same type,
                                you can create a named (non-default) mapping by specifying a name as a parameter, as shown in this code. 
                            myContainer.RegisterType<IMyService, CustomerService>("Customers");
                        :res:
                            https://msdn.microsoft.com/en-us/library/ff649564.aspx
                            https://msdn.microsoft.com/en-us/library/ff648271.aspx 
                        

        :Proccesses{
            :How to use
                -can be used as a stand-alone dependency injection mechanism 
                that
                    has no dependency on the Enterprise Library core or the Enterprise Library configuration system.
                -can use configuration information through configuration files to prepare the container
                    , but you can also use code to dynamically register dependencies at run time.
                    
                    
                It contains its own built-in mechanism for reading configuration—although,
                if appropriate, this information can come from the normal Enterprise Library configuration file.
            -Referencing 
                -Add a reference to the Unity Application Block assembly.
                    Microsoft.Practices.Unity.dll 
                -Use the same procedure to set a reference to the ObjectBuilder assembly
                    named Microsoft.Practices.ObjectBuilder2.dll.


            1-Entering Configuration Information
                The Unity Application Block can read configuration information from an XML configuration file.
                By default, this is the "App.config" or "Web.config" file .
                However, you can load configuration information from any other XML format file or from other sources.
                
                -Configuring Containers at Design Time:
                    -Format of the Unity Configuration File:
                        :syntax:
                            <configuration>
                                <configSections>
                                    <section name="unity" type="Microsoft.Practices.Unity.Configuration.UnityConfigurationSection, Microsoft.Practices.Unity.Configuration" />
                                </configSections>
                                <unity> 
                                ...
                                ...
                                </unity>
                                ...
                                ...
                            </configuration>
                        :X
                            <?xml version="1.0" encoding="utf-8" ?> 
                            <configuration>
                                <configSections>
                                    <section name="unity"
                                                    type="Microsoft.Practices.Unity.Configuration.UnityConfigurationSection,
                                                        Microsoft.Practices.Unity.Configuration, =1.2.0.0,
                                                        Culture=neutral, PublicKeyToken=31bf3856ad364e35" />
                                </configSections>

                                <unity>

                                    <typeAliases>

                                        <!-- Lifetime manager types -->
                                        <typeAlias alias="singleton"
                                                type="Microsoft.Practices.Unity.ContainerControlledLifetimeManager,
                                                        Microsoft.Practices.Unity" />
                                        <typeAlias alias="perThread"
                                                type="Microsoft.Practices.Unity.PerThreadLifetimeManager,
                                                        Microsoft.Practices.Unity" />
                                        <typeAlias alias="external"
                                                type="Microsoft.Practices.Unity.ExternallyControlledLifetimeManager,
                                                        Microsoft.Practices.Unity" />

                                        <!-- User-defined type aliases -->
                                        <typeAlias alias="IMyInterface"
                                                type="MyApplication.MyTypes.MyInterface, MyApplication.MyTypes" />
                                        <typeAlias alias="MyRealObject" 
                                                type="MyApplication.MyTypes.MyRealObject, MyApplication.MyTypes" />
                                        <typeAlias alias="IMyService"
                                                type="MyApplication.MyTypes.MyService, MyApplication.MyTypes" />
                                        <typeAlias alias="MyDataService"
                                                type="MyApplication.MyTypes.MyDataService, MyApplication.MyTypes" />
                                        <typeAlias alias="MyCustomLifetime" 
                                                type="MyApplication.MyLifetimeManager, MyApplication.MyTypes" />

                                    </typeAliases>

                                    <containers>

                                        <container name="containerOne">

                                            <types>

                                            <!-- Type mapping with no lifetime — defaults to "transient" -->  
                                            <type type="Custom.MyBaseClass" mapTo="Custom.MyConcreteClass" />

                                            <!-- Type mapping using aliases defined above -->  
                                            <type type="IMyInterface" mapTo="MyRealObject" name="MyMapping" />

                                            <!-- Lifetime managers specified using the type aliases -->
                                            <type type="Custom.MyBaseClass" mapTo="Custom.MyConcreteClass">
                                                <lifetime type="singleton" /> 
                                            </type>
                                            <type type="IMyInterface" mapTo="MyRealObject" name="RealObject">
                                                <lifetime type="perThread" />
                                            </type>
                                            <type type="IMyInterface" mapTo="MyRealObject" name="RealObject">
                                                <lifetime type="external" />
                                            </type>

                                            <!-- Lifetime manager specified using the full type name -->
                                            <!-- Any initialization data specified for the lifetime manager -->
                                            <!-- will be converted using the default type converter -->
                                            <type type="Custom.MyBaseClass" mapTo="Custom.MyConcreteClass">
                                                <lifetime value="sessionKey"
                                                            type="MyApplication.MyTypes.MyLifetimeManager,
                                                                    MyApplication.MyTypes" />
                                            </type>

                                            <!-- Lifetime manager initialization using a custom TypeConverter -->
                                            <type type="IMyInterface" mapTo="MyRealObject" name="CustomSession">
                                                <lifetime type="MyCustomLifetime" value="ReverseKey"
                                                            typeConverter="MyApplication.MyTypes.MyTypeConverter,
                                                                                MyApplication.MyTypes" />
                                            </type>

                                            <!-- Object with injection parameters defined in configuration -->
                                            <!-- Type mapping using aliases defined above -->  
                                            <type type="IMyService" mapTo="MyDataService" name="DataService">
                                                <typeConfig extensionType="Microsoft.Practices.Unity.Configuration.TypeInjectionElement,
                                                                                    Microsoft.Practices.Unity.Configuration">
                                                    <constructor>
                                                    <param name="connectionString" parameterType="string">
                                                        <value value="AdventureWorks"/>
                                                    </param>
                                                    <param name="logger" parameterType="ILogger">
                                                        <dependency />
                                                    </param>
                                                    </constructor> 
                                                    <property name="Logger" propertyType="ILogger" />
                                                    <method name="Initialize">
                                                    <param name="connectionString" parameterType="string">
                                                        <value value="contoso"/>
                                                    </param>
                                                    <param name="dataService" parameterType="IMyService">
                                                        <dependency />
                                                    </param>
                                                    </method>
                                                </typeConfig>
                                            </type>

                                            </types>

                                            <instances>
                                            <add name="MyInstance1" type="System.String" value="Some value" />
                                            <add name="MyInstance2" type="System.DateTime" value="2008-02-05T17:50:00"  />
                                            </instances>

                                            <extensions>
                                            <add type="MyApp.MyExtensions.SpecialOne" />
                                            </extensions>

                                            <extensionConfig>
                                            <add name="MyExtensionConfigHandler"
                                                    type="MyApp.MyExtensions.SpecialOne.ConfigHandler" />
                                            </extensionConfig>

                                        </container>

                                        <!-- ... more containers here ... -->

                                    </containers>

                                </unity>

                                </configuration>
            2-Loading Configuration Information into a Container
                The Unity Application Block does not automatically read the configuration information or create and prepare containers.
                You must programmatically instantiate a Unity container in your application. 
                You can programmatically configure it with 
                    registrations, type mappings, and any extensions 
                or you can configure it by reading configuration information from a file.

                If the configuration defines an unnamed container, that unnamed container is the default container.
                You can also declare named containers in addition to the default, unnamed container.
                By using Unity, you can load the information from each container configuration section into containers
                    that you have already created as part of a container hierarchy.
                
                -Configuring Containers at Design time examples
                    :X 
                        //Instantiate a new Unity container
                        // and then load it with the registrations, type mappings, and extensions
                        // defined in the configuration file for that container.
                        IUnityContainer container = new UnityContainer();
                        UnityConfigurationSection section
                        = (UnityConfigurationSection)ConfigurationManager.GetSection("unity");
                        section.Containers.Default.Configure(container);
                    :x2
                        //instantiate and load 'containerOne' container
                        IUnityContainer container = new UnityContainer();
                        UnityConfigurationSection section 
                        = (UnityConfigurationSection)ConfigurationManager.GetSection("unity");
                        section.Containers["containerOne"].Configure(container);
                    :x3
                        // Alternative way to load configuration information into containers
                        //(from a specific named configuration file)
                        ExeConfigurationFileMap map = new ExeConfigurationFileMap();
                        map.ExeConfigFilename = "MyConfig.config";
                        System.Configuration.Configuration config 
                        = ConfigurationManager.OpenMappedExeConfiguration(map, ConfigurationUserLevel.None); 
                        UnityConfigurationSection section
                        = (UnityConfigurationSection)config.GetSection("unity");
                        IUnityContainer container = new UnityContainer();
                        section.Containers["myContainer"].Configure(container);
            3-Configuring Containers at Run Time and Configuring Constructor, Property, and Method Injection

                :You can configure the Unity container to perform injection at run time 
                by directly creating and populating instances of the configuration classes.
                
                This provides an alternative approach to using attributes within the target classes
                    or configuring injection requirements using the Unity configuration file.

                Use the InjectionConstructor, InjectionProperty, and InjectionMethod classes
                    in conjunction with the Configure and ConfigureInjectionFor methods
                    to specify dependency injection parameters for the container.

                Some RegisterType overloads allow for configuring injection by accepting InjectionMembers
                , thus enabling you to avoid having to make a seperate call to ConfigureInjectionFor on the InjectedMembers extension.
                    :X
                                IUnityContainer container = new UnityContainer()
                                .RegisterType<AType>(new InjectionConstructor());

                                AType aType = container.Resolve<AType>();
                                Assert.IsTrue(aType.DefaultConstructorCalled);
                    :x2
                        The following example shows how you can configure constructor injection, property injection, and method injection
                        using the configuration classes through the fluent interface of the container.
                        

                        IUnityContainer myContainer = new UnityContainer();
                        myContainer.Configure<InjectedMembers>()
                        .ConfigureInjectionFor<MyObject>(
                            new InjectionConstructor(12, "Hello Unity!"),
                            new InjectionProperty("MyProperty"),
                            new InjectionProperty("MyStringProperty", "SomeText"),
                            new InjectionMethod("InitializeMe", 42.0, 
                                        new ResolvedParameter(typeof(ILogger), "SpecialLogger"))
                        );

                        The preceding code creates a container and then performs the following configuration for injection 

                            -It configures constructor injection for the constructor that accepts as parameters an Integer value and a String value
                                , and it passes the values 12 and "Hello Unity!" to these parameters.
                            -It configures property injection for the property named MyProperty to use the default configuration of the container. 
                            The container resolves the value for this property using registrations and mappings within the container.
                            -It configures property injection for the property named MyStringProperty to use the specified value. 
                            The container sets the property to the value "SomeText".
                            -It configures method injection for the method named InitializeMe that accepts as parameters a Double value and an instance of
                                a class that implements the ILogger interface. 
                                It passes to the first parameter the value 42.0. 
                                It also resolves the ILogger type through the container by looking for a mapping for that type with the name SpecialLogger
                                and passes the result to the second parameter of the method.

                        The style of the API for dynamic injection configuration is intended to provide sufficient flexibility 
                        and still remain easy and intuitive to use.

                        The injection configuration APIs are based on the subclasses of InjectionParameterValue. 
                        You can also provide other types of objects when setting up injection. 
                        The objects are translated to a InjectionParameterValue according to the following rules:

                            -If the object is an instance of a subclass of the InjectionParameterValue class, the injection system uses the object.
                            -If the object is an instance of the Type class, the injection system creates a ResolvedParameter that describes how the container should perform injection to resolve an instance of that type.
                            -In all other cases, the configuration API creates an InjectionParameter instance the container uses to get the value to be injected into a property.

        :res{
                http://unity.codeplex.com/
                https://msdn.microsoft.com/en-us/library/ff647964.aspx
    -Policy injection Block
        :This block provides a mechanism to change object behavior 
        by inserting code between the client and the target object without modifying the code 
        of the target object. The Policy Injection block is not covered in this book
:processes:
    -usage:
        you choose just the features you want to use and  disregard the rest.,but you need to configure it first. 
        you need to add the appropriate assemblies to your project.
    -Configuration Scenarios
        1-External configuration 
                - there are different ways that configuration information can reside in a persistent store.
                    Possible sources of persistent	configuration information are
                        files, a database, and other custom stores.
                but it usually resides in application App.config or web.config file, in XML format..
                -Enterprise Library can load	configuration information from any of these stores automatically.
                -You can manually edit the XML data, 
                    but the Enterprise Library provides two configuration tools that greatly simplify this task. 
                    These tools are the stand-alone configuration console and the configuration editor that is integrated with Visual Studio
                    :res : https://msdn.microsoft.com/en-us/library/ff664633(v=pandp.50).aspx

        2-Programmatic support
                -configuration information can be generated dynamically ,in different ways 
                    and applied to a configuration source at run time.

                Typically, in Enterprise	Library this programmatic configuration takes place through
                    1-the fluent interface specially designed	to simplify dynamic configuration,
                        Using the Fluent Interfaces
                            All of the application blocks expose a fluent interface
                            (except for the Validation Application Block and Policy Injection	Application Block) .
                            
                            This allows you to configure the block at run time using	intuitive code 
                            assisted	by Microsoft IntelliSense® in Visual Studio® to specify the providers andproperties for the block.
                        :X
                            The following is an example of configuring an exception policy
                                for the	Exception Handling Application Block 
                                and loading this configuration into the Enterprise Library :

                            container.
                            var builder = new ConfigurationSourceBuilder();
                            builder.ConfigureExceptionHandling()
                            .GivenPolicyWithName("MyPolicy")
                            .ForExceptionType<NullReferenceException>()
                            .LogToCategory("General")
                            .WithSeverity(System.Diagnostics.TraceEventType.Warning)
                            .UsingEventId(9000)
                            .WrapWith<InvalidOperationException>()
                            .UsingMessage("MyMessage")
                            .ThenNotifyRethrow();
                            var configSource = new DictionaryConfigurationSource();
                            builder.UpdateConfigurationWithReplace(configSource);
                            EnterpriseLibraryContainer.Current
                            = EnterpriseLibraryContainer.CreateDefaultContainer(configSource);
                    2-or by using the methods exposed by the Microsoft® .NETFramework System.Configuration API.
        -senarios:
            1-Scenario 1:					Using the Default Application Configuration File

                This is the default and simplest scenario.
                You configure your application using the configuration tool
                without adding a Configuration Sources section or any configuration sources. You must specify
                either your application's App.config or Web.config file when you save the configuration, or use the
                configuration tool to edit an existing App.config or Web.config file.

            2-Scenario 2: Using a Non-default Configuration Store
                In this scenario, you want to store your configuration in a file or other type of store, instead of in the
                application's App.config or Web.config file. To achieve this you:
                1. Use the configuration tools to add a suitable configuration source to the Configuration
                Sources section. If you want to use a standard format configuration file, add a file-based
                configuration source. To store the configuration information in a different type of store, you
                must install a suitable configuration source. You can use the sample SQL configuration
                source that is available from the Enterprise Library community site at
                http://entlib.codeplex.com to store your configuration in a database.
                2. Set the relevant properties of the new configuration source. For example, if you are using
                the built-in file-based configuration source, set the File Path property to the path and name
                for the configuration file.
                3. Set the Selected Source property in the properties pane for the Configuration Sources
                section to your new configuration source. This updates the application's default App.config
                or Web.config file to instruct Enterprise Library to use this as its configuration source.
            3.Scenario 3: Sharing the Same Configuration between Multiple Applications
                In this scenario, you want to share configuration settings between multiple applications or
                application layers that run in different locations, such as on different computers. To achieve this, you
                simply implement the same configuration as described in the previous scenario, locating the
                configuration file or store in a central location. Then specify this file or configuration store in the
                settings for the configuration source (such as the built-in file-based configuration source) for each
                application.
            4.Scenario 4: Managing and Enforcing Configuration for Multiple Applications
                In this scenario, you not only want to share configuration settings between multiple applications or
                application layers that run on different computers (as in the previous scenario), but also be able to
                manage and enforce these configuration settings for this application or its layers on all machines
                within the same Active Directory® domain. To achieve this you:
                1. Use the configuration tools to add a manageable configuration source to the Configuration
                Sources section.
                2. Specify a unique name for the Application Name property that defines the application
                within the Active Directory repository and domain.
                3. Set the File Path property to the path and name for the configuration file.
                4. Set the Selected Source property in the properties pane for the Configuration Sources
                section to the new manageable configuration source. This updates the application's default
                App.config or Web.config file to instruct Enterprise Library to use this as its configuration
                file.
                5. After you finish configuring the application blocks and settings for your application, rightclick the title bar of the manageable configuration source and select Generate ADM
                Template. This creates a Group Policy template that you can install into Active Directory.
                The template contains the settings for the application blocks, and configuring them in Active
                Directory forces each application instance to use the centrally specified settings
            5.Scenario 5: Sharing Configuration Sections across Multiple Applications
                In this scenario, you have multiple applications or application layers that must use the same shared
                configuration for some application blocks (or for some sections of the configuration such as
                connection strings). Effectively, you want to be able to redirect Enterprise Library to some shared
                configuration sections, rather than sharing the complete application configuration. For example, you
                may want to specify the settings for the Logging Application Block and share these settings between
                several applications, while allowing each application to use its own local settings for the Exception
                Handling Application Block. You achieve this by redirecting specific configuration sections to
                matching sections of a configuration store in a shared location. The steps to implement this scenario
                are as follows:
                1. Use the configuration tools to add a suitable configuration source for your application to the
                Configuration Sources section. This configuration source should point to the shared
                configuration store. If you want to use a standard format configuration file as the shared
                configuration store, add a file-based configuration source. To store the shared configuration
                information in a different type of store, you must install a suitable configuration source. You
                can use the sample SQL configuration source that is available from the Enterprise Library
                community site at http://entlib.codeplex.com to store your configuration in a database.227
                2. Set the relevant properties of the shared configuration source. For example, if you are using
                the built-in file-based configuration source, set the File Path property to the path and name
                for the application's configuration file.
                3. Set the Selected Source property in the properties pane for the Configuration Sources
                section to System Configuration Source.
                4. Click the plus-sign icon in the Redirected Sections column and click Add Redirected Section.
                A redirected section defines one specific section of the local application's configuration that
                you want to redirect to the shared configuration source so that it loads the configuration
                information defined there. Any local configuration settings for this section are ignored.
                5. In the new redirected section, select the configuration section you want to load from the
                shared configuration store using the drop-down list in the Name property. The name of the
                section changes to reflect your choice.
                6. Set the Configuration Source property of the redirected section by selecting the shared
                configuration source you defined in your configuration. This configuration source will
                provide the settings for the configuration sections that are redirected.
                7. Repeat steps 4, 5, and 6 if you want to redirect other configuration sections to the shared
                configuration store. Configuration information for all sections for which you do not define a
                redirected section will come from the local configuration source.
                8. To edit the contents of the shared configuration store, you must open that configuration in
                the configuration tools or in a text editor; you cannot edit the configuration of shared
                sections when you have the local application's configuration open in the configuration tool.
                If you open the shared configuration in the configuration tool, ensure that the Selected
                Source property of that configuration is set to use the system configuration source.
                You cannot share the contents of the Application Settings section. This section in the configuration
                tool stores information in the standard <appSettings> section of the configuration file, which
                cannot be redirected.
            Scenario 6: Applying a Common Configuration Structure for Applications
                In this scenario you have a number of applications or application layers that use the same
                configuration structure, and you want to inherit that structure but be able to modify or add
                individual configuration settings by defining them in your local configuration file. You can specify a
                configuration that inherits settings from a parent configuration source in a shared location, and
                optionally override local settings. For example, you can configure additional providers for an
                application block whose base configuration is defined in the parent configuration. The steps to
                implement this scenario are as follows:
                1. Use the configuration tools to add a suitable configuration source for your application to the
                Configuration Sources section. This configuration source should point to the shared
                configuration store. If you want to use a standard format configuration file as the shared
                configuration store, add a file-based configuration source. To store the shared configuration
                information in a different type of store, you must install a suitable configuration source. You228
                can use the sample SQL configuration source that is available from the Enterprise Library
                community site at http://entlib.codeplex.com to store your configuration in a database.
                2. Set the relevant properties of the shared configuration source. For example, if you are using
                the built-in file-based configuration source, set the File Path property to the path and name
                for the application's configuration file.
                3. Set the Parent Source property in the properties pane for the Configuration Sources section
                to your shared configuration source. Leave the Selected Source property in the properties
                pane set to System Configuration Source.
                4. Configure your application in the usual way. You will not be able to see the settings
                inherited from the shared configuration source you specified as the parent source.
                However, these settings will be inherited by your local configuration unless you override
                them by configuring them in the local configuration. Where a setting is specified in both the
                parent source and the local configuration, the local configuration setting will apply.
                5. To edit the contents of the shared parent configuration store, you must open that
                configuration in the configuration tools or in a text editor; you cannot edit the configuration
                of parent sections when you have the local application's configuration open in the
                configuration tool. If you open the parent configuration in the configuration tool, ensure
                that the Selected Source property of that configuration is set to use the system
                configuration source.
                The way that the configuration settings are merged, and the ordering of items in the resulting
                configuration, follows a predefined set of rules. These are described in detail in the documentation
                installed with Enterprise Library and available online at
                http://go.microsoft.com/fwlink/?LinkId=188874.
            Scenario 7: Managing Configuration in Different Deployment Environments
            In this scenario, you want to be able to define different configuration settings for the same
            application that will be appropriate when it is deployed to different environments, such as a test and
            a production environment. In most cases the differences are minor, and usually involve settings such
            as database connection strings or the use of a different provider for a block. Enterprise Library
            implements this capability using a feature called environmental overrides. The principle is that you
            specify override values for settings that are different in two or more environments, and the
            differences are saved as separate delta configuration files. The administrator then applies these
            differences to the main configuration file when the application is deployed in each environment. To
            achieve this:
            1. Follow the instructions in the step-by-step procedure in the section "Using the Configuration
            Tools" in Chapter 1, "Introduction," which describes how you configure multiple
            environments in the configuration tools and how you define the overridden settings.
            2. Open the properties pane for each of the environments you added to your configuration by
            clicking the chevron arrow to the right of the environment title, and set the Environment
            Delta File property to the path and name for the delta file for that environment.229
            3. Save the configuration. The configuration tool generates a normal (.config) file and a delta
            (.dconfig) file for each environment. The delta file(s) can be managed by administrators, and
            stored in a separate secure location, if required. This may be appropriate when, for
            example, the production environment settings should not be visible to developers or
            testers.
            4. To create a run-time merged configuration file (typically, this is done by an administrator):
            ◦ Open the local configuration (.config) file.
            ◦ Select Open Delta File from the Environments menu and load the appropriate
            override configuration (.dconfig) file.
            ◦ Set the Environment Configuration File property in the properties pane for the
            environment to the path and name for the merged configuration file for that
            environment.
            ◦ Right-click on the title of the environment and click Export Merged Environment
            Configuration File.
            5. Deploy the merged configuration file in the target environment.
            Enterprise Library also contains a command-line utility named MergeConfiguration.exe that you can
            use to merge configuration and delta files if you do not have the configuration console deployed on
            your administrator system. It can also be used if you wish to automate the configuration merge as
            part of your deployment process. Information about MergeConfiguration.exe is included in the
            documentation installed with Enterprise Library
```			
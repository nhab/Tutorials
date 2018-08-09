```
:termoprocs{
    basic topics 		

        Data Types

            complex Data Types

                array

                    int[,]myArr=new int[10,10];

                jagged arrays

                    :rows dimensionsize are not equal

                    int[]jarr=new int[10][];

                    jarr[0]=new Type[5];

                    jarr[1]=new Type[7];

                nullable type

                    : to which you can assign normal range of values as well as null values.

                    syntax

                        < data_type> ? <variable_name> = null;

                    x:

                        int? num1 = null;

                string functions

        Type Conversion
        Variables
        Constants
        Operators
        Decision Making

            if,switch

        Loops

            for:	used for arrays

            foreach: used for collections

        Encapsulation

            Encapsulation is implemented by using access specifiers.

                Public

                Private

                Protected

                    :allows a child class to access 

                Internal

                    :allows a class to expose its member variables and member functions to other functions and objects in the current assembly.

                Protected internal

                    :access specifier allows a class to hide its member variables and member functions from other class objects and functions, 

                    except a child class within the same application

        namespace

        Methods

            :can be functions or procedures.but the term is method in c#.

        method optional parameters

        method call without seqence

            x: 

                t(mon:3,day:2);

        

        The Null Coalescing Operator (??)

            :It is used for converting an operand to the type of another nullable (or not) value type operand, where an implicit conversion is possible.

            -If the value of the 1st operand is null,

                returns -> 2nd operand value

            else

                returns ->1st operand value

            X:

                num3 = num1 ?? 5.34;

        refrerence type /value types

        ref and out

            1. a variable you pass as an out parameter doesn`t need to be initialized 

            but passing it as a ref parameter it has to be set to something.      

            2.by ref you also want to pass a value to the  method

        

        structure

            x:

                struct Books

                {

                    public string title;

                    public string author;

                    public string subject;

                    public int book_id;

                };

        classes

        property vs field

            -property can be validated

            - Properties provide a level of abstraction allowing you to change the field

            

            while not affecting the external way they are accessed by the things that use your class.

        member of the class

            all proerty,field,method,Constants ,Indexers ,Operators ,nested types, constructors,Destructors   and events are members

        method and event

        Class versus Structure

            classes are reference types and structs are value types

            structures do not support inheritance

            structures cannot have default constructor

        enum 

            :An enumeration is a set of named integer constants.

        inheritence

            Base and Derived Classes

                X: class <derived_class> : <base_class>

        Polymorphism

            static vs dynamic polymorphism

                In static polymorphism

                    the response to a function is determined at the compile time.

                In dynamic polymorphism,

                    it is decided at run-time.

            early binding( static binding)

                The mechanism of linking a function with an object during compile time

            two techniques to implement static polymorphism:

                Function overloading

                    You can have multiple definitions for the same function name in the same scope. T

                Operator overloading	

        Abstract classes 
            contain abstract methods, which are implemented by the derived class.
            The derived classes have more specialized functionality.
            Here are the rules about abstract classes:

                You cannot create an instance of an abstract class

                You cannot declare an abstract method outside an abstract class

        virtual functions

            When you have a function defined in a class that you want to be implemented (`override`) in an inherited class(es),

            you use `virtual` functions. 	

            When a class is declared `sealed`, it cannot be inherited, abstract classes cannot be declared sealed.

            x:

                using System;

                namespace PolymorphismApplication

                {

                    abstract class Shape 

                    {

                        protected int width, height;

                        public Shape( int a=0, int b=0)

                        {

                            width = a;

                            height = b;

                        }

                        public virtual int area()

                        {

                            Console.WriteLine("Parent class area :");

                            return 0;

                        }

                    }

                    class Rectangle: Shape

                    {

                        public Rectangle( int a=0, int b=0): base(a, b)

                        {



                        }

                        public override int area ()

                        {

                            Console.WriteLine("Rectangle class area :");

                            return (width * height); 

                        }

                    }	

                }

        `new` keyword before method definition

            overriding a method wich is not virtual

        Exceptions

            finally block 

                :regardless you got exception or not,it would be executed

        throw 

            :to make an exception

        Operator Overloading

            You can redefine or overload most of the built-in operators available in C#.

            Thus a programmer can use operators with user-defined types as well. 

            Overloaded operators are functions with special names the keyword operator followed by the symbol for the operator being defined

            x:

                public static Box operator+ (Box b, Box c)

                {

                    Box box = new Box();

                    box.length = b.length + c.length;

                    box.breadth = b.breadth + c.breadth;

                    box.height = b.height + c.height;

                    return box;

                }

        Interfaces
            :?why/usage
                They’re for putting together plug-n-play like architectures whitout referencing the whole (different) Implementations.
            :process
                -definition
                    x:

                        public interface ITransactions

                        {

                            // interface members

                            void showTransaction();

                            double getAmount();

                        }

                -usage:
                        public a:ITransactions
                        {

                            ITransactions.showTransaction()

                            {

                                .....

                            }

                            

                        }
            :some characteristics
                -An interface is like an abstract base class. ...
                -An interface can`t be instantiated directly. ...
                -Interfaces can contain events, indexers, methods, and properties.
                -Interfaces contain no implementation of methods.
                -A class or struct can implement multiple interfaces.
        some Interfaces

            x:

                IComparable,IQuerable,IEnumerable

        Preprocessor Directives

            #define	It defines a sequence of characters, called symbol.

            #undef	It allows you to undefine a symbol.

            #if	It allows testing a symbol or symbols to see if they evaluate to true.

            #else	It allows to create a compound conditional directive, along with #if.

            #elif	It allows creating a compound conditional directive.

            #endif	Specifies the end of a conditional directive.

            #line	It lets you modify the compiler`s line number and (optionally) the file name output for errors and warnings.

            #error	It allows generating an error from a specific location in your code.

            #warning	It allows generating a level one warning from a specific location in your code.

            #region	It lets you specify a block of code that you can expand or collapse .

            #endregion

            ..

        Regular Expressions

            The Regex Class

                x:

                    MatchCollection mc = Regex.Matches(text, @"\bS\S*");

                    foreach (Match m in mc)

                    {

                        Console.WriteLine(m);

                    }

        Debug.assert

        File I/O

            using System.IO namespace

            The FileStream Class

                x:

                    static void Main(string[] args)

                    {

                        FileStream F = new FileStream("test.dat", FileMode.OpenOrCreate, FileAccess.ReadWrite);

                        for (int i = 1; i <= 20; i++)

                        {

                            F.WriteByte((byte)i);

                        }

                        

                        F.Position = 0;

                        for (int i = 0; i <= 20; i++)

                        {

                            Console.Write(F.ReadByte() + " ");

                        }

                        F.Close();

                        Console.ReadKey();

                    }

        Indexer

            -An indexer provides array-like syntax for our class.

            It allows a type to be accessed the same way as an array. 

            Properties such as indexers often access a backing store.

            - When you define an indexer for a class, this class behaves similar to a virtual array. 

            You can then access the instance of this class using the array access operator ([ ]).

            syntax

                element-type this[int index]

                {

                    // The get accessor.

                    get

                    {

                        // return the value specified by index

                    }

                    

                    // The set accessor.

                    set

                    {

                        // set the value specified by index

                    }

                }

        collections(System.Collections)

            Q?:

                when we use which?

            -you can use linq to query collections

            linq syntax:	

                from ... in ...

                where ...

                order by...

                select ...

            {:

                ArrayList

                    interface using an array whose size is dynamically increased as required.

                    -This collection dynamically resizes. It grows in capacity as elements are added (if space is needed). 

                    It is most often used in older C# programs.

                    - It stores elements of type object—casting is needed. 

                    -you can add any type to ArrayList but you can not use methods like `sort()`;

                    We end up with as-casts, numeric casts to test elements. Code becomes messy. Use a List instead.

                Hashtable

                    key/ value pair 

                storedList

                stack

                Dictionary

                

        static classes and members

        dateTime
            mil	liseconds DateTime.Now.ToString("hh.mm.ss.ffffff");

        Events
            1.event creation 
                :X
                    public delegate void OHandler(...,...);
                    public event OHandler oevent;

            2. calling /subscribing/attaching  to event (+=)
                :+= means subscribe.
                    In other words it's like you are telling subscribe my method (the right operand)
                        to this event (the left operand),
                        this way, when the event is raised, your method will be called.
                :OPTS:
                    There are two basic ways to subscribe to an event:
                    1.
                        SomeEvent += MyHandlerMethod;
                    2.
                        SomeEvent += new EventHandler<ArgType> (MyHandlerMethod);
                x:
                        oevent +=dffdgf(...);

            
            3.unsubscribe(-= ) 
                    :unsubscribe from this event,
                    when you have finished your work 
                    ( but before you dispose you object ) 
                    in order to prevent your method being called and to prevent resource leaks. 

    Advanced Topics
        Performance counter

            if(!PeformanceCounterCategort.Exists("fdg sdfg sdfg sdfg"))

                    ....;

            you can see the result under windows control panel/performance monitor

            

        Using Application Profiling	
        delegates

            :are types for method signature.

            -are like C++ function pointers, with a big difference that they are type safe.

            -Delegates define a type, which specify a particular method signature. A method (static or instance) that satisfies this signature can be assigned to a variable of that type, then called directly (with the appropriate arguments) or passed as an argument itself to another method and then called

            X:

                public class Program

                {

                public delegate string Reverse(string s);

                static string ReverseString(string s)

                {

                    return new string(s.Reverse().ToArray());

                }

                static void Main(string[] args)

                {

                    Reverse rev = ReverseString;

                    Console.WriteLine(rev("a string"));

                }

                }


        boxing/unboxing

            boxing is assigning from value type to reference type

                x:

                    int i=1;object o;o=i;

            unboxing x: int j;j=(int)o;

        unit test

            in the function (1.	arrange 2.	 act 3.assert)

        Generic class(type safe collections)
            :Generic classes encapsulate operations that are not specific to a particular data type. 
            The most common use for generic classes is with collections like linked lists, hash tables, stacks, queues, trees, and so on. 
            Operations such as adding and removing items from the collection are performed in basically the same way 
            regardless of the type of data being stored.
            -T is a keyword in c#
            x:
                public class customList<T>
                {
                    public T this[int index]{get;set}
                    public void Add(T item)
                    {

                    }

                }

        constraining type parameter by interface

            (there are 6 types of it)

            X: public class customlist<T> where T:INeverage

        abstract vs sealed

            abstract cant be instantiated.	

            sealed a class that cant be inherited

        creating custom exceptions
        creating extention method

            :Extension methods are a special kind of static method, but they are called as if they were instance methods on the extended type.

            there is no apparent difference between calling an extension method and the methods that are actually defined in a type.

            ?:are used to extend sealed classes(like string class)

            :-by preceding the parameter with 'this` keyword you indicate to compiler that your method is an extension method to that type

                x:

                    public static bool ContainesNumbers(this String s)

                    ..

                    String text="hjgfhjghj";

                    if(text.ContainsNumbers)...		

        GAC(global assembley cache)	

            GacUtil -i dllName :to register a dll in GAC

            Creating strong name key for assembley: to be able to add it to GAC

            gacUtil -l:to list assembley

        Files

            Ref:System.Io.File class

                string s=File.ReadAllText(..);

        serialization

            [Serializable]/[NonSerializedAttribute]

            BinarFormatter/ SoapFormatter

            JSonFormatter	

        Streaming

            FileStram

        Partial class
        Accessing a database

            -Entity Data Models

            To modify an entity/ customize the model classes:

                we can add other file to project and define a partial class for the entity we want to modify

            -DBContext.Employee.First(e=>e.LastName=="Prest");

            -DBContext.SaveChanges();

            -linq syntax

                Anonymous Type (by using 'new')/ and usage of group ..by

                    var emps=from e in DBContext.Employees

                        group e by e.JobTitle into eGroup

                        select new {job=eGroup.Key,CountOfEmployees=eGroup.Count()}

                Deferred vs Immediate Query Execution in LINQ

                    In deferred query execution, the LINQ query is not sent or executed against the database 

                    until the object created is iterated by the user

        .net Remoting

            :.NET remoting enables you to build widely distributed applications easily,

            whether application components are all on one computer or spread out across the entire world

            {:

                A remotable object.

                A host application domain to listen for requests for that object.

                A client application domain that makes requests for that object.



            Data contract

                is a class with extra attribute named [DataContract()] and its members attributed by [DataMember()]

            service

            {

                asmx web service

                wcf

                

            ?:creating wcf web service :

                VS>new Project>WCF>WCF Project library		

                - ISErvice interface has [serviceContract] attribute

                - Iservic has GetData method which has attribute of [OperationContract]

                -we can add any method signeture to IService with 	 [OperationContract] attribute

            ?:to use wcf web service:

                - vs>new console application

                - Add Service reference

                -copy url of the previously created web service into Address and discover it and ok

                -then you can use methods of recently added web service class ,in your code

            WCF Data Service

                a service which retreives data rom database

                ?:

                    in your project>Add WCF Data service item to your project>change wcfDataService1 class >

                    -change DataService type to your dataContext from your entity model

                    -in InitializeService uncomment config.setEntitySetAccessRule and change parameters to yours.

                    -(you should turn of your browser`s feed reading ,to see the result in browser)

        WPF	

            user control

                :you can have a XAML user control.

                usage ?:you can use it by adding its namespace xmlns: in <window x:Class....>

            reusable resources

                x:

                    <Window.Resources>

                        <sys:String x:Key="strHelloWorld">Hello, world!</sys:String>

                    </Window.Resources>

                -Resource Dictionary

                    :A place to add all resources for wcf project here

                    ?:

                        Add new project item : Resource Dictionary (wcf)

                

            The ability to store data as a resource

                X:

                    <Window x:Class="WpfTutorialSamples.WPF_Application.ResourceSample"

                        xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"

                        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"

                        xmlns:sys="clr-namespace:System;assembly=mscorlib"

                        Title="ResourceSample" Height="150" Width="350">

                        <Window.Resources>

                            <sys:String x:Key="strHelloWorld">Hello, world!</sys:String>

                        </Window.Resources>

                        <StackPanel Margin="10">

                            <TextBlock Text="{StaticResource strHelloWorld}" FontSize="56" />

                            <TextBlock>Just another "<TextBlock Text="{StaticResource strHelloWorld}" />" example, but with resources!</TextBlock>

                        </StackPanel>

                    </Window>

            Binding

                <TextBlock Text="{Binding Source={StaticResource coffe1},path=Bean}" />

        Timing
            Async ,await

                when you want to download a movie ,you dont want to wait until the download is completed.

                you can use "async" in the download method definition and "await" in its usage.

            dispatcher
                :Provides services for managing the queue of work items for a thread.
                x:
                    Your app has a main UI thread (usually ManagedThreadId==1). 

                    Typically in a chat app your events will come in on other threads

                    (either dedicated socket listen threads or thread pool threads from listening code).

                    If you want to update the UI from an event that gets pull on some other thread you must use the dispatcher.

                        A useful test here is the Dispatcher.CheckAccess() method that returns true if code is on UI thread 

                        and false if on some other thread. A typical call looks something like:



                        using System.Windows.Threading; // For Dispatcher.



                        if (Application.Current.Dispatcher.CheckAccess()) {

                            network_links.Add(new NetworkLinkVM(link, start_node, end_node));

                        }

                        else {

                            Application.Current.Dispatcher.BeginInvoke(DispatcherPriority.Normal, new Action(()=>{

                                network_links.Add(new NetworkLinkVM(link, start_node, end_node));

                            }));

                        }



                    If you`re in the main window you can use:

                    Dispatcher.BeginInvoke(...

                    If you`re in someother context eg a view model then use:

                    Application.Current.Dispatcher.BeginInvoke(  ...

            another aproach

                var task4=Task.Run(()=>Consol.Writeln('ghjghj'));

                task1.Run();

            another approach

                Task task1=new Task(new Action(f2));

            another aproach

                in async method:

                Task<int> task1=Task.Run<int>(()=>Total(3,2));

                label1.Content=await task1;

                ...

                

            Sleep

                System.Threading.Thread.Sleep(1000);

            returning values 

                Task<string> task1 =task.Run<string>(()=>DateTime.Now.DayOfWeek.ToString());

            Parallel

                :Provides support for parallel loops and regions.

                REF:(System.Threading.Tasks)

                Parallel.For(from,to,index=>{...});

                Parallel.ForEach

            Task Cancelation

            nested tasks

            child tasks

        callback method
            : a method with a single parameter of type string that doesn`t return anything(void) :
            public void DoRequest(string request, Action<string> callback)
            {

                // do stuff....

                callback("asdf");

            }

            

        Anonymous delegate

            X:

                Task task1=new Task(new delegate{console.writeln('hjghjgh')});

        locking

            when you want to ensure some pease of code to be run not paralell with any code,you lock it:

                X:

                    lock(cofeelock)		{.....}

            

            

        IsNullOrEmpty

            :The string.IsNullOrEmpty method tests strings.

            It checks for string references that are null or have no data.

            Strings are reference types and can be equal to null.

    

        automatic properties

            X: public bool Discontinued { get; set; }

        Type safety 

            means that the compiler will validate types while compiling, and throw an error if you try to assign the wrong type to a variable.

        CLR

            :compiles msil to os native exe s

        Unmanaged Codes

            :the codes are not under donet framework is unmanaged code(unmanaged by clr)

        dynamic (data type)
            :
                is a keyword shows a data type which is not under   compile-time type checking .(is not managed code)
                -Type dynamic behaves like type object in most circumstances.
                
                - at compile time, an element that is typed as dynamic is assumed to support any operation.

                Therefore, you do not have to be concerned about whether the object gets its value from a COM API, from a dynamic language
                such as IronPython, from the HTML Document Object Model (DOM), from reflection, or from somewhere else in the program.
                However, if the code is not valid, errors are caught at run time.
            X:

                dynamic word=new Application;

                dynamic doc=word.Documents.Add();

                doc.Activate();

        DLR

            :The purpose of the DLR is to enable a system of dynamic languages to run on the .NET Framework and give them .NET interoperability.

            -The dynamic language runtime (DLR) is a runtime environment 

            that adds a set of services for dynamic languages to the common language runtime (CLR). 

            -The DLR makes it easier to develop dynamic languages to run on the .NET Framework 

            and to add dynamic features to statically typed languages.



            Dynamic languages can identify the type of an object at run time,

            whereas in statically typed languages such as C# and Visual Basic (when you use Option Explicit On) 

            you must specify object types at design time.

            Examples of dynamic languages are Lisp, Smalltalk, JavaScript, PHP, Ruby, Python, ColdFusion, Lua, Cobra, and Groovy.



            Most dynamic languages provide the following advantages for developers:

                The ability to use a rapid feedback loop		 (REPL, or read-evaluate-print loop).

                    This lets you enter several statements and immediately execute them to see the results.

                Support for both top-down development and more traditional bottom-up development. For example, when you use a top-down approach, you can call functions that are not yet implemented and then add underlying implementations when you need them.

                Easier refactoring and code modifications, because you do not have to change static type declarations throughout the code.

                Dynamic languages make excellent scripting languages. 

                Customers can easily extend applications created by using dynamic languages with new commands and functionality.

                Dynamic languages are also frequently used for 

                    creating Web sites and test harnesses,

                    maintaining server farms, 

                    developing various utilities,

                    and performing data transformations.



            

            The DLR introduces dynamic objects to C# and Visual Basic in Visual Studio 2010

            to support dynamic behavior in these languages and enable their interoperation with dynamic languages.

            The DLR also helps you create libraries that support dynamic operations.

            For example, if you have a library that uses XML or JavaScript Object Notation (JSON) objects, 

            your objects can appear as dynamic objects to languages that use the DLR.

            This lets library users write syntactically simpler and more natural code for operating with objects and accessing object members.

            For example, you might use the following code to increment a counter in XML in C#.

                Scriptobj.SetProperty("Count", ((int)GetProperty("Count")) + 1);

            By using the DLR, you could use the following code instead for the same operation.

                scriptobj.Count += 1;

        IDisposable

            Dispose()

            using 

                :destroys containg object automatically for objects which are implementing IDisposable interface

        attributes

            : associating declarative tag  to convey information to runtime of various elements C# code elements 

            (like types, methods, properties, and so forth).

            -3 pre-defined attributes

            {:

                1- [Obsolete("Use MethodB instead")]

                2- [AttributeUsage(   validon,   AllowMultiple=allowmultiple,   Inherited=inherited)]

                    :describes how a custom attribute class can be used

                    X:

                        [AttributeUsage(AttributeTargets.Class |AttributeTargets.Constructor |AttributeTargets.Feild |

                        AttributeTargets.Method |AttributeTargets.Property,AllowMultiple = true)]

                3-[Conditional("DEBUG")]

                    means it will be compiled if it is debug mode

            Declaring a Custom Attribute

                using System;

                [AttributeUsage(AttributeTargets.All)]

                public class HelpAttribute : System.Attribute 

                {

                public readonly string Url;



                public string Topic               // Topic is a named parameter

                {

                    get 

                    { 

                        return topic; 

                    }

                    set 

                    { 



                        topic = value; 

                    }

                }



                public HelpAttribute(string url)  // url is a positional parameter

                {

                    this.Url = url;

                }



                private string topic;

                }

        Object metadata /reflection
        System.CodeDOM

            :to build source code model using CodeDOM elements to assemble an object graph.

        Encryption
        Preprocessor Directives
            :The preprocessor directives give instruction to the compiler to preprocess the information before actual compilation starts.
            :{
                #define 		It defines a sequence of characters, called symbol.
                #undef 		It allows you to undefine a symbol.
                #if 			It allows testing a symbol or symbols to see if they evaluate to true.
                #else 		It allows to create a compound conditional directive, along with #if.
                #elif 		It allows creating a compound conditional directive.
                #endif 		Specifies the end of a conditional directive.
                #line 		It lets you modify the compiler`s line number and (optionally) the file name output for errors and warnings.
                #error 		It allows generating an error from a specific location in your code.
                #warning 	It allows generating a level one warning from a specific location in your code.
                #region 		It lets you specify a block of code that you can expand or collapse when using the outlining feature of the Visual Studio Code Editor.
                #endregion 	It marks the end of a #region block.
        
        Extension method 
            Extension method ها توابع static  در درون کلاس های static می باشد که به شما امکان می دهد تا متود استاتیک دلخواه را در یک کلاس کمکی ایجاد کرده و
                آنها را به فهرست متدهای یک کلاس دیگر اضافه کرد بدون آن که مجبور به دستکاری کلاس اصلی شوید.

            فکر کنید چقدر خوب بود که نوع داده String دارای متدی جهت حذف تگ‌های HTML داشت و یا کلاس Image دارای متدی جهت تغییر اندازه (Resize) داشت و …

            Extension method ها به همین منظور متولد شده اند. در واقع هر زمان بدنه کلاسی (DataType، کنترل و تمام اشیاء دات نتی) در اختیار ما نباشد
                امکان اضافه کردن متد الحاقی به آنها وجود دارد.
            برای نوشتن Extension method ها باید موارد زیر را مد نظر داشته باشید

            1- این توابع بصورت public static تعریف شوند.

            2- کلاسی که این متد در داخل آن تعریف می شود نیز باید بصورت public static تعریف شود.

            3- اولین پارامتر ورودی این توابع باید با کلمه کلیدی this همراه باشد و این پارامتر اشاره به کلاسی دارد که متد جاری به آن الحاق (یا ضمیمه) خواهد شد.

            یک مثال

            public static class  MyExtensions

            {

            public static int WordCount(this String str)

            {

            return str.Split(new char[] { ‘ ‘, ‘.’, ‘,’ }).Length;

            }

            }

            و فراخوانی آن :

            class Program

            {

            public static void Main()

            {

            string s = “What is Extension Method in RTWO.ir “;

            int i = s.WordCount();

            Console.WriteLine(i);

            }

            }
:process
    // retrieve ConnectionString from config file
        ConnectionStringSettings cs = ConfigurationManager.ConnectionStrings[Constants.CONNECTION_STRING_NAME];
        ConnectionString = cs.ConnectionString;
:ref
        microsoft knowledgebase https://support.microsoft.com/en-us
        syllabus of microsoft c# training: https://www.microsoft.com/en-in/learning/course.aspx?cid=20483
    cheah kk
        msil (microsoft intermediate language): assembley
        microsoft certificate
            ?:
                mcp,mcts(ms certificate technical specialist)
                obljective online exam.(2 to 2.5 hours)
                immidiately result is shown
                objectives: multi option questions
            REF:
                https://www.microsoft.com/en-us/learning/default.aspx
                certificate https://www.microsoft.com/en-us/learning/mcsd-windows-store-apps-certification.aspx
                Microsoft Official Courses On-Demand https://www.microsoft.com/en-us/learning/on-demand-online-courses.aspx
```
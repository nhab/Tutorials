```
File and stream i/o
    Isolated Storage
        :
            For desktop apps, isolated storage is a data storage mechanism 
            that provides isolation and safety
            by defining standardized ways of associating code with saved data.
            
            Standardization provides other benefits as well.
            Administrators can use tools designed to manipulate isolated storage 
            to configure file storage space, set security policies, and delete unused data. 
            
            With isolated storage,
            your code no longer needs unique paths to specify safe locations in the file system, 
            and data is protected from other applications that only have isolated storage access. 
            Hard-coded information that indicates where an application's storage area is located is unnecessary.
        :termoprocs:
            -Save to and Load from Isolated Storage with LINQ to XML
                :X
                    using System.IO;
                    using System.Xml.Linq;
                    using System.IO.IsolatedStorage;

                    XDocument doc = new XDocument(
                        new XComment("This is a comment"),
                        new XElement("Root",
                        new XElement("Child1", "data1"),
                        new XElement("Child2", "data2")
                        )
                    );

                    using (IsolatedStorageFile isoStore = IsolatedStorageFile.GetUserStoreForApplication())
                    {
                        using (IsolatedStorageFileStream isoStream =
                            new IsolatedStorageFileStream("myFile.xml", FileMode.Create, isoStore))
                            {
                                doc.Save(isoStream);
                            }
                    }

                    using (IsolatedStorageFile isoStore = IsolatedStorageFile.GetUserStoreForApplication())
                    {
                        using (IsolatedStorageFileStream isoStream = new IsolatedStorageFileStream("myFile.xml", FileMode.Open, isoStore))
                        {
                            XDocument doc1 = XDocument.Load(isoStream);
                            OutputTextBlock.Text = doc1.ToString();
                        }
                    }
                :x saving
                    private static void Serialize(string fileName, object source)
                    {
                        var userStore = IsolatedStorageFile.GetUserStoreForApplication();
                        using (var stream = new IsolatedStorageFileStream(fileName, FileMode.Create, userStore))
                        {
                            XmlSerializer serializer = new XmlSerializer(source.GetType());
                            serializer.Serialize(stream, source);
                        }
                    }
                :x loading
                    public static void Deserialize<T>(ObservableCollection<T> list , string filename)
                    {

                        list = new ObservableCollection<T>();

                        var userStore = IsolatedStorageFile.GetUserStoreForApplication();
                        if (userStore.FileExists(filename))
                        {
                            using (var stream = new IsolatedStorageFileStream(filename, FileMode.Open, userStore))
                            {
                                XmlSerializer serializer = new XmlSerializer(list.GetType());
                                var items = (ObservableCollection<T>)serializer.Deserialize(stream);

                                foreach (T item in items)
                                {
                                    list.Add(item);
                                }
                            }
                        }
                    }
System.Threading
    :TERMOPROCS:
        simple theading
            :x
                using System;
                using System.Threading;
                class ThreadTest
                {
                    static void Main()
                    {
                    Thread t = new Thread (WriteY);          // Kick off a new thread
                    t.Start();                               // running WriteY()
                    
                    // Simultaneously, do something on the main thread.
                    for (int i = 0; i < 1000; i++) Console.Write ("x");
                    }
                    
                    static void WriteY()
                    {
                    for (int i = 0; i < 1000; i++) Console.Write ("y");
                    }
                }
                //result:
                //xxxxxxxxxxxxxxxxyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy
                //xxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxyyyyyyyyyyyyy
                //yyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyxxxxxxxxxxxxxxxxxxxxxx
                //xxxxxxxxxxxxxxxxxxxxxxyyyyyyyyyyyyyyyyyyyyyyyyyyyyyyy
                //yyyyyyyyyyyyyxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxxx
                //...
        Thread synchronization 
            is the concurrent execution of two or more threads that share critical resources
```
__Where to write php code?__
1. in pure php file with extention .php
1. inside an html file:
        <?php
            .
            .
            php code 
            .
            .
        ?>
__Comments__ are lie c++: <br>
        // و /*...*/
__To print a statement :__
    Echo و  PRINT : <br>
    ````
        <?php echo "i like it" ?>
        <?php print "I like it" ?>
    ````
    -متغیرها :
        نیاز به تعریف کردن ندارند و هرجا استفاده شوند ازآن به بعد شناخته میشوند فقط نامشان باید با $ شروع شوند:
        <?php
            $like="I like it";
            print $like;
        ?>
        متغیرها کیس سنسیتیو اند.
    -برای ترکیب متغیرها و استرینگها از . استفاده میکنیم :
        print $like ." " .$num;
    -با {} میتوانیم نام متغیر را هم داینامیک کنیم:
        $test="success";
        $primary="test";
        $ID=${$primary};
        echo $ID;
    -آرایه ها :
        $a=array{1,2,3,4,5};
        <?php f[0]="j";f[1]="a";f[2]="r"; 
    -operator ها :
        مانند سی هستند:
    -if  ماننذ سی هست:
        if ($arr){$price=0.90;}else{..}
    -حلقه ها:
        مانند سی هستند:      
        <?php
            for($num=1;$num<=10;$num++)
            {
                print $num." ";
            }
            /*----------------*/
            while($num<=10)
            {
                ...
            }
            /*---------------*/
            <$php
                $a=array(1,2,3,4,5);
                foreach($a as $b)
                {
                    print $b." ";
                }
            ?>
    -توابع:
        <$php
            function examplefunc()
            {
                print "Hi <br>";
            }
            print "sample line:<br>";
            examplefunc();
            $s=examplefunc();
            print $s;
        ?>
        - آرگومان های  با ریفرنس توابع :
        &:
        function add_some(&$str1){...}
        -مقدار دیفالت آرگومان تابع:
        function makeCoffe($types=array("cappuccino",$coffeMaker=Null)){..}
    -تابع یافتن آی پی شخص بازدید کننده :
        Getenv("REMOTE_ADDR")
    -آپلود یک فایل :
        <form enctype="multipart/form-data" action="upload.php" method="post">
        فایل خود را انتخاب کنید :
        <input name="uploaded" type="file" /><br />
        <input type="submit" value="Upload" />
        </form>
    -برای استفاده از متغیرهای در سطح سشن ابتدا آنها را تعریف می کنیم:
        <?php
            session_start();تابع لازم
            $_SESSION['Color']='red';
            $_SESSION['size']='small';
            ...
        ?>
    سپس در صغحه دوم  از آن متغیرها استفاده می کنیم:
        <?php
         session_start();
         echo $_SESSION['color'];
         echo $_SESSION['size'];
         ?>
    -print_r($SESSION)  کل سشن را چاپ میکند
    -برای تغییر یک متغیر سشن کافیست به آن مقدار جدید بدهیم و برای حذف آن از 
    unset 
    استفاده کنیم:
         $_SESSION['size']='larg';
         unset( $_SESSION['shape']);
         برای حذف کلی : session_unset();
                        session_destroy();
    -کار با فایل :
        تابع fopen :
            <?php
            $a=fopen("/home/files/yourfile.txt","r");
            $b=fopen("yourfile.gif","w");
            r  مد را مشخص میکند
            مدهای دیگر باز کردن فایل :
            x+,x,a+,a,w+,w-,r+,r-
            برخی توابع کار با فایلها:
            fwrite();
            file_get_contents();کل محتوای فایل را بصورت یک رشته برمیگرداند
            file();
            fgets(); برای خواندن یک خط یک خط از فایل
            fread();
        مثال file():
            $lines=file('yourfile.txt');
            foreach($lines as $line_num=>$line)
            {
                print"<font color='red'> line # {$line_num}</font>;".$line."<br/>\n";
            }
        مثال fgets()
            <?php
            $myFile="yourfile.txt";
            $handle=fopen($myFile,'r');
            while(!feof($handle))
            {
                $data=fgets($handle,512);
                echo $data;
                echo "<br>";
            }
            fclose($handle);
            ?>
    -include
     برای اینکلود کردن فایلهای دیگر به یک فایل پی اچ پی از دو تابع زیر استفاده میشود:
     INCLUDE(),REQUIRE()
     مثال :
        Include 'http://www.yoursite.com/path/file.php';
    -میتوانیم در داخل یک فایل متغیرهای گلوبال بگذاریم و آنرا در همه جا اینکلود کنیم
    حتی اگر کلمه گلوبال را جلوی تعریف متغیر بگذاریم میتوان آنرا در داخل هر تابعی استفاده کرد.مثل::
    <?php
        function printname()
        {
            global $name;
            include 'variables.php';
            print $name;
        }
    حتی میتوان فایلهای تکست یا اچ تی ام ال را اینکلود کرد
    -کار با کلاس
        <?php
        class test{
            public static function run(){
                print "works\n";
            }
            $ClassName='test';
            $ClassName::run();
        }

:phpMysql:
    - برای وصل شدن
:procs
    -hello world :X:
        <!DOCTYPE html><html><body>
        <?php
        echo "My first PHP script!";
        ?>
        </body></html> 
    -install
        can be direct install or wap/lamp install
    -form handling
        -A Simple HTML Form
            <html>
            <body>

            <form action="welcome.php" method="post">

            Name:   <input type="text" name="name">  <br>
            E-mail: <input type="text" name="email"> <br>

            <input type="submit">
            </form>

            </body>
            </html>
    -include 'filename';require 'filename';
        <html>
        <body>

        <div class="menu">
        <?php include 'menu.php';?>
        </div>

        <h1>Welcome to my home page!</h1>
        <p>Some text.</p>
        <p>Some more text.</p>

        </body>
        </html>
    -database
        -Open a Connection to MySQL 
            //Example (MySQLi Object-Oriented)
                <?php
                    $servername = "localhost";
                    $username = "username";
                    $password = "password";

                    // Create connection
                    $conn = new mysqli($servername, $username, $password);

                    // Check connection
                    if ($conn->connect_error) {
                        die("Connection failed: " . $conn->connect_error);
                    }
                    echo "Connected successfully";
                    ?>   
                //Example (MySQLi Procedural)
                    <?php
                    $servername = "localhost";
                    $username = "username";
                    $password = "password";

                    // Create connection
                    $conn = mysqli_connect($servername, $username, $password);

                    // Check connection
                    if (!$conn) {
                        die("Connection failed: " . mysqli_connect_error());
                    }
                    echo "Connected successfully";
                    ?> 
                //Example (PDO)
                    <?php
                    $servername = "localhost";
                    $username = "username";
                    $password = "password";

                    try {
                        $conn = new PDO("mysql:host=$servername;dbname=myDB", $username, $password);
                        // set the PDO error mode to exception
                        $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
                        echo "Connected successfully";
                        }
                    catch(PDOException $e)
                        {
                        echo "Connection failed: " . $e->getMessage();
                        }
                    ?> 
                -Insert
                    Example (PDO) and get last id
                        <?php
                        $servername = "localhost";
                        $username = "username";
                        $password = "password";
                        $dbname = "myDBPDO";

                        try {
                            $conn = new PDO("mysql:host=$servername;dbname=$dbname", $username, $password);
                            // set the PDO error mode to exception
                            $conn->setAttribute(PDO::ATTR_ERRMODE, PDO::ERRMODE_EXCEPTION);
                            $sql = "INSERT INTO MyGuests (firstname, lastname, email)
                            VALUES ('John', 'Doe', 'john@example.com')";
                            // use exec() because no results are returned
                            $conn->exec($sql);
                            echo "New record created successfully";
                                $last_id = $conn->lastInsertId();
                            echo "New record created successfully. Last inserted ID is: " . $last_id;
                            }
                        catch(PDOException $e)
                            {
                            echo $sql . "<br>" . $e->getMessage();
                            }

                        $conn = null;
                        ?> 
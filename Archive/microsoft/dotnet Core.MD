```
ref:
    https://www.microsoft.com/net/core#windows
    https://dotnet.github.io/
:.NET Core is a cross-platform implementation of .NET 
:Process 
    -hello world:
        1-initialize some code
            mkdir hwapp
            cd hwapp
            dotnet new

        2-Run the app
            dotnet restore
            dotnet run

{:

    .NET Core command-line (CLI) tools

        :used for building .NET Core apps and libraries through your development flow

        (compiling, NuGet package management, running, testing, ...). http://dotnet.github.io/

    -CLI: 

        a set of standalone command-line (CLI) tools, 

    -a shared framework 

    -DNX services:

        a set of runtime services.

        The DNX services will be offered as a hosting option available to apps. You can opt to use a host that offers one or more of these services, like file change watching or NuGet package servicing 

?:

    1.Install .NET Core from

    https://dotnetcli.blob.core.windows.net/dotnet/beta/Installers/1.0.0.001598/dotnet-win-x64.1.0.0.001598.exe

    2.Initialize some code

        x:

            mkdir hwapp

            cd hwapp

            dotnet new

    3.run

        x:

            dotnet restore

            dotnet run
```
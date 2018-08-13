```
#MVC 6 (http://proudmonkey.azurewebsites.net/asp-net-5-getting-started-with-mvc-6/)
    view
        -The @inject directive allows you to inject some method calls from a class or service directly into your view

            x:(how to inject a class in the View:)

                @model IEnumerable<MVC6Demo.Models.DOTAHero>

                @inject MVC6Demo.Models.HeroStats Stats



                <div>  

                    <span>Number of Strength: @await Stats.GetHeroCountByType("strength")</span><br/>

                    <span>Number of Agility: @await Stats.GetHeroCountByType("agility")</span><br/>

                    <span>Number of Intelligence: @await Stats.GetHeroCountByType("intelligence")</span><br />

                    <span>Total Heroes: @await Stats.GetHeroCount()</span>

                </div>  

            Now in order for it work we need to configure the AddTransient() method by adding the HeroStats model into it:

                public void ConfigureServices(IServiceCollection services)  

                {

                    services.AddMvc();

                    services.AddTransient<MVC6Demo.Models.HeroStats>();

                }

        -View Components

            :a class which is of type :ViewComponent.

            are like partial views but have more functionalities.

            -easy description and example :

                http://www.dotnetjalps.com/2015/10/view-component-aspnet-mvc6.html

    Controller
        -In MVC 6, there is one Controller base class for both MVC and Web API controllers
        which is the Microsoft.AspNet.Mvc.Controller class.
    Setting up the MVC folder structures

        To follow the MVC standard pattern and the separation of concern, 

        let’s create the “Models”, “Views” and “Controllers”

    Introducing the project.json file

        The project.json file serves as the new project file (.csproj/.vbproj). 

        This is where we put all the dependencies that our application requires. 

        -it provides intellisense for the available packages while you add or edit dependencies. 

        -All packages that you’ve added from this file will automatically pulls the packages from NuGet. 

        when you remove packages it automatically removes them from your project reference. 
```
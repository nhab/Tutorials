```
: a framework :-for-> building RESTful applications using HTTP services for clients,
    including browsers and mobile devices. 
    - both creating client and server endpoints
:Terms
    #REST
        stands for ‘Representational State Transfer’  
        and it is an architectural pattern for creating an API  
        that based on HTTP and uses HTTP requests, responses, verbs and status codes to communicate. 
        The fact that REST services use HTTP means they can be consumed by almost any ‘online’ device or 
        application (including IoT devices such as toasters, cars, pedometers etc) – no proprietary knowledge of the API is required.
    #HTTP
        is a request and response system;
        a calling client -sends-> a request to an endpoint and the endpoint responds. 
        
        The client and endpoint can be anything but a typical example is
        a browser accessing a web server or an app accessing and API.
        :{
            Resources 
                -REST uses addressable resources to define the structure of the API.
                These are the URLs (or URIs) you use to get to pages on the web,
                X: ‘http://www.microsoft.com/Surface-Pro-3’ 
                    /Products 
                    /Products/81
            Request Verbs 
                These describe what you want to do with the resource.
                :X
                    A browser typically issues a GET verb to instruct the endpoint it wants to get data,
                :X 2
                    POST, PUT , DELETE,..
                See the full list at http://www.w3.org/Protocols/rfc2616/rfc2616-sec9.html

            Request Headers 
                These are additional instructions that are sent with the request. 
                :{  (only some of them are listed here)
                    Accept
                        :the Accept request-header field can be used to specify certain media types which are acceptable for the response.
                        :X 2
                            Accept: text/plain; q=0.5, text/html,
                                    text/x-dvi; q=0.8, text/x-c
                
                    authorisation details.
                    The Authorization field value consists of credentials
                        containing the authentication information of the user agent for
                        the realm of the resource being requested.
                        :x
                            Authorization  = "Authorization" ":" credentials
                    cacheable
                        response is cacheable
                    Connection
                        The Connection general-header field allows the sender to specify options that are desired for that 
                        particular connection and MUST NOT be communicated by proxies over further connections.
                        The Connection header has the following grammar:

                            Connection = "Connection" ":" 1#(connection-token)
                            connection-token  = token

                See the full list at http://www.w3.org/Protocols/rfc2616/rfc2616-sec14.html

            Request Body 
                Data that is sent with the request. 
                For example a POST (creation of a new item) will required some data which is typically sent as the request body 
                in the format of JSON or XML.

            RESPONSE Body  
                This is the main body of the response.
                If (request == to a web server)  =>  a "full HTML page",
                if (request == to an API      )  =>  a "JSON or XML document".

            RESPONSE Status codes 
                These codes are issues with the response and give the client details on the status of the request.
                See the full list at www.w3.org/Protocols/rfc2616/rfc2616-sec10.html
        :X (some typical requests you might expect to see in an ecommerce API:)
            Resource 											Verb 	Expected Outcome 											Response Code
            /Products 											 GET 	A list of all products in the system 							200/OK
            /Products?Colour=red 					 			 GET 	A list of all products in the system where the colour is red 	200/OK
            /Products 					 						 POST 	Creation of a new product 										201/Created
            /Products/81 										 GET 	Product with ID of 81 											200/OK
            /Products/881(a product ID which does not exist) 	 GET 	Some error message 												404/Not	Found
            /Products/81 										 PUT 	An update to the product with an ID of 81 						204/No Content
            /Products/81 										 DELETE Deletion of the product with an ID of 81					 	204/No
            Content/Customers 									 GET 	A list of all customers 										200/OK
    #HttpApplication pipeline flows
        The request is processed by the HttpApplication pipeline and 
        events are fired in the following order:

        BeginRequest -
        The BeginRequest event signals the creation of any given new request.
        This event is always raised and is always the first event to occur during
            the processing of a request.

        AuthenticateRequest - 
            The AuthenticateRequest event signals that the configured authentication 
            mechanism has authenticated the current request.
            Subscribing to the AuthenticateRequest event ensures that 
            the request will be authenticated before processing the attached 
            module or event handle.

        PostAuthenticateRequest -
        The PostAuthenticateRequest event is raised after the AuthenticateRequest event has occurred. All the information available is accessible in the HttpContext’s User property.

        AuthorizeRequest - 
            The AuthorizeRequest event signals that ASP.NET has authorized 
            the current request.
            You can subscribe to the AuthorizeRequest event to perform custom
            authorization.

        PostAuthorizeRequest - 
            Occurs when the user for the current request has been authorized.

        ResolveRequestCache - 
            Occurs when ASP.NET finishes an authorization event to let the caching modules serve requests from the cache, bypassing execution of the event handler and calling any EndRequest handlers.

        PostResolveRequestCache –
            Reaching this event means the request can’t be served from the cache, and thus a HTTP handler is created here. A Page class gets created if an aspx page is requested.

        MapRequestHandler - 
            The MapRequestHandler event is used by the ASP.NET infrastructure to determine the request handler for the current request based on the file-name extension of the requested resource.

        PostMapRequestHandler -
            Occurs when ASP.NET has mapped the current request to the appropriate HTTP handler

        AcquireRequestState - 
            Occurs when ASP.NET acquires the current state (for example, session state) that is associated with the current request. A valid session ID must exist.

        PostAcquireRequestState -
            Occurs when the state information (for example, session state or application state) that is associated with the current request has been obtained.

        PreRequestHandlerExecute - 
            Occurs just before ASP.NET starts executing an event handler

        ExecuteRequestHandler –
            Occurs when handler generates output. This is the only event not exposed by the HTTPApplication class.

        PostRequestHandlerExecute - 
            Occurs when the ASP.NET event handler has finished generating the output

        ReleaseRequestState -
            Occurs after ASP.NET finishes executing all request event handlers. This event signal ASP.NET state modules to save the current request state.

        PostReleaseRequestState - 
            Occurs when ASP.NET has completed executing all request event handlers and the request state data has been persisted.

        UpdateRequestCache - 
            Occurs when ASP.NET finishes executing an event handler in order to let caching modules store responses that will be reused to serve identical requests from the cache.

        PostUpdateRequestCache -
            When thePostUpdateRequestCache is raised, ASP.NET has completed processing code and the content of the cache is finalized.

        LogRequest - 
            Occurs just before ASP.NET performs any logging for the current request. The LogRequest event is raised even if an error occurs. You can provide an event handler for the LogRequest event to provide custom logging for the request.

        PostLogRequest -
            Occurs when request has been logged

        EndRequest - 
            Occurs as the last event in the HTTP pipeline chain of execution when ASP.NET responds to a request. In this event, you can compress or encrypt the response.

        PreSendRequestHeaders –
            Fired after EndRequest if buffering is turned on (by default). Occurs just before ASP.NET sends HTTP headers to the client.

        PreSendRequestContent -
            Occurs just before ASP.NET sends content to the client.
    Controllers
        - Resources(URIs) are mapped directly to> controllers 
            using "routing engine"   
        - Typically, APIs are held within a ‘/api/’ route 
    Actions 
        :are used to map to specific HTTP verbs
        :X
                a GET action returns all of the entities which looks like this:
                public IEnumerable<string> Get()
                {return new string[] { "value1", "value2" };
                }
                
                //another controller
                public string Get(int id)
                {return "value";
                }
    #routing table
        To determine which action to invoke, the framework uses a routing table
    #route template
        Each entry in the routing table contains a route template. 
        The default route template for Web API is "api/{controller}/{id}".
        In this template, "api" is a literal path segment, and {controller} and {id} are placeholder variables
:mechanisms
    - "pipeline model".
        - when a server (hosting a web API) receives a request,
        a controller class  handles HTTP requests, passes through ".nets request pipeline " first. 
        - on ASP.net vNext  you can potentially host your Web API outside of Windows Server. 
        See http://www.asp.net/vnext for detail.
    
        -Serialization and Model Binding
            -json
                :Web API is setup by default to provide responses in either XML or JSON (JSON is default)
            -content negotiation
                as a developer you do not need to do any conversion or parsing –
                you simply return a strongly typed object and Web API will convert it to XML or JSON and 
                return it to the calling client, this is a process called Content Negotiation. 
                :X (get)
                    This is an example of a GET action which returns a strongly typed Product object.
                    public Product GetProduct(int id)
                    {
                        var product = _products.FirstOrDefault(p => p.ID == id);
                        if (product == null)
                        {
                            throw new HttpResponseException(HttpStatusCode.NotFound);
                        }
                        return Request.CreateResponse(HttpStatusCode.OK, product);
                    }
            -Model Validation
                with it, Web API is able to validate and parse incoming response body data
                to a strongly typed object for you to work with in your code 
                :X 
                    public HttpResponseMessage Post(Product product)
                    {
                        if (ModelState.IsValid)
                        {
                        // Do something with the product (not shown).
                        
                        return new HttpResponseMessage(HttpStatusCode.OK);
                        }
                        else
                        {
                        return Request.CreateErrorResponse(HttpStatusCode.BadRequest, ModelState);
                        }
                    }
    -routing mechanism:
        The default route template for Web API is "api/{controller}/{id}"
            /api :
                The reason for using "api" in the route is to avoid collisions with ASP.NET MVC routing.
                That way, you can have "/contacts" go to an MVC controller, and "/api/contacts" go to a Web API controller.
                Of course, if you don`t like this convention, you can change the default route table.

            /{controller} :
                When the Web API framework receives an HTTP request,
                it tries to match the URI against one of the route templates in the routing table. 
                If no route matches, the client receives a 404 error. For example, the following URIs match the default route:
                    /api/contacts
                    /api/contacts/1
                    /api/products/gizmo1
                but not 
                    /contacts/1

                Once a matching route is found, Web API selects the controller and the action:
                    To find the controller,
                        Web API adds "Controller" to the value of the {controller} variable.

            To find the action,
                    Web API looks at the HTTP method for an action whose name "begins" with that "HTTP method name".

                    For example , with a GET request , Web API
                        -> looks for an action that starts with "Get...", such as "GetContact" or "GetAllContacts".

                    This convention applies only to GET, POST, PUT, and DELETE methods.
                    You can enable other HTTP methods by using attributes on your controller.
            Other placeholder variables in the route template, such as {id}, are mapped to action parameters.
:HOWTO
    -A simple web-api project
        1.create an empty web api project
            in vs2013> New Project > visula c# > web >  ASP.NET Web Application > select `Empty` template and tick the webAPI checkbox
        2.Add a Model
            Solution Explorer> right-click Models folder > Add > class... >put this code into it
                namespace ProductsApp.Models
                {
                    public class Product
                    {
                        public int Id { get; set; }
                        public string Name { get; set; }
                        public string Category { get; set; }
                        public decimal Price { get; set; }
                    }
                }
        3.Add a Controller 
            Solution Explorer > right-click Controllers folder > Add > Controller... >
            (In the Add Scaffold dialog)> Web API Controller - Empty > Click Add.
            >put this code into it
                using ProductsApp.Models;
                using System;
                using System.Collections.Generic;
                using System.Linq;
                using System.Net;
                using System.Web.Http;

                namespace ProductsApp.Controllers
                {
                    public class ProductsController : ApiController
                    {
                        Product[] products = new Product[] 
                        { 
                            new Product { Id = 1, Name = "Tomato Soup", Category = "Groceries", Price = 1 }, 
                            new Product { Id = 2, Name = "Yo-yo", Category = "Toys", Price = 3.75M }, 
                            new Product { Id = 3, Name = "Hammer", Category = "Hardware", Price = 16.99M } 
                        };

                        public IEnumerable<Product> GetAllProducts()
                        {
                            return products;
                        }

                        public IHttpActionResult GetProduct(int id)
                        {
                            var product = products.FirstOrDefault((p) => p.Id == id);
                            if (product == null)
                            {
                                return NotFound();
                            }
                            return Ok(product);
                        }
                    }
                } 
        4. You have a working web API!
            Each method on the controller corresponds to one or more URIs:
            Controller Method		URI
            ---------------------------------
            GetAllProducts		/api/products
            GetProduct			/api/products/id
            
            it because of defaulr routing table
            (	
                The Visual Studio project template for Web API creates a default route:
                routes.MapHttpRoute(
                    name: "API Default",
                    routeTemplate: "api/{controller}/{id}",
                    defaults: new { id = RouteParameter.Optional }
                );

                This route is defined in the WebApiConfig.cs file, which is placed in the App_Start directory
            )
```
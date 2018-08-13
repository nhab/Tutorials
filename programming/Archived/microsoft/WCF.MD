```
#WCF (Windows Communication Foundation )
	:
		-is used to develop SERVICES on Windows platform both "web" and  "windows"

		- is a runtime and a set of APIs for creating programs 
			to  "send messages" between "service endpoints"(services and clients).

		-it unifes theses older technologies into one place:
			.ASMX Web Services ,MSMQ ,.NET Remoting , and more.

	:{
		WCF service
		WCF service host
		WCF service client.
	:Concepts
		Message
			a communication unit 
			that comprises of several parts apart from the body.
			Message instances are sent as well as received 
			for all types of communication
			between the client and the service.
		Endpoint
			:are places where messages are sent or received (or both),
				and they define all the information required for the message exchange. 
			-It defines 
				1-the address(A)
				2-and communication mechanism(Binding ) 
				of where a message is to be sent or received. 
				3-as well as Contracts
					:the functionality the endpoint exposes to the clinet

			:is  a RESOURCE or an ENTITY IN the NETWORK to which messages can be sent.				

			Endpoints are responsible for the COMMUNICATION between a client and the SERVICE.
			-Elements > endpoints which referred to as ABC`s of WCF, are  {:

					- Addresses               ?: 

						to locate the service

						X:

							scheme://domain_name:port/path

							http://localhost:8080/services/MyFirstService

					- Bindings                 : 

						Specify the communication protocol used  .

						predefined bindings (:

							basicHttpBinding 

							wsHttpBinding

							wsDualHttpBinding

							wsFederationHttpBinding

							netTcpBinding

							netNamedPipeBinding

							netMsmqBinding

							msmqIntegrationBinding

							netPeerTcpBinding

					- Contracts               : 

						to specify the functionalities to be performed .

						Agreements between the client and services. 3 basic contracts are (:

							Service Contracts: Defines the methods of the service.

							Data Contract: Defines the data types used by the service methods.

							Message Contract: Ability to control the message headers during the creation of the message.

							

					- Endpoint behaviors : to specify the runtime behavior of the service endpoint.

			
			X:
				Endpoints will be mentioned in the web.config file on the created service.
				<system.serviceModel>
				<services>
					<service name="MathService"
						behaviorConfiguration="MathServiceBehavior">
					<endpoint
						address="http://localhost:8090/MyService/MathService.svc" contract="IMathService"
						binding="wsHttpBinding"/> 
					</service>
					</services>
					<behaviors>
					<serviceBehaviors>
						<behavior name="MathServiceBehavior">
						<serviceMetadata httpGetEnabled="True"/>
						<serviceDebug includeExceptionDetailInFaults="true" />
						</behavior>
					</serviceBehaviors>
					</behaviors>
				</system.serviceModel> 
		Hosting
			:from the viewpoint of WCF refers to the WCF service hosting
			which can be done through many available options like self-hosting, IIS hosting, and WAS hosting.
			
		Metadata
			: it facilitates easy interaction between a client application and a WCF service. 
			-it is generated automatically when enabled by inspection of service and its endpoints.
		
		WCF Client
			A client application that gets created for exposing the service operations in the form of methods.
			This can be hosted by any application, even the one that does service hosting.
		
		Channel 
			is a medium through which a client communicates with a service.
			Different types of channels get stacked and are known as Channel Stacks.
		WCF runtime 
			is the set of object responsible for sending and receiving message.
			For example formatting the message, applying security and transmitting 
			and receiving message using various protocol.	
	{:Architecture
		- Contracts layer
			:It is an 'AGREEMENT BETWEEN 2 MACHINES' 
				defining the terms and conditions for the messages to be exchanged

			Types :
				- Data Contract :
					Agreement between a service and a client on the data that has to be exchanged.
					Also defines what data structures and parameters to be used by services 
					in order to interact with the client

				- Message Contract :

					Provides control over the SOAP messages that are produced and consumed by WCF.

					It also provides direct access to message header & body to alter the SOAP message 



				- Service Contract:

					Defines the kind of operations supported by the service.

					It also exposes certain information to the client such as:

						Data Types in the message.


						Locations of the operations, or where the methods are defined

						Protocol information and serialization format

						Message exchange patterns(whether the behavior of the message is either one-way, duplex or request/reply type)



				- Policy and Binding: 

					Specify important information such as security, protocol.



		- Service Runtime layer ("BEHAVIORS" of the service )
			:specifies and manages different "BEHAVIORS" of the service 
				that occur during the service operation.
			-Service Behaviors "are  objects"
				that modify and control the run time characteristics of WCF. 
			{:list of Service Behaviors
				- Throttling Behavior  : Determines the number of processed messages, which varies according to the demand of the service.
				- Error Behavior          : Specifies what kind of action to be taken when any of the messages give error during runtime.
				- Metadata Behavior     : Specifies whether metadata is available across the network.
				- Instance Behavior     : Specifies the number of service instances that are available to process a message.
				- Message Inspection   : Inspects a message totally or partly during runtime.
				- Transaction Behavior: Enables the transaction operation, which rollbacks the transaction if any process fails during runtime.
				- Dispatch Behavior     : Determines the handling and processing of a message.
				- Concurrency Behavior: Specifies whether the messages are processed sequentially or concurrently.
				- Parameter Filtering  : Filters the message headers & executes preset actions based on the filter of the message headers.

		- Messaging layer 
			:is responsible for the pattern of exchanges and its format.

			It`s composed of the following components and channels:

				WS-Security Channel: Enables message security by implementing the WS-Security specifications. 

					Extensive coverage on WS Security can be found out here: http://msdn.microsoft.com/en-us/library/ms977327.aspx

				WS Reliable Messaging Channel: Guarantees delivery of messages.

				Encoders: Provides the number of encoders for messages, such as Binary, XML, Text, MTOM.

				HTTP Channel: States that HTTP is used to deliver messages.

				TCP Channel: States that TCP is used to deliver messages.

				Transaction Flow Channel: Governs transacted message patterns.

				Named Pipe Channel: Enables Inter Process Communication.

				MSMQ Channel: Enables services to operate with MSMQ.

	

		- Activation and hosting layer 
			This layer provides a number of options in which a service can be ACTIVATED and HOSTED.
			Hosting can be of 2 types: 1-self hosting, 2-hosting on external agents, such as IIS.
			Various options provided by this layer are as follows:

				Windows Activation Services  : Enables WCF applications to automatically activate, when deployed on a system running WAS.

				.EXE                                     : WCF services can also be run as executable files.

				Windows Services                   : WCF services can also be run as Windows services.

				COM+					     : WCF services can also be run as COM+ app.
	Features  :
		Endpoint Support
		Improved Transport Layer:

			Unlike .ASMX web services, WCF services use a numerous protocols for communication between a client and the service.

			It uses HTTP, TCP, HTTPS, Named pipes. Hence, improved transport facility.

			

		Queuing Support:

			WCF supports queuing, which allows messages to be stored in a queue and then sent in a timely manner, thus giving a consistent state of communication.

		Improved Transactional Support:
			WCF incorporates improved transactional support,
			which says if any process fails during service runtime
			, the transaction doesn`t commit, it rollbacks.

		Improved Security:

			Authentication plays a big role in WCF, also WCF ensures that during transit, order of the messages ain`t altered

		Hosting support on various environments:

			WCF allows hosting of services in a number of environments, such as Windows NT Services, Windows Forms, Console Apps, IIS,

			Windows Activation Services(WAS). IIS provides added advantages such as automatic start and stopping of the service.

		AJAX Integration and JSON Support:

			WCF supports ASP.NET AJAX and JSON data format, which allows WCF services to expose operations to AJAX clients.

			JSON is a data format used to carry data exchange between AJAX enabled services and their clients.
	?:(how to)
		1-first create  wcf service by 
			Visual Studio 2012>new project> in Visual C# tab, select WCF option.
		2-Hosting wcf service
			IIS Hosting 
				?:
					1-Visual Studio 2012 and click File -> New -> Web site. Select “WCF Service” and Location as http. 
					This will host the service in IIS. Click OK.
					2,3-write code behind
					4-Service file (.svc) contains the name of the service and the code behind the file name.
					5-Server-side configurations are mentioned in the config file. 
					Here, there is a mention of only one end-point which is configured to 'wsHttpBinding';
					we can also have multiple endpoints with different bindings. 
					Since we are going to host in IIS, we have to use only http binding.
					6-You need to mention the service file name, along with the Address mentioned in the config file.
					The screenshot of IIS is given here.
					Click Start -> run -> inetmgr which will open the following window.
					7- Run the application .
			Self Hosting
				1. Create a console application
				2. Right click References> in the Solution Explorer > click Add References> add 'System.ServiceModel' reference to the project.
				3. Create an ISimpleCalculator interface, Add ServiceContract and OperationContract attribute to the class and function 
				4,5.The code behind
				6.Create a new console application and name it as 'MyCalculatorWCFServiceHost'.
				7. Add the reference of system.servicemodel and the project MyCalculatorWCFService.
		3-Consuming WCF service  Hosted in IIS 5/6 in client applications.
			1.Before creating the client application, we need to create a proxy for the service. 
			This proxy is used by the client application to interact with the service. 
			To create a proxy, run Visual Studio 2008 command prompt.
			Using service utility, we can create the proxy class ,and its configuration information.
			svcutil http//localhost/IISHostedService/Service.svc 
			
			After executing this command, we will get two files generated in the default location.
				MyService.cs – Proxy class for the WCF service
				output.config – Configuration information about the service 
			2. Now, we will start creating the Console application using Visual Studio 2008 (Client application).
			3. Add the reference 'System.ServiceModel'; this is the core dll for WCF.
			4. Create a Proxy class.
									
		Creating simple WCF Service 
			1. VS2008 > File>New>Project>Blank solution

			Add>New Project>WCF service library		

			2.Add a console app to expose the serice

				2.1.Add system.ServiceModel to its refrence

				2.2.copy the app.config of the service library project to the console app

				2.3.change the target framework of the console project to ".net framework 4.0"

				2.4.Add System.ServiceModel.Web reference to console project 

			3.Add this code to the main function of the console application

				Console.WriteLine("Starting Service Console Host...");

				// instantiate

				ServiceHost baseServiceHost = new ServiceHost(typeof(WcfServiceLibrary1.Service1));

				baseServiceHost.Open();

				string baseAddress = baseServiceHost.BaseAddresses[0].AbsoluteUri;

				Console.WriteLine("The service is ready at {0} "", baseAddress);

				Console.WriteLine("Press <Enter> to stop the service.");



				// ServiceHost crossDomainServiceHost = new ServiceHost(typeof(CrossDomainService));

				//crossDomainServiceHost.Open();

				Console.ReadLine();

	sync,async ->completed
	user state 		
```

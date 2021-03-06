
**Step 1: Review Inputs**

 [Add Step 1: Review Inputs](https://github.com/SOFE3650F18/project-group-26/blob/master/ADD/ADD%20Step%201:%20%20Review%20Inputs.md)

**Step 2: Establish Iteration Goal by Selecting Drivers**

  The main iteration goal of this section is CRN-1, to create and define the overall system structure. This iteration is driven by general architecture of the system, but all drivers in step 1 are being considered as influence within this iteration as it will create the underlying structure of the system.

**Step 3: Choose One or More Elements of the System to Refine**

![alt Context Diagram](https://github.com/SOFE3650F18/project-group-26/blob/master/Iteration%201/ContextDiagram.png)   

*Figure 1.1: Context Diagram*

**Step 4: Choose One or More Design Concepts That Satisfy the Selected Drivers**

| Design Decisions and Location                                                                       	| Rationale                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                           	|
|-----------------------------------------------------------------------------------------------------	|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------	|
| Logically Structure the client part of the system using the  Web Application reference architecture 	| The Web application reference architecture supports the development of applications which are accessed through the internet with the use of a clients browser. These applications support rich user interfaces that are needed to display and receive information from user to update and display system information in a user friendly manner. These capabilities are also helpful in implementing drivers in the system as web applications support technologies used for drivers outlined above. The implementation of a User system with the use of sessions(UC-1).  This architecture will increase accessibility as Web application architecture can be accessed from multiple platforms including Desktop, mobile, etc (QA-1, QA-5) as well as differing OS(Windows, MacOS, Linux)(CON-6). <br><br>__Discarded Alternatives__ <br>**Rich Client Application:** Although this architecture allows for rich user interfaces and updating functionality, this was discarded due to its need of user installation as well as being less accessible than chosen architecture <br>**Mobile Applications:** This architecture was discarded because the alternative proves more efficient in communicating with the user as well as the access to the alternative solution through the mobile’s web browser 	|
| Structure the server part of the system using the Service Application architecture                  	| Service applications do not provide user interfaces but provides services to other components of the system through application protocols securely (CON-5, QA-4).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   	|
| Structure the application using a  three-tier deployment pattern                                    	| Since our system is deployed within a Web application and is accessed through a web browser which consists of front-end, back-end, and database(CON-2). We can see that a three tier architecture is appropriate as we are separating each component within its own tier. The layers help to differentiate components into their own specific roles.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                	|
| Build the client side and user interface of the client’s application using the AngularJS framework  	| AngularJS is a structural framework for dynamic web applications. This will allow the design of a rich user interface (CON-3) and allows the development team to utilize known technologies(CRN-3).                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 	|
| Deploy the application using Server sided technology                                                	| Access to the application is obtained via web browser.  This technology updates client code on when update versions are available on client reload. Allows for deployment and updating                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              	|
| MVC Architecture                                                                                    	| Model View Controller (MVC) architecture pattern is used to implement user interfaces. Using this architecture and the three tier deployment pattern, to separate the application logic of our different components and increase modularity and collaborations between the components                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                               	|

**Step 5: Instantiate Architectural Elements, Allocated Responsibilities and Define Interfaces**

| Design Decision and Location                                               	| Rationale                                                                                                                                     	|
|----------------------------------------------------------------------------	|-----------------------------------------------------------------------------------------------------------------------------------------------	|
| Create a server module dedicated to accessing the database                 	| The service agent component is abstracted to access server information as well as information stored within the database(UC-4, CON-5).        	|
| Create a client module dedicated to communicating with server              	| The client module should communicate with the server to retrieve information as well as update, and store information                         	|
| Create a client security module dedicated to processing client information 	| The security module on the client side should display the user information in relation to the role of the user (UC-1, UC-3).                  	|
| Create a server security module to process server information              	| The security module on the server side should process requests and serve the appropriate response based on the users input(QA-4, CON-5).      	|
| Create UI modules to interface with the user                               	| The UI modules will provide the user with rich user interfaces, to allow the user to access the systems content in an friendly manner(CON-3). 	|

**Step 6: Sketch Views and Record Design Decisions**

![alt Three layered architecture](https://github.com/SOFE3650F18/project-group-26/blob/master/Iteration%201/three-layered%20model.png)
<br>
*Figure 1.2: The three layered architecture visually showing the relationship between the client side and the server side*


| Element                  | Responsibility |                                                                                           
|--------------------|----------------------|
| Presentation CS          | This layer controls the flow and the user input (User interface)  |                               
| Business logic CS        | This layer performs operations based on business operations   |                                              | Cross-cutting CS         | "This layer access different modules across the CS in order to provide security logging and I/O files" |   
| UI module                | This module displays user's inputs |                                                             
| UI Process modules       | This module controls the flow of the user's input |                    
| Business modules CS      | This module controls the user input with relation to the Business |            
| Business entities CS     | This module is the foundation of the client side contains all interfaces required for the user |         
| Communication modules CS | This module provides services and connections between the client side and the server side|          
| Services SS              | This layer interacts with the client side and opens up the server side for the client side to use|    
| Business logic SS        | This layer performs logical operation based on the client side business layer|                            
| Data SS                  | This layer is responsible for containing data and for returning data we asked for|                        
| Cross- cutting SS        | This layer access different modules across the SS in order to provide security logging and I/O files |
| Service interface SS     | This module takes input from the client side and organizes it in the server side| 
| Business modules SS      | This module implements operations |    
| Business entities SS     | This module is made up of entities |           
| DB access module         | This module is responsible for the storing of data and its relational information as well as protecting valuable data |

| Element            | Responsibility                                                                        |
|--------------------|---------------------------------------------------------------------------------------|
| User Workstation   | The application of system where the user interacts with the system. Hosts the clients |
| Application server | The server that hosts the application                                                 |
| Database server    | The server that hosts the databases                                                   |
| University server  | The server that hosts the university's data                                           |

| Relationship                                     | Description                                 |
|--------------------------------------------------|---------------------------------------------|
| Between application server and database server   | Communication between each other using JDBC |
| Between application server and university server | Communication between each other using JSON |

![alt Initial deployment diagram](https://github.com/SOFE3650F18/project-group-26/blob/master/Iteration%201/Initial%20Deployment%20Diagram%20for%20CMS.png)
*Figure 1.3: The initial deployment diagram*

**Step 7: Perform Analysis of Current Design and Review Iteration**

| Not Addressed | Partially Addressed | Completely Addressed | Design Decisions Made during the Iteration
|---------------|---------------------|----------------------|---------------------------------|
|               | UC-1                |                      | Implementation of User system and its functionality as well as its reference for other attributes     |
|               | UC-2                |                      | "Information display will be implemented through views in the users web client with the use of web technologies such as HTML CSS and JavaScript(AngularJS)" |
| UC-3          |                     |                      | N/A            |
|               | UC-4                |                      | Component is explained as being able to access server information stored in a database  |
| UC-5          |                     |                      | N/A  |
| UC-11         |                     |                      | N/A  |
|               | QA-1                |                      | Mentioned the availability of the system and its portability|
| QA-2          |                     |                      | N/A   |
| QA-3          |                     |                      | N/A   |   
|               | QA-4                |                      | Identified the uses of security through its protocol and its uses in other components  |
|               | QA-5                |                      | Identified the wide variety of usage the system has |
| CON-1         |                     |                      | N/A |
|               | CON-2               |                      | Data storage and retrieval will be implemented through the use of Database Management System (DBMS)  |
|               |                     | CON-3                | Mentioned AngularJS as being a dynamic framework for web application |
| CON-4         |                     |                      | N/A |
|               | CON-5               |                      | Described the compatibility between databases and the relationship between them   |
|               |                     | CON-6                | The system will be implemented through a Web application which will allow availability on multiple platforms through their native Web browser. |
| CON-7         |                     |                      | N/A  |
| CON-8         |                     |                      | N/A  |
|               | CRN-1               |                      | Technologies considered to be implemented reflect the development teams knowledge and benefit the underlying structure of the system    |
| CRN-2         |                     |                      | N/A   |
|               | CRN-3               |                      | "Based on the references above with a dynamic framework allowing users to utilize technology" |

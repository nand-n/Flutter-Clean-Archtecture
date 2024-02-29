# Clean Archtecture on  Flutter 

## The three lay of archtecture
1. Data 
    - The outer most layer of the applicatoin 
    - It is responsibele for data retrival in the form of api call or local db 
    - It contains 3 layers 
        1. Repository
            - It includes actual implementation of repositories in the domain layer 
            - It is responsible for the coordination of data form d/t data sourcess 
        2. Data Sources 
            - It consits of remote(perform http requests) and local(cache or percist data in the) data sources 

2. Domain 
    - Domain Layer is the inner most layer and have no any dependency on another layers
    - It contains 
        1. Entities 
            - Entitiels must be our data types or classes that are gone be used in d/t parts of our software 
        2. Repository Interfaces
            - Abstract classes or contracts 
            - Defines the properties and methods that our project will need in specific features
        3. Use Cases
            - Includes the application's specific bussiness rules
             - Each event is interaction of a user with the system whci is called usecase 
             - Use case is a bridge b/m layers 
             - It is a single call to bussiness logic 
    - The domain layer is only concerned with bussiness layer of the application not with the implementation details 

3. Presentation (Feature layer)
    - prensets the app content and trigger the events that modify the app state 
    - have 3 parts 
        1. Pages 
        2. State managment 
        3. Widgets 




# Core concepts of clean Archtecture

## Domain - Entitities
    - Entities represents the core data models of the application.They define the structure and properties of the data.
    - Create an entity to be passed arround in the application.
    - It is the blueprint that defines what structure the data will be or what properties our user's data will carry when it comes from the server right so what does the server gives back to us 
## Domain - Repositories 
    - Repositories define the contract b/n the data layer and the domain layer.
    - Create a repository to specify the methods of data operations. 
    - Repositories handle data operations and follow the DIP Prencipals 

        -> DIP: Dependency Inversion Prenciple : states that high level module should not depend on low level modules; both should depend on abstractions.Abstractions should not depend on details. Details should depend on abstractions
## Domain - Usecases 
    - Usecases represents the bussiness logic of the application .
    - They depend on the repository and call its methods to perform data operations.
    - Usecases Enforce the SRP preenciple and focus on specific functionalities. 

        -> SRP prenciple : Single Responsiblity Principle -> Focus on Specific Functionality 

## Data -  Models 
    
    - Models are entities with extra features.
    - Models are subclasses of the entities and hanldes data serialization , they transform data b/n entities and data sources.
    - Models help to achieve the OCP Precipal.

        -> OCP prencipal : Open Close Prencipal is on of the SOLID prencipals of oop design , which encourages the code to be open for extention but closed for modification. 

## Data - Repository 

    - Repositories have the implementation of the repository contract defined in the domain layer. 
    - They interact with data sources to retrive data.
    - Repository implementations allow switching data sources without modifying the domain layer. 

## Data - Sources  

    - Data Sources provide the actual data from external sources (eg api , databases , localstorage .... etc) 
    - They implement the repository interfaces defined in the domain layer.
    - Data Sources promote modularity and adher the DIP Prenciple 


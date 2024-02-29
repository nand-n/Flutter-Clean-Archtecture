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





## Entitities are bussiness objects of an application or a system 

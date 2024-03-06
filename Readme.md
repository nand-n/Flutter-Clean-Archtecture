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

## Presentation - Bloc/Cubit 

    - Bloc/Cubit manages the state of the UI and bussiness logic.
    - It depends on usecases to execute bussiness operations.
    - Bloc/Cubit emits states to the ui , decoupling it from bussiness logic.

## Presentation - View 

    - Views are responsible for displaying UI components and listeneing to bloc/cubit states.
    - They reacts to state changes and update the ui accordingly 
    - Views promote the SRP Prenciple by separating presentation logic from the bussiness logic 

## TDD - Test Driven Develpment 

    - TDD involves writing tests before implementating the actual code . Each layer and and module can be tested independently. 
    TDD helps in achieving better code quality and fewer bugs. 

## Dependency Injection 

    - DI is used to provide dependencies to different layers of the app. 
    - It helps in managing the dependencies and allows easy swapping of implementations. For example Getit can be used for dependency injection. 






# Example Clean Archtecture  Login 

## user Authentication 
    - When the user clicks "Login " , it triggers the nest step 
## Step 2 - Bloc Bussiness Logic 
    - The Bloc(Bussiness logic component) handles the login process when the user logsin , the bloc continues to the nest step(Use case bussiness logic ).

## Step 3 - Usecases  Bussiness logic 
    - Usecases will hand over the login process to the repositories.
## Step 4 - Repositories  Data Operations 
    - Repositories define the contract b/n data adn domain layers .
    - They will make a call to the data sources. 
    - The Repository will be the implementaion of our contract or interface 
## Step 5 - Data Sources 
    - Data sources provice actual data form external sources. 
    - They interact with repositories and continue to the next step.
    - Data sources sends that response back to the repository 
## step 6 Use Cases - bussiness logic 
    - Usecases handles the server response
## Step 7 - Bloc Bussiness logic 
    - Bloc handles the final responses from the usecase 
## Step 8 - View - User Result
    - The vies recives the fianl result from the Bloc . 
    - The login process is complete 

## Using call for callable functions in dart 
    
     void main() {
        final callable = Callable()
        callable("nahi)
     } 

     class Callabele {
        void call(String message) {
            pring("Hello worled $message);
        }
     }

     - This means we can use callable funciton with out calling the function call only by using call funciton.

# Testing 
 
  ## Unit testing 
  - For unit testing testing we have to ask our selfs 
    1. askdjfwhat does the class depends on 
    2. how can we create a fake version of the dependencies 
    3. How do we controll what our dependencies do

    there are d/t type of testing libraries for dart 
    - Moctail 
    - Mockito 


# MVVM
    MVVM Pattern helps to cleanly separate application's bussiness and presentation logic fron the users interface . 

    Mantaining A clean separation b/n application logic and the ui helps address numerous development issues and makes an application easieer to test , mantain and evelve . 
    
    it can also significantly improve core re uses opportunity and allows developers and ui designers to collaborate more easily when developing their respective parts of an app.


# Bloc Pattern 
## Stream
    - Transport asyncrounse data 
    - Streams are usefull 

## Cubit vs Bloc

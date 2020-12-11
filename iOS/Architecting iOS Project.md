# Architecting iOS Project

Massimo Oliviero

slide http://www.slideshare.net/MassimoOliviero


## 大綱 Agenda
- Project, how to design Xcode project 
- Application, how to design an iOS app
- Resources, links, books and videos


## 範例程式碼 Source code

Kimera - A simple iOS application for educational purpose

https://github.com/maxoly/Kimera


## Project
- 慣例，如何命名檔案和資料夾
- 結構，怎麼為專案打好地基
- 資料夾，如何組織檔案和資料夾

### Naming Conventions 命名慣例 
- 第一步為所有類型的檔案建立特定的命名規則
  - file names, class names, project names, images, etc.
- 使用大駝峰命名法 files, folders and class
  - 首字大寫 i.e. Controllers, MyClass, BestAppEver, etc.
- 使用小駝峰命名法 methods, properties & variables 
  - 首字小寫 i.e setFirstName:, userPassword, etc.
- 避免使用 首字母縮略字（acronyms）和縮寫（abbreviations）
  - “usrPswdLbl” 是什麼噁心東西？？

### Coding Conventions 寫作慣例
- 請使用 `K&R`  或  `Allman` 縮排原則
  - http://en.wikipedia.org/wiki/Indent_style
- 也請參考蘋果官方建議的 Coding Guidelines for Cocoa 
  - http://developer.apple.com/library/mac/#documentation/Cocoa/Conceptual/CodingGuidelines/CodingGuidelines.html
- 最重要的是選擇一個文筆風格，然後盡量遵守規則
  - 這件事的目的是為了要讓你的專案有一致性的表達方式

### Structure
- 為專案設定一個好的名字與前綴習慣（prefix）
  - 僅以英數（alphanumeric）的方式為專案建立簡單的前綴
- 設定嚴格的條件來增進程式品質
  - 打開 Static Analyzer 或是把 Warnings 是為 Errors
  
### Build Automation
- It’s the act of automating a wide variety of tasks 
  - you can use build tools like Ant, Maven, Make , CMake or Rake
- At least you must automate Compiling and Deploying 
  - compiling and deploying are the most common tasks for developer
- You can also automate Testing and Docs generation
  -  they are useful to use in combination with a Continuous Integration



## Folders 使用資料夾分類

把所有東西都放在正確的位子，讓他們看起來 makes sense

- 讓每個 view controller 都有自己的資料夾

- 用資料的種類來做資料夾命名，像 images, fonts, sounds, videos, strings, plist, samples

### （Massimo Oliviero）的資料夾組織

| 資料夾名稱 | 用途描述 |
|---|---|
| Application | Specific app related stuff like `AppDelegate`, `main.m`, `.pch` etc |
| Controllers | view (.xib) and view controller stuff put together (obviously) |
| Library | Specific application classes like helpers, base classes, services, etc |
| Models | application domain models and entities, Core Data model too |
| Resources | assets like images, fonts, sounds, videos, etc. |
| Vendors | 第三方函式庫或 frameworks |



## Application
- **Design**, 老生常談的設計原則與設計模式
- **Layers**, 如何組織應用程式的類別
- **Compositions**, 一群可以被重複使用的元件 
- **Best Practices**, 有用的技術清單可以參考

### Design
- Typically an application is divided into **layers**
  - A layer is a black box with a contract that de!ne an input and output
- To increase the **cohesion** and **decoupling** of the software 
  - The layers, if well designed, help to decouple and increase the cohesion
- **Cohesion** indicates strongly related software module
  - it would be a subroutine, class or library with common responsibilities 
- **Coupling** measure the level of dependency
  - between two software module, such as classes, functions or library

### Design Principles, SOLID

### From Principles to Patterns
- Design Pattern is a general reusable solution 
  - to a commonly occurring problem within a given context
- It’s a description or template for how to solve a problem 
  - It’s not a !nished design that can be transformed into source code
- There are many types of design patterns
  - Architectural, Algorithm strategy, Computational, Implementation strategy, Structural, etc.






## Layers

- Layer represents a **logical section** of the system, also enforce reusability and testability

- A typical client/server app have at least 3 layers, Presentation, Business, Data Access.

### Presentation Layer

- It have 2 components: the UI and the presentation logic 
  - in Cocoa the UI is the View and the presentation logic is the Controller

- Cocoa adopt Model View Controller Design Pattern 
  - the Presentation Layer is already in iOS SDK out-of-the-box

- Advanced Appearance Customization with Theme 
  - user Appearance Proxy and Theme technique to customize UI.

### Business Layer

- It holds the specific app Business Logic and Behaviors
  - It is concerned with the retrieval, processing, transformation, and management of application data; application of business rules and policies

- The Domain Model is a conceptual model of business
  - It describes the various entities, their attributes, roles, and relationships, plus the constraints that govern the problem domain

- Business Layer gets data through a Service Layer
  - Service Layer de!nes an application's boundary with a layer of services that establishes a set of available operations and coordinates the application's response in each operation

### Domain Model Layer

- Domain Model, An object model of the domain that incorporates both behavior and data

- You can use simple Objective-C objects that inheriting from NSObject

- Or use Core Data objects extend the class NSMangedObject

### Service Layer

- Service Layer uses Data Access Layer to access data 
  - Service Layer uses DAL to performs the task of retrieving and storing data both from server via network and from database

- Service Layers is a design pattern
  - The benefits a Service Layer provides is that it de!nes a common set of application operations available to different clients and coordinates the response in each operation.

- Service Layer is used by ViewController
  - No more a ton of line of codes in your ViewController, instead few lines of simple Service Layer calls

### Data Access Layer

- It’s a layer which provides simplified access to data 

- It may uses a Persistence Layer or Network Layer 

- Both exposes a simplify contract to access data

### Persistence Layer

- The persistence layer is responsible for manipulating the database, and it is used by the service layer

### Network Layer

- is responsible of all networking calls, like `AFNetworking`

- AFNetworking is built on top of NSURLConnection, NSOperation, and other familiar Foundation technologies



## Composition 寫作

- It’s a way to combine objects into more complex ones
  - Compositions are a critical building block of many basic data structures, including the tagged union, the linked list, and the binary tree, as well as the object used in object-oriented programming

- In a real-world iOS/OS App there are many custom views 
  - For example, all views that must be inserted in a scroll view, or all those portions of the view that occur multiple times in different view and only with different content.



## Best Practices

- API Design
  - Pay attention to the design of your API. Learn your target platform's conventions before coding. Define the rules that are in accordance with the convention of language

- Block and Delegation
  - When should I use blocks instead of delegation for callbacks? Pay attention to this topic and alway look at Apple docs to see how they done

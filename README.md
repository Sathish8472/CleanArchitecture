# CleanArchitecture

Welcome to the CleanArchitecture repository, an ASP.NET Core project showcasing a clean architecture approach. This repository is structured with multiple class libraries and a web API project. Follow the guide below to understand the organization of the solution.

Project Structure
1. Domain

Responsibilities:
Represents the core business logic and entities of the application.
Defines business rules, validations, and core functionality.
Contains interfaces for factories and enumerations.
Encapsulates value objects and custom exceptions.
What It Should Have:
Entities representing core business objects.
Core business rules and validations.
Factory interfaces and enumerations.
Value objects and custom exceptions.
What It Should Not Have:
No dependencies on other layers.
No infrastructure-specific code.
No application or presentation concerns.


No dependency
Contains:
Entities
Core business rules
Factory interfaces
Enumerations
Value objects
Custom exceptions


2. Application

Responsibilities:
Orchestrates and implements use cases based on business requirements.
Utilizes services and the Mediator pattern for handling requests and coordinating actions.
Dependencies:
Depends on the Domain layer.
No direct dependency on infrastructure or presentation layers.
What It Should Have:
Implementation of use cases.
Services and Mediator for handling requests.
What It Should Not Have:
No direct dependencies on infrastructure or presentation layers.
No detailed implementation of external libraries or frameworks.

Dependency: Domain
Implements:
Use cases
Services/Mediator


3. Infrastructure

Responsibilities:
Provides implementations for external resources and services.
Contains database access, file systems, external APIs, etc.
Responsible for data access and persistence.
What It Should Have:
Implementation of external services and resources.
Data access and persistence logic.
What It Should Not Have:
No direct dependencies on higher-level layers (e.g., Domain or Application).
No business rules or specific use case implementations.


No external libraries implemented


4. Presentation
Responsibilities:
Handles user interface and interaction.
Translates user inputs into application actions.
Displays information and responds to user commands.
What It Should Have:
User interface components.
Interaction logic translating user inputs to application actions.
What It Should Not Have:
No business logic.
No direct dependencies on lower-level layers (e.g., Application or Infrastructure).


(No specific details provided)

5. WebApi

Responsibilities:
Exposes application functionality through APIs.
Handles HTTP requests and manages the flow of data.
Dependencies:
Depends on Application, Infrastructure, and Presentation layers.
What It Should Have:
Integration with external libraries (e.g., Serilog for logging).
Dependency injection setup using ServiceCollection.
What It Should Not Have:
No detailed business logic.
No direct dependencies on lower-level layers (e.g., Domain).

Dependencies: Application, Infrastructure, and Presentation
Implements:
Integration of Serilog libraries
Implementation Details
Serilog Libraries: Serilog libraries are implemented throughout the project for logging purposes.

Dependency Injection:

Dependency injection using ServiceCollection is added to all the libraries.
Registrations are performed in the Program.cs file of the WebApi project.
Getting Started
Clone this repository to your local machine.

bash
Copy code
git clone https://github.com/yourusername/CleanArchitecture.git
Open the solution in your preferred IDE.

Build and run the solution.

Contributing
Feel free to contribute to the project by submitting issues or pull requests. Your feedback and enhancements are highly appreciated.

License
This project is licensed under the MIT License. Feel free to use, modify, and distribute the code for your own projects.

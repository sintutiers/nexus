---
unlisted: true
uid: 4um2r409vhplswwy95ul8
title: TDD Examples to Kinda Base it on
modified: Thursday, October 22nd 2026, 6:38 pm
created: Thursday, October 8th 2026, 2:31 pm
author:
  - "[Dean](https://deanlemans.github.io/)"
  - Mink
---

# TDD Examples to Kinda Base it on

> [!NOTE]- TDD Example Game to kinda base it on
> Een TDD is een document waarin je de technische aspecten van je project beschrijft. 
> Het is een belangrijk onderdeel van het ontwikkelproces, omdat het helpt om de technische details van je project te plannen en te communiceren met anderen.
>
> Het FDD beschrijft wat je gaat bouwen, terwijl het TDD beschrijft hoe je het gaat bouwen.
>
> Onderdelen van een TDD kunnen zijn:
> * System Architecture: 
>   * In welke componenten kun je je applicatie opdelen? 
>   * Hoe communiceren die met elkaar?
> * Technical Stack: 
>   * Een lijst van de technologieën en tools die je gaat gebruiken (denk aan frontend, backend, database, etc.) en de versies daarvan.
> * Deployment: 
>   * Hoe ga je je applicatie deployen (online zetten, domeinnaam, ...)?
> * Technical Specifications: 
>   * Uitgewerkte technische specificaties zoals API-endpoints, databasediagram, etc.
> * Backlog: 
>   * Lijst van taken die nog moeten worden uitgevoerd, inclusief technische taken die nodig zijn om de functionaliteit te implementeren.
> * User Acceptance Test (UAT): 
>   * Een testplan om te controleren of de app voldoet aan alle functionele, ontwerp- en codekwaliteitseisen vanuit het perspectief van de eindgebruiker.
>
> ## System Architecture
> Game can be devided into these main components that will need to be programmed:
> * Factory components
>   * Beer Filter
>   * Water Pump
>   * Beer mill
>   * Beer Storage
>   * Retail Center
> * Factory component upgrades
> * Weather
>   * Heavy Rain
>   * Drought
>   * Neutral
> * Water Pollution
> * Camera
>   * Camera movement
>   * Factory component selection
>   * UI displaying game information
>
> The game will be stored the server hosting the website, which the client will then download in order to view and play the game.
>
> ## Technical Stack
> This will be a 3D Unity game, built in the 6000.3.2f1 version of the editor. We will be using C# for our script and writing them in Visual Studio.
>
> ## Deployment
> The game will be deployed in a Web build integrated into a website that our web developer will be developing for his assignment. Exact URL is not yet clear.
>
> ## Technical Specifications
> The game will be making use of Unity's API, but not much beyond that.
>
> ## Backlog
> We have a Project board in the project's Github repo.
> <https://github.com/orgs/Sint-Lucas/projects/696/views/1>
>
>
> ### User Acceptance Test (UAT)
> Controleer of de app voldoet aan alle functionele, ontwerp- en codekwaliteitseisen vanuit het perspectief van de eindgebruiker.
>
> - [ ] The game includes all of the factory components listed above in a fully functional form
> - [ ] The game has an upgrade system
> - [ ] The game has a moveable camera
> - [ ] The game has a weather system that impacts gameplay
> - [ ] The game has a pollution mechanic
> - [ ] The game has an environment score displayed to the player in UI
> - [ ] The game has a message about the effects that pumping too much water has on the environment
>
> ### Test Cases
>
> | Test Case ID | Description                                                                                      | Steps to Test                                                                                                                                             | Expected Result                                                          | Pass/Fail |
> |--------------|--------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------|-----------|
> |              |                                                                                                  |                                                                                                                                                           |                                                                          |           |
> |              |                                                                                                  |                                                                                                                                                           |                                                                          |           |
> This will be filled in later, upon testing.

> [!NOTE]- TDD Example Web to kinda base it on
> Een TDD is een document waarin je de technische aspecten van je project beschrijft. 
> Het is een belangrijk onderdeel van het ontwikkelproces, omdat het helpt om de technische details van je project te plannen en te communiceren met anderen.
>
> Het FDD beschrijft wat je gaat bouwen, terwijl het TDD beschrijft hoe je het gaat bouwen.
>
> Onderdelen van een TDD kunnen zijn:
> * System Architecture: 
>   * In welke componenten kun je je applicatie opdelen? 
>   * Hoe communiceren die met elkaar?
> * Technical Stack: 
>   * Een lijst van de technologieën en tools die je gaat gebruiken (denk aan frontend, backend, database, etc.) en de versies daarvan.
> * Deployment: 
>   * Hoe ga je je applicatie deployen (online zetten, domeinnaam, ...)?
> * Technical Specifications: 
>   * Uitgewerkte technische specificaties zoals API-endpoints, databasediagram, etc.
> * Backlog: 
>   * Lijst van taken die nog moeten worden uitgevoerd, inclusief technische taken die nodig zijn om de functionaliteit te implementeren.
> * User Acceptance Test (UAT): 
>   * Een testplan om te controleren of de app voldoet aan alle functionele, ontwerp- en codekwaliteitseisen vanuit het perspectief van de eindgebruiker.
>
> ## System Architecture
> Game can be devided into these main components that will need to be programmed:
> * Factory components
>   * Beer Filter
>   * Water Pump
>   * Beer mill
>   * Beer Storage
>   * Retail Center
> * Factory component upgrades
> * Weather
>   * Heavy Rain
>   * Drought
>   * Neutral
> * Water Pollution
> * Camera
>   * Camera movement
>   * Factory component selection
>   * UI displaying game information
>
> The game will be stored the server hosting the website, which the client will then download in order to view and play the game.
>
> ## Technical Stack
> This will be a 3D Unity game, built in the 6000.3.2f1 version of the editor. We will be using C# for our script and writing them in Visual Studio.
>
> ## Deployment
> The game will be deployed in a Web build integrated into a website that our web developer will be developing for his assignment. Exact URL is not yet clear.
>
> ## Technical Specifications
> The game will be making use of Unity's API, but not much beyond that.
>
> ## Backlog
> We have a Project board in the project's Github repo.
> <https://github.com/orgs/Sint-Lucas/projects/696/views/1>
>
>
> ### User Acceptance Test (UAT)
> Controleer of de app voldoet aan alle functionele, ontwerp- en codekwaliteitseisen vanuit het perspectief van de eindgebruiker.
>
> - [ ] The game includes all of the factory components listed above in a fully functional form
> - [ ] The game has an upgrade system
> - [ ] The game has a moveable camera
> - [ ] The game has a weather system that impacts gameplay
> - [ ] The game has a pollution mechanic
> - [ ] The game has an environment score displayed to the player in UI
> - [ ] The game has a message about the effects that pumping too much water has on the environment
>
> ### Test Cases
>
> | Test Case ID | Description                                                                                      | Steps to Test                                                                                                                                             | Expected Result                                                          | Pass/Fail |
> |--------------|--------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------|-----------|
> |              |                                                                                                  |                                                                                                                                                           |                                                                          |           |
> |              |                                                                                                  |                                                                                                                                                           |                                                                          |           |
> This will be filled in later, upon testing.
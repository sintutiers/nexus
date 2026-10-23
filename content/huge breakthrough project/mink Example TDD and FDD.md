---
unlisted: true
uid: o1pk0ngezrjc2a372yc9w
title: FDD Example Game to Kinda Base it on
modified: Friday, October 23rd 2026, 12:56 pm
created: Monday, October 19th 2026, 7:34 pm
---

# FDD Example Game to Kinda Base it on

> [!NOTE]- FDD Example Game to Kinda Base it on
> ## General Description
> Inspired by the "Insaniquarium" game,  "AquaMystics" plunges players into an underwater realm. Here, players nurture aquatic creatures and defend against mysterious threats..
>
> ### Dynamics
> Resource Management: Gain money, spend it to care for your creatures, make more money!
>
> Strategic Defense: Defend your creatures from threats.
>
> Care and Nurture: Keep your creatures healthy and growing.
>
> Risk and Reward: Deciding whether to save currency for bigger upgrades or spend on immediate needs.
>
> ## Functional Requirements
> Feeding Mechanism:
> - Players tap/click to feed creatures. This costs currency.
> - Food falls down slowly and dissapears when it hits the bottom.
>
> Creatures:
> - The player can buy a creature.
> - The creature stays within the aquarium.
> - Creatures can get hungry.
> - When hungry they will swim to falling food. If not hungry, they won't.
> - If it gets no food, it dies.
> - After enough food, a creature can grow.
> - A creature can't grow beyond a certain limit.
> - Some creatures might behave in different ways like swiming around, staying at the bottom of the aquarium, being really fast or attacking threats.
>
>
> Currency:
> - Creatures generate currency if they are big enough.
> - Currency falls down like food and dissapears if it hits the ground.
> - Currency can be collected by clicking it.
> - The bigger the fish, the more currency it makes.
> - Currency can buy the following:
>   - Upgrade your food quality.
>   - Buy more creatures.
>   - An idividual food.
>   - A damage upgrade.
>   - The win condition which finishes the level and unlocks the next level.
>
>
> Hostiles:
> - Hostile creatures can appear randomly.
> - Before it appears, you get an indicator and warning that it is about to spawn and where.
> - They start chasing your creatures.
> - If they touch a creature, it dies.
> - You can kill the hostile to by clicking it to deal damage to it.
> - There can be unique hostiles like a version that can dash, teleport, shoot projectiles, etc.
>
>
> General game progression:
> - The game is level based.
> - Each level gets more difficult.
> - The type of creatures and hostiles can vary from level to level.
> - Winning a level rewards the player with currency that is not relevant to the levels.
> - The player can spend this currency in a universal shop.
> - This universal shop will allow the player to buy minor upgrades or unlocks like:
>   - Starting every level with better food quality.
>   - Starting every level with more starting currency.
>   - Cosmetic changes to the aquarium background.
>
> ## Non-functional Requirements
>
> ### Performance
> * The game should not lag or reduce below 60 frames per second, even while the player and enemies are shooting.
>
> ## Refinement of Each Requirement
> Refine each requirement and include drawings below.

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
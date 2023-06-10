# Ex No :07

# <p align="center"> Implement the AI chasing when AI see the player </p>


## Aim:
To create a Unreal project That have AI character To Chase the Player

## Procedure:
1.Open Unreal Engine and create a new Blueprint project.

2.Create a Blueprint class for your character: • Right-click in the Content Browser and select "Blueprint Class." • Choose "Character" as the parent class. • Name the Blueprint as desired.

3.Create a Blueprint class for the AI controller: • Right-click in the Content Browser and select "Blueprint Class." • Choose "AI Controller" as the parent class. • Name the Blueprint as desired.

4.Open the AI controller Blueprint: • In the Event Graph, right-click and search for "Blackboard." • Add a "Blackboard" node to the graph and name it "MyBoard."

5.Open the Blackboard: • Create a new Key named "TargetLoc" with the Vector data type.

6.Create a Behavior Tree (BT) Blueprint: • Right-click in the Content Browser and select "Blueprint Class." • Choose "Behavior Tree" as the parent class. • Name the Blueprint as desired.

7.Open the Behavior Tree Blueprint: • Create a sequence node by dragging and dropping it from the palette onto the graph. • Connect the sequence node to the root node.

8.Add a "Move To" task to the sequence: • Drag and drop the "Move To" task from the palette onto the graph. • Connect the output of the sequence node to the input of the "Move To" task.

9.Add a "Wait" task after the "Move To" task: • Drag and drop the "Wait" task from the palette onto the graph. • Connect the output of the "Move To" task to the input of the "Wait" task.

10.Add a Service to the "Move To" task: • Right-click on the "Move To" task and select "Add Service." • Choose "BTService_BlueprintBase" as the service. • Set the Blackboard Key of the service to "TargetLoc." • Open the service by double-clicking on it.

11.In the Event Graph of the service: • Create a variable named "BK" of type "Blackboard Key Selector." • Use the "Event Receive Activation AI" event node. • Connect the execution pin of this event to the "Set Blackboard Value as Vector" node. • Connect the "Key" of the "Get BK" variable to the "Key" pin of the "Set Blackboard Value as Vector" node. • Connect the "Controlled Pawn" pin of the event to the "Get Actor Location" node. • Connect the return value of the "Get Actor Location" node to the "Get Random Reachable Point in Radius" node. • Connect the output of the "Get Random Reachable Point in Radius" node to the value pin of the "Set Blackboard Value as Vector" node.

12.Create a new Blackboard key named "Player": • In the Behavior Tree Blueprint, open the Blackboard. • Create a new key named "Player" with the Object data type. • Choose "Actor" as the base class for the "Player" key.

13.In the Behavior Tree: • Create a new sequence node from the selector node. • Add a "Blackboard Condition" task to the sequence. • Add the "Move To," "Rotate to Face BB Entry," and "Wait" tasks to the sequence. • Add the "Player" key to all the tasks created in the Behavior Tree.

14.Open the AI Perception Blueprint: • In the Event Graph, add an "On Perception Update" event.

15.Use a "For Each Loop With Break" node: • Connect the output of the "On Perception Update" event to the "For Each Loop With Break" node. • Iterate through the "Currently Perceived Actors" array.

16.Get the AI Perception: • Use the "Get AI Perception" function on the currently perceived actor. • Cast it to the third-person character you created earlier.

17.Get the Blackboard and set the value: • Get the Blackboard and make a literal name for the key. • Set the value as an object. • Connect this function correctly to the rest of the logic.

18.In the AI Perception Sense Config details panel: • Enable the "Detect Neutrals" option.

19.After completing all the steps, place the AI character in the viewport: • Drag and drop the AI character Blueprint into the viewport to place it. • Ensure that the third-person character is also present in the scene for the AI character to chase.

## OUTPUT:
### Content browser:

![243110779-d6370c1c-efda-40e8-a39a-fff5d75e4b30](https://github.com/durga46/ex7.gameprogramming/assets/75235704/aa0c494f-f57f-4a68-92f6-8ee2b1b71570)

### Third_Person character:
![243110780-16cbdd56-16c2-4212-a3ea-600dcea82eb7](https://github.com/durga46/ex7.gameprogramming/assets/75235704/6a3bf752-95a0-4faf-95e7-996331edfdc4)


### AI character:
![243110785-5ce7ad65-71d8-450e-b3ba-25b7502fae14](https://github.com/durga46/ex7.gameprogramming/assets/75235704/63f3d54e-1bf1-41c7-9101-2c956b705159)


### AI Controller Event graph:
![243110788-908b2f7e-c3c5-40cb-9ae2-bc65e941fbd8](https://github.com/durga46/ex7.gameprogramming/assets/75235704/0c73b84c-38da-4d7e-9759-9b8602211600)
![243110801-103dcdce-289b-48be-989b-770ee1017b1e](https://github.com/durga46/ex7.gameprogramming/assets/75235704/58c89279-68ce-4474-927a-497464d05ef9)


### MY Black Board:
![243110815-6f52fae9-ecea-4021-92f7-b279d441df3f](https://github.com/durga46/ex7.gameprogramming/assets/75235704/f0654175-e599-487f-b26f-29cfc5f0479f)
![243110820-f8e8202b-99e6-472b-b1ee-a64356f904ab](https://github.com/durga46/ex7.gameprogramming/assets/75235704/e814452b-bb7f-48b3-a523-c2aabe6a4c10)


### MY Behavior tree:
![243110834-6d833dd3-5771-428c-a972-f69f1f9184b3](https://github.com/durga46/ex7.gameprogramming/assets/75235704/72285959-ad7a-4589-982e-6be026d42e09)


### Service:
![243110842-bd28f51f-84df-445e-a6a1-5dbb27a4aa00](https://github.com/durga46/ex7.gameprogramming/assets/75235704/11933b30-b66f-4861-9dda-7282e1a60eb9)


### Blackboard key:
![243110852-5160695f-2f65-44a0-966b-dc7f1b75dc8d](https://github.com/durga46/ex7.gameprogramming/assets/75235704/1e4d7e2d-44e2-404a-9cfa-73ce68a8c53d)



### AI Perception:
![243110860-069eca84-eddd-46c2-9319-fe2d89b965e2](https://github.com/durga46/ex7.gameprogramming/assets/75235704/261ecd45-30af-401c-b3a8-6771899368e5)


### AI Movement:
![WhatsApp Image 2023-06-08 at 5 56 38 PM (4)](https://github.com/durga46/ex7.gameprogramming/assets/75235704/a8d2cbc7-60b5-4abe-9265-4348d2296739)


## Results:
Thus we successfully created a Unreal project That have AI character To Chase the Player


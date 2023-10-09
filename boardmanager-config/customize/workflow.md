# Workflow
The Board Manager Workflows are used to automate the creation, movement, and management of Boards, Lists and Cards.

Board Manager options can be used in other Hornbill Applications through the Business Process Designer.
* Use the Automated Tasks node, and find the Board Manager options under the Application drop-down.

## Board
### Get Board Information
Use this node to retrieve information about a specific Board.
#### Options
* **Application**<br>The name of the Application the Board belongs too - Mandatory
* **Entity**<br>The name of the list from the above specified board to which the Comment card will be added.
* **Entity ID**<br>The actual comment, as it will appear on the card on the Board.
* **Board**<br>The name of the board you wish to get information about.

## Card
### Add to Board
Use this node to manually add a card to a Board at the required stage in a process.

#### Options
* **Application**<br>Optionally choose which application the card you want to add to the board originates from. The benefit of doing this is it will automatically define and populate the values for the Title, Content, Link, and Card Type options below. If you want to manually set these values for the card you are adding, then leave this option as Auto otherwise it will overwrite any manually entered values in the other options mentioned previously.
* **Key**<br>The Key identifier for the new card, in the case of Service Manager requests this will be Requestid.
* **Board**<br>The name of the Board on which the card will be added.
* **Lane**<br>The name of the lane from the above specified board to which the card will be added.
* **Lane Column**<br>The column within a lane to which the new card will be added, if not specified the card will be added to the first column in the lane. This option expects a zero based index to the column, so the supplied value should be the column number minus 1.
* **Order**<br>The position the card will appear in on the lane of the board, if not specified the card will appear at the top of the lane. You can use the Get Lane Information option to get the next available position for a card on the lane.
* **Value**<br>A value for the card, for example scrum points, cost.
* **Progress**<br>A numerical value between 0-100 represents the progress to completion on the card.
* **Title**<br>The title of the card on the board. This value will be ignored if the Application option is populated.
* **Content**<br>The content of the card on the board. This value will be ignored if the Application option is populated.
* **Link**<br>This will allow you to open in a pop-up or other tab if configured. This value will be ignored if the Application option is populated.
* **Card Type**<br>The type of the new card, there are various card types to choose from, please review these on the Card Types wiki page. This value will be ignored if the Application option is populated.

### Get Card Information
This Hornbill Automation retrieves the details about a card on a board. This includes the lane that the card resides in on the board, the progress made on the card, the order of the card on the board, and other useful properties. This node can be used once at the beginning of a Workflow stage and does not need to be used each time you want to move or remove a card in a stage.

#### Options
* **Board**<br>This is a mandatory option and is needed to identify the board that the card resides in.
* **Lane**<br>This option can be set with the name of the lane that the card resides in. This is optional and should only be set when a card with the same key appears with two different types on the same board.
* **Key**<br>The key identifier for the card. For example in Service Manager, the Id of a Request is the key identifier.

### Move Card on Board
Use this option to move a card between lanes on a board.

#### Options
* **card Id**<br>This is a mandatory setting and is needed to identify which card to move on the board. You can get the card ID by first having a Get Card Information node in the stage on the process, and using the output param as a variable for this field using the variable picker.
* **Lane**<br>The name of the lane on the board which you wish to move the card into.
* **Order**<br>The position the card will appear in on the lane, if not specified it will appear at the top of the lane.

### Remove Card from Board
Use this option to remove a card from a specific board.
#### Options
* **card Id**<br>This is a mandatory setting and is needed to identify which card to remove from the board. You can get the card id by first having a Get Card Information node in the stage on the process, and using the output param as a variable for this field using the variable picker.
It is possible that a card resides on different boards, and will therefore have different card id's for each board. As such you will need to obtain the card ID for the board you wish to remove the card from.
* **Remove Completely**<br>The default is false, and the card will be archived, if set to true the card will be completely removed from the board and will not be able to be manually un-archived.

## Lane
Use the Lane operation to get information about the card position and order in the lane, in order to have the information available when using other operations like Add to Board and Move on Board if you want to add a card to the next position on a lane, as appose to always adding it to the top.

### Get Lane Information
Use this node to obtain the next card position and order on a given lane on a board. Once this node has been used, you can use the output params from it via the variable picker to insert new cards onto boards and lanes using the Add to Board and Move on Board operations.

#### Options
* **Board**<br>The name of the Board on which the lane exists.
* **Lane**<br>The name of the lane against which you wish to obtain the information.
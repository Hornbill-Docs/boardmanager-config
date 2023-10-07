# Autotasks
Autotasks can be created for Board Manager these can be used in the following places:

By creating a Custom Button on the Board
By creating a Custom Button on the Card
By creating an automation for a board which can be triggered when a card is added, removed, or updated
By creating an automation for a lane which can be triggered when a card enters (either created in, or moved into a lane) or exits (either removed whilst in a lane, or moved out of a lane)
To create autotask a user must have the manage BPM system right, this right can be granted by the Autotask Designer role

The following inputs are sent:

Board Custom Button
boardId - Id of the board
title - Name of the Board
content - Description of the Board
Card Custom Button / Card Created automation / Card Updated automation / Enter Lane automation / Exit Lane automation
boardId - Id of the Board
cardId - Card Id
laneId - Lane Id
title - Card title
content - Card content
link - Card link
value - Card value
type - Type of card
progress - progress of card from 0-100
key - Id of the related entity (e.g. Request Id, document Id etc)
status - Card status
status_info - Card
action - Automation action: one of CREATE/UPDATE/ENTER/EXIT
Card Removed automation
boardId - Id of the board
cardId - Card Id
action - REMOVE
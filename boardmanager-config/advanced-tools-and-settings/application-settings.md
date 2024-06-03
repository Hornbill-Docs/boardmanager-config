# Application Settings
The various application settings associated with Hornbill Board Manager can be configured in Configuration under the Board Manager app. This document describes some of the more commonly used settings. This is not a complete list and more settings can be viewed within Configuration.

## Before You Begin
* The Board Super User role is required to access the Board Manager settings.
* Be familiar with how to use [Configuration](/esp-config/getting-started/using-configuration).

## Accessing Application Settings
1. Select the Configuration Cog on the bottom of the left-hand application menu bar
1. From the Configuration Selector choose Board Manager
1. Scroll the navigation panel and find the section Advanced Tools and Settings
1. Select Application Settings

## Filters
At the top of the list there are some options available to help you find the different available settings.

![Advanced Settings](_books/boardmanager-config/advanced-tools-and-settings/images/include-advanced-settings.png)

Advanced settings are less used and potentially more complex to change.  Advanced settings are not displayed in the list of settings by default. If you are unable to find a particular setting, you may find that it is classed as an advanced setting and selecting this option will make it visible in the list.

* **app.view.board.largeboard**<br>This setting limits the number of cards that are available to a single board. The default is set to 200 cards. The number of cards on a board will affect performance and it is not recommended to go above the default value of 200.
* **webapp.view.boardlist.favouriteFilter**<br>Turn this setting on to allow users to define and view a Favorites list when viewing the list of available boards.
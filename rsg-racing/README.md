# ItsANoBrainer

If you like or use this resource, please consider supporting by starring the repo and checking out my other resources.

## _QBCore Racing_
Original code converted, tied up, slightly rewritten, and features added from [qb-lapraces](https://github.com/qbcore-framework/qb-lapraces).

I really liked the qb-lapraces, but I wanted a standalone version that did not require qb-phone, as well as some custom features so here it is!

This so

QB-Racing lets you manage your racing scene in a better way using items and custom racer names instead of player names! There are two items involved, the `master racing fob`, and the `basic racing fob`. At the moment, these are created using the `createracingfob` command by a qb-core admin, but you can implement any system you want. When created, the fob is bound to the citizenid it was created for, and has a racer name attached to it. Only the citizenid created for it can use it. Using the fob brings up the racing options menu (examples below) which is where you do all the interacting with the script. Each fob has an entry in the Config to tune it to your server to allow or deny certain usage abilities (listed below). By default the master racing fob is required to CREATE new race tracks, and both dongles allow you to do everything else.

Config Options per Dongle:
 - Join a race
 - View race records
 - Setup a new race
 - Create a new race track

## Setup
You only need either this resource, or qb-lapraces, not both. I have not tested if they work independently together.

1. Update or insert the database table. Instructions are found in the `racing.sql` file
* Option 1: Updating from qb-lapraces must follow OPTION 1 to update their database table and preserve their race tracks
* Option 2: NOT updating from qb-lapraces must follow OPTION 2 to create the database table 
2. Adjust values in the `config.lua` file to your likings
3. Add the items to your `qb-core/shared/items.lua`
```lua
['fob_racing_basic'] = {['name'] = 'fob_racing_basic', ['label'] = 'Basic Racing Fob', ['weight'] = 500, ['type'] = 'item', ['image'] = 'fob_racing_basic.png', ['unique'] = true, ['useable'] = true, ['shouldClose'] = true, ['description'] = 'This basic fob allows someone to join custom races.'},
['fob_racing_master'] = {['name'] = 'fob_racing_master', ['label'] = 'Master Racing Fob', ['weight'] = 500, ['type'] = 'item', ['image'] = 'fob_racing_master.png', ['unique'] = true, ['useable'] = true, ['shouldClose'] = true, ['description'] = 'This master fob allows someone to create custom races.'},
```
4. Add the item images to your inventory image folder
5. Until my [qb-menu pull request](https://github.com/qbcore-framework/qb-menu/pull/23) is approved (or denied), permission enable/disable config support will not work. You can either wait for the PR, just make the changes in the PR to your version, or implement your own logic in the script.

## Dependencies
* [qb-menu](https://github.com/qbcore-framework/qb-menu)
* [qb-input](https://github.com/qbcore-framework/qb-input)

## Features
* Standalone racing script not requiring qb-phone to utilize
* Items to immerse your racing scene with Racer Names
* Config options to adjust item permissions to your liking
* Config options to adjust different options
* Locale Support
* Create Custom Races Tracks

## Example Usage
### Interface Examples
![Interface](https://i.imgur.com/4SyDq5k.png)

### Video Example
#### Creating a Race
[![Video Example](https://i.imgur.com/DCFUJw9.png)](https://i.imgur.com/WoSxall.mp4)
#### Race Interface, Joining a Race, Finishing a Race
[![Video Example](https://i.imgur.com/hsZVHeL.png)](https://i.imgur.com/oYgHBdj.mp4)

## Change Log
#### 1.02
* Use item hotfix
* Added InfoBox on inventory item add for createracingfob

#### 1.0
* Initial release

## Future ToDos
* Ability to delete race tracks ingame

## Other Creations
* [FiveMArtifactUpdater](https://github.com/ItsANoBrainer/FiveMArtifactUpdater)
* [qb-scenes](https://github.com/ItsANoBrainer/qb-scenes)


## License
[GNU GPL v3](http://www.gnu.org/licenses/gpl-3.0.html)

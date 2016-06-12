# Most Wanted: An Exile Bounty Mod

### Features
* Exile security
* Made with Exile's UI in mind
* Bounty contracts require players to pick and choose targets that they go after. Anyone is free game, but only one person can claim the bounty.
* Completed contracts allow players to hold onto contracts before cashing them out. 
* Friend's list keeps players from setting bounties on their friends.
* Immunity protects players from bounties being set on them after they have been killed by a contracted killer. 

### Installation 
#### extDB
1. Copy `MostWanted-SQL.sql` into your favorite mySQL viewer's query window and run it.
2. Confirm you have a `bounties` table. 

#### Server
1. PBO `MostWanted_Server` and place in `@ExileServer\addons` folder. 
2. Copy the contents of `MostWanted-extDB.ini` into your `@ExileServer\extDB\sql_custom_v2\exile.ini` file at the bottom.

#### Client
1. Copy `MostWanted_Client` folder into the root of your `exile.MAPNAME` mission folder. 
2. In your `init.sqf` or `initPlayerLocal.sqf`, add `[] execVM "MarXet\MarXet_Init.sqf";`
3. In your `description.ext`, add 

            #include "MostWanted_Client\Dialog\MWDefines.hpp"
            #include "MostWanted_Client\Dialog\RscMostWantedDialog.hpp"
4. In your `config.cpp`, add at the top, `#include "MostWanted_Client\CfgMostWanted.hpp"`
5. `Notifications.hpp` and `NetworkMessages.hpp` both will depend on your set up.

    If you **ALREADY** have `class CfgHints` or `class CfgNetworkMessages` **ANYWHERE** in your `description.ext` or `config.cpp` in your exile.MAPNAME folder:

    Add `#include "MostWanted_Client\NetworkMessages.hpp` in `class CfgNetworkMessages`
    
    Add `#include "MostWanted_Client\Notifications.hpp` in `class CfgHints` so it looks kind of like what is below. 

    If you don't have `class CfgHints` or `class CfgNetworkMessages`, in your `config.cpp`, add this anywhere.

           class CfgHints
           {
                #include "MostWanted_Client\Notifications.hpp"
           };

           class CfgNetworkMessages
           {
                #include "MostWanted_Client\NetworkMessages.hpp"
           };
6. You are done! Head on down to configuration.

### Configuration
Most Wanted has a few configuration options, they are inside `MostWanted_Client\CfgMostWanted.hpp`, please review these as that they control the functionality. 

### SERVER OWNERS, PLEASE READ
A note on exploiting. A lot of time and effort went into making sure exploiting was difficult and a pain in the ass to do with this script. If you find an exploit or notice players finding exploits, **DO NOT POST THEM ON THE EXILE FORUMS OR IN THE TOPIC COMMENTS**. 

To properly report these:
1. Private message (Taylor Swift)[http://www.exilemod.com/profile/472-taylor-swift/] or (WolfkillArcadia)[http://www.exilemod.com/profile/12063-wolfkillarcadia/]
2. Include, in detail, how to replicate the exploit, providing step by step instructions. 
3. We will look into the proper way, if any, to keep it from happening. ArmA will be ArmA in some cases. 
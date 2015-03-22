# sparcraft
Automatically exported from code.google.com/p/sparcraft
SparCraft is an open source abstract StarCraft combat simulation package for Windows and Linux. It can be used to create standalone combat simulations or be imported into an existing BWAPI-based StarCraft bot to provide additional AI functionality.

SparCraft was built with speed in mind, and uses a system of frame fast-forwarding to bypass game frames during which no combat decisions are being made (ie: during attack cooldowns, movements, etc). Using this system, SparCraft can easily perform tens of millions of unit actions per second.

SparCraft is abstract in the sense that it does not perfectly model all aspects of StarCraft. Since no StarCraft source code is available, all combat logic is our best guess at what is happening in the game engine. It is meant to be a simple testbed for AI systems playing an abstract version of a very complex RTS game. It does not need to perfectly model all StarCraft features to do this job.

SparCraft currently contains the following functionality:

Accurately models all unit size, weapon, armor and damage types
Accurately models all unit upgrades and research types
Accurately models unit speeds, attack cooldowns and animation frame timings
Can extract map files straight from StarCraft for use in simulation
SparCraft Unit Movements

While SparCraft supports arbitrary pixel-precision movements, GameState::generateMoves() only generates UP, DOWN, LEFT, RIGHT movements of a fixed length. This abstraction is to give the search algorithms a reasonable number of actions to search over. This means the standalone version of SparCraft only supports 4-directional movement, but if you edit the code yourself you can implement arbitrary movements.
SparCraft does not yet contain the following functionality:

Unit Collisions - This is by design. Unit collisions are expensive, the point of the system is to be fast
Fog of War
Spell-Casting or Splash Damage (Muta 1-hit only)
No Burrowing or Cloaking / Detection
Non-Deterministic Aspects (such as random hit chance)
Vision Up Ramps
Unit turning or acceleration
Despite these features not yet being included, SparCraft simulations demonstrate a high level of accuracy with what happens in an actual StarCraft battle. The accuracy of these simulations however diminishes as battle sizes increase, due to the lack of unit collision functionality.

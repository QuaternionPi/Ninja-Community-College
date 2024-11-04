# Ninja Community College


# User Stories
## John Helldiver Plays a Single Turn
- John Helldiver decides to play a single turn of Ninja Community College
- He opens the application to the [Main Menu](#main-menu)
  - He clicks load game  
- This opens the [Load Game Menu](#load-game)
- John is then shown a view of the [map](#maps), with 5 [units](#units) who are about to enter a 2 floor [building](#buildings)
- He then orders 3 units to [breach](#breaching) through a [door](#buildings)
- One unit [climbs](#climbing-surfaces) up the side of the building and through a [window](#buildings)
- The final unit continues up the building to the roof

# Menus
## Main Menu
- Continue Game
- New Game
- Load Game
- Settings
- Quit to Desktop

## Load Game
Presents a list of games with options to:
- Load Game
- Delete - requires confirmation
- Rename - presents rename bar

# Maps
## Structure
- Maps contain buildings, furniture, evac points, and units
- Everything can have supporting surfaces
- Everything can provide cover

## Supporting Surfaces
- Supporting surfaces allow a unit to stand on
- Horizontal movement can be done by walking and dashing on a support surface
- Jumps can be made from a supporting surface
- Weapons can be used from a supporting surface

## Climbing Surfaces
- Climbing surfaces allow a unit to climb up
- Climbing occurs on one side of the surface and moves the unit vertically
- Jumps can be made from a climbing surface
- Limited weapons can be used from a climbing surface

## Buildings
- Buildings are structures with floors, walls, windows, doors and internal supports
  - Their floors are supporting surfaces
  - Walls provide cover and are hard to destroy
  - Walls can be scaled from the outside of the building
  - Windows are enterable, and provide a position to shoot from
  - Doors are enterable and breachable
- Buildings can contain elevators and stair cases
  - These allow internal vertical traversal of a building
- Upon the loss of enough internal supports the building collapses
  - A building collapse does lots of damage to its occupants and destroys valuables inside

## Pillars
- Pillars are special kinds of buildings with no volume and climbing surfaces on either side
- Examples include trees and power poles

## Furniture
- Furniture encapsulates objects that can be found on the map
- Examples include crates, vehicles, explosives and objectives

## Evac Points
- Units can leave a mission early by reaching an evac point
- Upon departure, units not at the evac point will be lost
- Early evacuations are encouraged in losing situations

# Mission Types
## Targeted
- Kill Demon or Cultist leader
  - Final Mission to kill The Devil
- Retrieve/destroy item/person

## Mass Assault
- Destroy building
  - Demon nest, Cultist temple
- Clear area

# Story Missions


# Units
- Units are the main points of interaction in the game
- They can be ordered to perform actions on the map
  - This includes moving, shooting, melee combat and interacting with the environment

## Stats
- Health: int
  - How much damage can this unit take
- Defense: int
  - Protection level from enemy attack
- Speed: int
  - Amount of action doable per turn
- Conscious: bool
  - Is this unit still conscious
- Class: Object

## Class
- Assault
  - Short range
  - High health 
- Sharpshooter
  - Mid-long range
  - Heavy caliber weapons
  - Not very mobile
- Melee
  - Zero range
  - Stealth
  - Acrobatics
  - Quiet shooting, stabbing
- Skills come in levels
  - Can only take 50% of skills per level
  - Highest level unit referred to as senior
- Captain
  - The senior in a battle with out a surviving captain becomes a captain
  - Keeps original skill tree

## Unconscious
- Once a unit's health falls below 20%, it becomes unconscious
- Unconscious units are unable to do anything
- The can be rescued, kidnapped or killed

## Movement
- They occupy a position on the map
  - They can stand on a supporting surface
  - Climb on a climbing surface
  - Jump between surfaces

## Squad Actions
- Several units can be ordered to perform actions in concert, called squad actions

### Breaching
- Multiple units queue at a door
- Once they are all in position, the enter
- Useful for entering hostile spaces
- Can order grenades or explosives thrown in upon entry

### Focus Fire
- Order many units to focus on a single unit
- Will wait until all units are ready 
- Prevents one unit from breaking surprise on enemies

### Protect
- Units use their body as cover for another unit
- Causes movement speed penalty

### Squad Move
- Units move as a squad, prevents one unit from running ahead or behind

## Carrying
- Units can pick up and carry objects
- This includes items around the map and unconscious units
- Carrying 'heavy' objects causes a move speed penalty
- Carrying limits the use of weapons

# Combat


# Abilities


# Factions
## Ninjas
- Units can be sent into hell to reduce demon aggression
  - Higher level higher reduction in aggression
  - Can come back in difficult circumstances
  - Can appear in battles in hell

## Cultists


## Demons


# Graphics



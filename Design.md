# Ninja Community College


# User Stories
## John Helldiver Plays a Single Turn
- John Helldiver decides to play a single turn of Ninja Community College

### Loading the Game
- He opens the application to the [Main Menu](#main-menu)
  - He clicks load game  
- This opens the [Load Game Menu](#load-game)
- John is then shown a view of the [map](#maps), with 5 [units](#units)
- They are about to enter a 2 floor [building](#buildings) with a sky light
- The mission is to [clear the building](#mission-types)

### Turn Simulation
- He then orders 3 units to [breach](#breaching) through a [door](#buildings)
- One unit is ordered to [climb](#climbing-surfaces) up the side of the building and through a [window](#buildings)
- The final unit is ordered to continue up the building to the roof
- It is then ordered to [loss a grenade](#carrying) he was carrying down the sky light

### Turn Combat
- The breach squad enters via the front door
- They shoot and kill 2 [demons](#demons)
- The window entrance unit interrupts a [cultist ritual](#cultist-rituals)
  - He hides behind [cover](#cover) and shoots at the cultists
- Finally the roof unit drops a grenade in through the roof
- The grenades [AoE](#area-of-effect) kills the cultists
- The remainder of the turn plays out

### Exiting
- Every enemy on the map is now dead
- The mission is complete

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

## Cover
- Cover is absolute, often destructible, protection from most attacks
- Buildings, furniture and protection orders provide cover
- Cover can be shot from

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
## Capture Demon
- Capture a demon and torture information from him
- He reveals heaven isn't real

## Convert Cultists
- Retrieve senior Cultist from temple
- Show him heaven isn't real

## Final Mission
- Summon a portal to hell
- Bring a squad of ninjas and turned Cultists
- Need to complete a ritual to close all portals

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

## Class Progression
### Generic Classes
All units in the game take one of the following classes:
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

### Rock Paper Scissors
- Assault units beat Melee units
- Melee beats Sharpshooter
- Sharpshooter beats Assault

### Ninja Classes
Ninjas progress in levels.
- They can only take 50% of skills per level
- Highest level unit referred to as senior
- Skills are given some bias to their cost
  - This cost is randomized per unit

Ninjas Can optionally have the class of Captain.
- Captain
  - The senior in a battle with out a surviving captain becomes a captain
  - Keeps original skill tree
  - Has additional skills to boost the whole team

### Cultist Classes
Cultists progress by upgrading their abilities.
Each level they can gain one (pre-determined) skill in their chosen class. 
- Cultist who are the most senior of their class at the end of a mission become Priests
- Priests are like Ninja Captains, however they gain class-specific team boosts
- Priests can conduct ceremonies
  - Ceremonies require at least one Priest at all times
  - This priest cannot use attacks until the ceremony is completed or cancelled

### Demon Classes
- Demons grow in strength by consuming human souls
- This can happen on the battlefield!
- Once demons reach the final level in their class they have two options
  - Become class-specific, powerful killing machine
  - Become a Demon Lord and leave the map, increasing demon aggression

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
- Carried items can also be dropped or thrown

# Combat
## Damage Calculation
- Any combat action will use $Attack$ and $Defense$ and compute $Damage$
- The formula for damage is as follows
  - $Damage = max(Attack-\frac{Defense}2, \frac{Attack}2)$
  - So if $Attack \lt Defense$ then $Damage=\frac{Attack}2$
  - Otherwise $Defense \leq Attack$ then $Damage=Attack-\frac{Defense}2$
- $Attack$ is primarily controlled by the attacking weapon
- $Defense$ is primarily controlled by attacked

## Melee
- Melee weapons are high attack, zero range weapons
- They are stealthy
- They can be thrown at range, but have to be recovered

## Ranged Weapons
- Ranged weapons are medium-high attack
- The make noise and aren't conducive to stealth
- The have an attack value and set up time, as well as range
- Ranged weapons can have lower set up, lower attack uses
  - Consider a quick shot, aimed shot, and multi shot
  - Each having a time to damage difference

## Area of Effect
- Certain weapons will do area of effect damage
- This effects a radius around the point of explosion
- It can damage building's internal supports
- Explosions will have a radius $r$, within which full damage is done
- Within a radius of $2r$ only half damage is done
- Examples include grenades and explosives

# Abilities


# Factions
## Ninjas
- Units can be sent into hell to reduce demon aggression
  - Higher level higher reduction in aggression
  - Can come back in difficult circumstances
  - Can appear in battles in hell

## Cultists
- Think the way to save souls is to stop people from sinning
  - This is done by speeding up the end of days
  - Have accepted they are going to hell
- Have summoned demons to kill everyone
- Want you to fight back, to save your own soul

### Cultist Rituals
- Cultists perform rituals to aid demons
- Most commonly to open a demon portal

## Demons
- Known heaven isn't real
- Are fading souls, extending their lives by consuming humans
- Satan is old, bored and wants to stop existing
  - He can only die once there are no more souls on earth

## Civilians
- Civilians are humans found around the map
- They can be consumed by demons, granting them powers

### Civilian Combatants
- Some civilian will take up arms
- If they are found they will be brought under your control
- If they survive a round they may be available to recruit

# Graphics
## Dimensions
- The game is 2 dimensional pixel art
- The background is parallax scrolled on the x-axis
- Play takes place on the z=0 layer of the parallax

## Character Sprites
- Character sprites are comprised of 2 components:
  - Color textures, texture of colors 
  - Lookup texture, texture of indexes in the color texture
- The character sprite are made by:
  - Replacing pixels in the lookup texture with their indexed location in the color texture
  - Then blending on top any additional color textures


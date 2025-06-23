---
title: "Implementing Run from Cool Math Games in C!"
excerpt: "(Game Design, Software) Created a C-based implementation of Run from scratch with a custom physics engine<br/><img src='/images/cs003-2024spring-intermediate.png'>"
collection: portfolio
---

# Game Features and Design Docs
## Gameplay
Our game will not consist of levels, but rather, progress through changing scenery. The game progression looks like the sprite running through an eternal tunnel, with holes in the ground as well as obstacles that need to be avoided. The trace of the tunnel will be square, so the player will be able to glide along the walls and reorient the world. The player’s goal will be to last as long as possible in the game and collect as many points as possible; hence there are no particular win conditions. Points are awarded based on the number of coins a player collects during the game. The loss condition will be falling through the hole tiles (i.e. not landing on a solid tile). There will also be tiles that disintegrate shortly after they are landed on so this will also be a potential loss condition.

Controls:
Our game will leverage the keyboard for the user to control the motion of the sprite. The space bar will be used to jump, the left and right arrow keys will be used to move the player to the left or right respectively.

Physics: 
Gravity will be used for the player’s jumps. Destructive collisions will be used to keep count of the coins the player collects because when the player comes in contact with a coin, it will disappear and the point total will increase.

Game Flow:
The player will use the controls to move their sprite around in the continuous environment. As the environment moves past them, they will be avoiding holes in the ground and tiles that fall when the player comes in contact with them. All the while, they will be trying to collect coins along the way and travel as far as possible. If the player collides with the walls on the side, then the entire screen will rotate (in a discrete fashion) and the tiling will swap so that the tiling patterns that were on the side will now be on the ground. The game will be over if the player falls through the tunnel. 


Graphics:
The main sprite and coins will be drawn, while the scene itself will be a composition of many different polygons. While all polygons will share the same shape, the colors will indicate their role in the game in order to distinguish “holes” in the environment from solid tiles.

## Feature Set

3D rendering of environment
Making the tiles render 3d perception in a still environment
Making sure that each edge of the tunnel is contained within a struct to make implementation of rotation easier 
Implement a continuous environment 
Maintain 3d perception as tiles move relative to the sprite
Calculating how to resize the tiles alongside the changing x coordinates to make it look like the sprite is moving through the tunnel (i.e. the tiles in the background should look like they have moved closer into the foreground)
Implementing keyboard handler 
Space bar means jump
Left arrow key moves player to the left
Right arrow moves player to the right

Make graphics 
Sprite and coins
Random creation of falling tiles
Figure out how to manage multiple tile types and check for collisions specifically with tile types that will potentially result in a loss condition

Generation and collection of coins
Move coins along with tiles
Coins must be randomly generated on stable tiles
When sprite collides with a coin, the coin must disappear

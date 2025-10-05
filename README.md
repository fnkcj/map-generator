# CoDJumper Map Generator

CoDJumper Map Generator, or CJMG for short, is a project aimed at helping with the custom map drought that has faced CoDJumper for quite a long time.
The goal is to create a tool that could generate a wide variety of maps in terms of gameplay, but also aesthetically, in a very short time.
It is not going to be a replacement for handcrafted maps, but instead be a way to have some fun in between of the more major map releases.

For now the project is still under early development and will probably see a large rewrite at some point.
At this stage, I'm not comfortable with sharing the source code yet, but I will publish it once the project reaches a far enough stage.

Until then, I will put out periodic releases of maps I've generated using the tool and put them under the downloads folder.
You have my permission to host these maps on any server and/or include any parts of the map sources into your own maps.

## How it works

Currently the project uses a random number generator to determine most things.
At every point where this happens, you can also set up boundaries of which the random number is selected, or even force it to be a fixed value.

Everything begins by first determining the generation volume. This is an area in the map in which the tool can generate objects into.
This done by a chunk based system, where it first generates a cube, which you are then able to place on a grid, creating an area for the generation.
You can even place special start and end markers to form a linear path and place walls to block and guide the player.

Once the generation area is determined, the tool will generate the objects within it.
These are things like bounces, platforms and lights.
It generates the density of these objects per chunk, and creates the needed prefab imports for them.
Based on the total import count, it generates the prefabs themselves, meaning every import has a unique size, shape and rotation with texturing and for the lights things like radius and intensity are generated.

Finally the worldspawn is generated and the map source files are packaged into a .zip file which you can then extract into your CoD4 directory and compile the map.

Currently setting up a map like `mp_cjmg1` from nothing takes less than 5 minutes with compile times included.

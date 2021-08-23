# MinecraftBiomesDataset

## Description
This is a labeled dataset containing pictures of different types of biomes in Minecraft (beach, birch_forest, dark_forest, dessert, forest, mountains, ocean, plains, swamp) and urls to access the files in this repository. Some images may not be the same size. A potential application is a classifier that tells what biome a player is in from a photo.

## Data Gathering Procedure
Photos are taken between (-7,000, -7,000) and (7,000 7,000). An X and Z were randomly choosen between these points, and the player was teleported to the highest block at those coordinates. The player was assigned a random yaw between 0 and 360 and a pitch between -20 and 20. The client would then check the biome it arrived at. If it was in any of the desired biomes, it would take a picture. Otherwise it would continue teleporting and taking pictures. The biome the player is said to be in is based on the block they are standing on. For example, the photo [biome.minecraft.beach9.png](https://github.com/Exeton/MinecraftBiomesDataset/blob/main/beach/biome.minecraft.beach9.png) contains a jungle, but because the block the player is standing on is in the beach biome, it is labeled as a beach.

## Human labeling performance
A person was shown 50 full size images from the dataset. First, a random class (jungle, forest, etc.) was choosen and then a random image (no duplicates) from that class was shown. Because of different amounts of data for different classes, this is not entierly repersentative of the data. The person was then shown the image and was told what the actual result was after seeing the photo. The person was told the pitch of the photos were between -20,20 and was shown what these angles look like in pratice. Additionally, the person was instructed and shown about phots on the edge of a biome problem.

The person got 43/50 photos correct and improved as the test went on. The key insighits were looking at context of what is around the photo (e.g. even if it was in water, if there are birch trees, it is still likely a birch forest). They also used the depth of the water (e.g. if the player was more than 3 blocks deep) and the color of the water to tell beaches apart from oceans. Additionally, they used the mini map to help them.

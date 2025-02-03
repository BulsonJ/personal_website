---
layout: post
title:  "Near Infinite, Procedural Terrain"
category: project
---
<img src="/assets/images/procedural-terrain/terrain.png" alt="" width="100%" height="500px"/>

In the third year of my university degree, for my dissertation I decided to investigate procedural generation. For my dissertation, I used Unity to create a tool where I could generate terrain procedurally, and then expanded this so that terrain is generated at run-time on a near-infinite level as the user flies around the terrain. I then used this tool to compare two different noise generation algorithms, Perlin Noise and OpenSimplex noise.

<img src="/assets/images/procedural-terrain/terrain-top-down.png" alt="" width="100%" height="500px"/>

The terrain is broken up into chunks. Each chunk is 255 vertices across. The noise to generate the height map has a variety of parameters to control it, and I even layered into two seperate heightmaps. The first height map had larger, more smooth features to shape the overall look of the landscape. Then, a second layer of noise was generated which had a lot of smaller detail. These combined together gave great results.

<img src="/assets/images/procedural-terrain/coordinate-system.png" alt="" class="cover"/>

To create the "infinite" system, I generated chunks on the fly. Chunks only close to the camera were generated and once the player flew far away enough, chunks were automatically hidden. This system also utilised multi-threading to increase the performance. I used multi-threading because chunk generation can be done in parallel instead of generating each one at a time. Each chunk would be sent to a thread where the height map would be calculated. When the thread had finished, the data was processed in a queue by the main thread. 

<img src="/assets/images/procedural-terrain/shader-shading.png" alt="" class="cover"/>

Because the terrain was procedurally generated, I could not texture it before hand. I created a custom shader in Unity that used a variety of textures to add sand, grass, rock etc to the terrain. They are then blended together based on the height of the terrain, and how steep it is. The steepness was calculated using the vertex normals of the terrain mesh to figure out what direction the terrain was facing. 

<img src="/assets/images/procedural-terrain/level-of-detail.png" alt="" class="cover"/>

Chunks also had a level of detail system, so that more chunks could be on screen at one time. Chunks were generated at a specific level of detailed based on how far away they were from the camera. This meant that chunks closer to the camera were higher resolution, and ones that would not be seen much by the player(ones further away) would be in lower resolution.

In the end, I found that OpenSimplexNoise was a lot faster than Perlin Noise. This was tested by monitoring the FPS and the Memory usage of the tool as the camera went in a straight line for 1 minute, and was repeated multiple times to get an average for the runs. However, I also had to test the noise algorithms more specifically, to ensure that other variables or factors were not influencing the testing within the tool. These tests were completed by timing how long they took to generate 100 chunks of noise, and this was repeated 30 times. In both scenarios, OpenSimplexNoise was faster.


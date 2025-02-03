---
layout: post
title:  "First Vulkan Renderer"
category: project
---

![Renderer](/assets/images/vulkan/rendererInitial.png)

Throughout my final year of university I've been heavily involved in Graphics programming. After using OpenGL and GNM in some of my modules, I've decided to create my own Vulkan renderer. Previously, I've built on top of a base level framework provided to me by the University that has already got lots of functionality. However, this time, I would like to add lots of that functionality myself.

My main goals for this project are as such:
- Explore Vulkan and modern graphics API concepts
- Explore more of graphics programming as a whole
- Create my own rendering tool that I can use for learning

Although I would have liked to start from complete scratch, I've never used Vulkan before. To get a base understanding of Vulkan, I followed [Vulkan-tutorial](https://vulkan-tutorial.com/) and [vkguide](https://vkguide.dev/). After working my way through the 5 main chapters of vkguide, I kept the codebase as a base structure to work on. While this means I started my renderer with a small amount of help, I feel that this is the best way for me to gain familiarity with Vulkan, and I plan to refactor some parts once I better understand where I need more control or different abstractions.

Currently, what I've added so far is:
- Phong lighting
- Swapchain recreation (Resizing window)
- Skybox (Cubemap)
- ImGUI
- (Optional) Use of index buffers

I'm planning to continue working on this renderer in my spare time. For my dissertation this year, I want to investigate Hydraulic Erosion, and I'm going to use this Vulkan renderer as part of it.





---
layout: post
title:  "University Graphics"
category: project
---

# Team Project

This module consisted of 8 of us working together to create a game. We had just under 2 months to prototype & then create a game in C++, building on top of our previous modules base code. For this project, I was responsible for building a **High-Level Rendering API** that we could use on PC and PS4 and supporting the rest of the team with any graphics problems.

- Implemented a High-Level Renderer that worked for **OpenGL** & **PS4**
    - Implemented rendering structure that would work across both APIs
    - Ported **shaders** from OpenGL
    - Implemented basic lighting, UI, asset loading, painting mechanic on PS4
- Supported another team member to implement the **painting** gameplay
- Implemented menu flow

<iframe class="large" src="https://www.youtube.com/embed/gx8T80bnTCk?si=uHj4srhI8wh-t61I" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

# Graphics Module
The second module I completed at University was Advanced Graphics for Games. For this module, we initially learnt the basics of rendering and using **OpenGL**, and then we were tasked with creating a graphics scene of a tropical island, and implementing different graphical features to increase the fidelity of the scene.

Before this module, I had no prior experience with a Graphics API at all. I had created shaders before, but I had never learnt anything about a rendering engine, matrices or anything like that, which meant at first it was a real challenge. But, because of how rewarding I found to get things appearing on my screen, I was able to work harder on this module than I have in anything previously.

For the submission for this module, I was able to create a scene that included:
- Forward & Deferred Rendering (Pointlight + Spotlights + Directional light)
- Real-time shadows (Pointlight + Spotlights + Directional light)
- Advanced Water Shader (Refraction + Reflection + Foam)
- Terrain shader (Height & Steepness based texturing)

Unfortunately, I did have some problems with low quality sun shadow & shadows flickering, but I believe with more time I would have been able to fix this, using **Cascaded Shadow Mapping** for the sun shadow instead of a single shadow pass.

From all of my modules at University, this one was my favourite. It was fascinating to learn about how Graphics pipelines actually work and how the games that I play are drawn to the screen. It also opened my eyes to the amount of amazing work that has to take place for such advanced graphics features to be created. Implementing new graphics features was really satisfying, especially once a feature was implemented correctly and you can see the full effects of it.

You can view the scene in a youtube video [here](https://www.youtube.com/watch?v=dZs4oOYhsKM).

<iframe class="large" src="https://www.youtube.com/embed/dZs4oOYhsKM?si=IQ77R_CqBPrNT0_u" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
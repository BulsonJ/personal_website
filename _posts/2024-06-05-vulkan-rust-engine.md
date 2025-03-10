---
layout: post
title:  "Vulkan Rust Game Engine"
category: project
---

<img class="heading_image" src="/assets/images/vulkan/bloom.png" alt=""/>

After my dissertation was finished, I had learnt the basic of Vulkan. I started working on my own renderer and game engine using C++. 
However, I started learning Rust and found many of it's features nice to use, and found the development process very convenient, so I 
decided to switch to using it.

Features:
- Blinn-phong Lighting
- Basic Shadows
- Bloom
- Bindless Rendering
- Particle Systems (2D & 3D)
- egui integration
- Reloadable Shaders

This was the biggest personal project that I have worked on thus far. Initially I was just going to make a Renderer, but pivoted towards making a simple plane game. After getting busier at work, I placed the project on hold, but you can see the results below:

Showcase:
<iframe class="large" src="https://www.youtube.com/embed/YvuSozLz2Ls?si=wz043gpAYrZJz-1z" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

Reloadable Shaders:
<iframe class="large" src="https://www.youtube.com/embed/8ndSdJrnvRk?si=tIP7pyJXoFUndc0L" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

Lighting & Shadows:
<iframe class="large" src="https://www.youtube.com/embed/RwFS4GX6STQ?si=5j57xjiMvAMQiHTk" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

Particles (2D & 3D):
<iframe class="small" src="https://www.youtube.com/embed/d0zJSWPXQaQ?si=_QS3zfPNxDQ3HX7y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
<iframe class="small" src="https://www.youtube.com/embed/IzAv00Y4xRo?si=K3shU0qNRLg70OhN" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

# Overview

My project consists of three parts:
- Game
- Engine
- Graphics Library

## Game
All the game specific logic is handled within this.

**egui integration** is handled at this level and uses the public renderer API to be drawn. Allows for it to be easily removed if not necessary.

## Engine
Contains timing and asset management logic. 

Asset Manager caches off textures and is able to load .gltf files.

## Graphics Library - jb_gfx
Contains all of the rendering logic. 

### Public API
Public API involves returning handles to render resources which the user can pass back into functions that the renderer will use. 
RenderModel is a MeshHandle and a MaterialInstanceHandle with a transform.
A MaterialInstance is diffuse & emissive colours, and optionally textures.
For each Mesh there is one draw command to draw all of the meshes, since currently they all use the same material.

### UI
Public UI interface simply takes in a struct containing vertices and indices, an ImageHandle and a scissor. Needs to be pushed to the Renderer every frame.

### RenderList
**RenderList** abstracts **RenderPass** building away. My **simplified** version of a RenderGraph as the ordering has to be specified by the user.
Attachments and RenderPasses are referred to by String.
DrawCommands are generated for models, particles etc, which are then used in each pass to render them all.

Example code:

{% highlight rust %}
        let forward = list.add_pass(
            "forward",
            RenderPassLayout::default()
                .add_color_attachment("forward", &default_attachment)
                .add_color_attachment("bright", &bright)
                .set_clear_colour([0.0, 0.0, 0.0, 1.0])
                .set_depth_stencil_attachment("depth", &depth)
                .set_depth_stencil_clear(1.0, 0),
        );

        let combine = list.add_pass(
            "combine",
            RenderPassLayout::default()
                .add_color_attachment("output", &default_attachment)
                .add_texture_input("forward")
                .add_texture_input("bloom_vertical")
                .set_clear_colour([0.0, 0.0, 0.0, 1.0]),
        );

        list.set_backbuffer("output");
        list.set_pass_order(&[
            shadow,
            gbuffer,
            deferred_lighting,
            forward,
            bloom_initial,
            bloom_vertical,
            bloom_horizontal,
            bloom_final,
            combine,
            ui,
        ]);

         self.list.run_pass(self.forward, |list, cmd| {
            {
                // Draw particles
            }
        });
{% endhighlight %}

# Bugs
As with all graphics projects, had some interesting bugs along the way:
![bug](/assets/images/vulkan/bug.png)
![bug2](/assets/images/vulkan/bug2.png)
![bug3](/assets/images/vulkan/bug3.png)
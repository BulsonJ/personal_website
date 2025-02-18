---
layout: post
title:  "Rebuilding my Island Scene from University"
category: blog
---

I previously built my [game engine]({% post_url 2024-06-05-vulkan-rust-engine %}) in Rust. 2 years on, I've been using C++ professionally for 3 years now and I feel much more confident in my ability to work the language. Instead of tripping overmyself (and the borrow checker), I've decided to rebuild my graphics projects in C++. My first showcase is to be an Island scene.

<figure>
    <div class="figcontent">
        <div> 
        <img src="/assets/images/posts/2025-02-18-rebuilding-island-scene/horizon-forbidden-west-concept-art.jpg" alt="">
        </div>
     </div>
      <figcaption>
        <p class="figure-title">Horizon Forbidden West Concept Art</p>
        <p>Erik van Helvoirt – Concept Artist – Guerrilla</p>
    </figcaption>
</figure>

# Motivation

Just over 3 years ago, I was at University where I first learnt about graphics. We had to create an island scene using OpenGL and that's what led me on my graphics journey. I thought this rebuild of my code would be a great opportunity to test myself to rebuild that scene(or something akin to it). Vulkan has been a great learning experience but I've found myself on the side of engineering architecture more than any actual scenes to be impressed by. 

# What graphics features will I be implementing?

For the original island scene, I ended up with a deferred renderer that had real-time shadows from light sources(Pointlight + Spotlights + Directional light), a day/night cycle, and terrain & water shaders. 

For this scene, the goals are:
- Instanced rendering
- Deferred rendering
- Water shader (Foam, Refraction, SSR)
- Real-time shadows (Directional w/ CSM + Pointlights. Unsure about spotlights)
- Day/Night cycle
- Foliage (Trees + Grass, probably w/ a wind shader)
- 2D Particles (Campfire?)

# What have I got so far?

Currently, I'm still in the process of piecing what I had back together. So the most impressive thing, instanced rendering! I'm using bindless to simplify descriptor set management.

<figure>
    <div class="figcontent">
        <div> 
        <img src="/assets/images/posts/2025-02-18-rebuilding-island-scene/instanced-rendering.png" alt="">
        </div>
     </div>
      <figcaption>
        <p class="figure-title">Instanced Rendering</p>
    </figcaption>
</figure>

My next steps are to get an island mesh setup, with a simple water plane, then go from there! Hopefully in my next post I'll be able to share more screenshots of something that looks like an island!





---
layout: post
title:  "Rebuilding my Island Scene from University - Part 2"
category: blog
---

<figure>
    <div class="figcontent">
        <div> 
        <img src="/assets/images/posts/2025-02-25-rebuilding-island-scene/screenshot.png" alt="">
        </div>
     </div>
      <figcaption>
        <p class="figure-title">Screenshot</p>
    </figcaption>
</figure>

## Progress

- Instanced drawing
- Materials
    - Terrain shader using height to blend
    - Water shader using depth buffer
- Blinn-phong lighting
- Basic GLTF loading (would not hold up to anything complicated)
- Reverse Depth

## Current Frame Breakdown

<figure>
    <div class="figcontent">
        <div> 
        <img src="/assets/images/posts/2025-02-18-rebuilding-island-scene/instanced-rendering.png" alt="">
        </div>
     </div>
      <figcaption>
        <p class="figure-title">RenderDoc</p>
    </figcaption>
</figure>

Blender isn't my strong point, so the terrain mesh is extremely overkill for what it needs to be. I'll easily be able to save vertices by removing detail from below the sea and finding a better way of creating the mesh as a whole to remove excess vertices in areas of low gradient(where the higher detail in mesh does not add anything)

## What's next?

- Shadows
- Post-processing





---
layout: post
title:  "Enginefall"
category: games
tags:
  - UnrealEngine
  - C++
  - Multi-player
---

<img class="heading_image" src="/assets/images/games/enginefall.jpg" alt=""/>

<hr>

I have been working as a **Gameplay Programmer** on **Enginefall** from April 2025, at Red Rover Interactive.

My responsibilities and work includes:
- Owned and implemented multiple systems. As part of this, handled scoping out the features, giving feedback on design, and iterating on them from player feedback.
- Improved building system; refactored to support prefabs (collections of building pieces), made placing objects easier and refactored build zones to improve UX for design.
- Fixed character collision bugs by refactoring and simplifying how character collision was handled. Implemented a component that managed collision profiles that sorted them by priority.
- Implemented a tech tree system and UI. This supported player or group progression depending on the tech tree. It was able to support large numbers of nodes across multiple pages.
- Created a world marker system which handled data from objects within the game for use on an in-game compass and map. This involved tracking various dynamic and static data sources across the server and client, ensuring that any replication cost was kept to a minimum.
- Refactored how item descriptions worked by implementing a stat system for items, that pulled stats dynamically from the item. This stopped text becoming out of date, improved the workflow as text no longer had to manually be updated, and made it easier to support localisation.
- Supported the programming team with my UI knowledge, offering advice and solutions in addition to preparing and delivering a presentation to give them an overview of UI in Unreal.

<hr>

## Features

### Tech Tree

Enginefall has a Tech Tree system that can be used to research knowledge and upgrades within the game.

I was solely responsible for implementing multiple versions of the front-end UI as the project progressed. I also refactored the initial gameplay system to allow for multiple tech-trees, each of which could store progression individiually or shared across a group of players (players who are a part of the same group train).

<figure>
    <div class="figcontent">
        <div> 
        <img src="/assets/images/games/enginefall/Tech_Tree_1.png" alt="">
        </div>
     </div>
      <figcaption>
        <p class="figure-title">Tech Tree - New Design</p>
    </figcaption>
</figure>

The UI was complex, involving a large canvas upon which nodes could be placed. Lines were dynamically drawn between nodes.

To ensure that the performance of the Tech-Tree was sufficient, I employed multiple tactics:
- Widget pooling - Node widgets were created from a widget pool, allowing for UWidgets to be re-used across multiple tech-tree pages, and to avoid the cost of constructing/destructing these widgets repeatedly.
- Caching of Node Data - Instead of needing to re-construct the tree and the node's state each time the Tech Tree was viewed, I generated the positions of the nodes once, and then cached them off. For their unlock state, this was cached off when any conditions changed, to avoid re-evaluating conditions repeatedly when nothing had changed.

<figure>
    <div class="figcontent">
        <div> 
        <img src="/assets/images/games/enginefall/Tech_Tree_2.png" alt="">
        </div>
     </div>
      <figcaption>
        <p class="figure-title">Tech Tree (Locked)</p>
    </figcaption>
</figure>

<figure>
    <div class="figcontent">
        <div> 
        <img src="/assets/images/games/enginefall/Tech_Tree_3.png" alt="">
        </div>
     </div>
      <figcaption>
        <p class="figure-title">Tech Tree (Unlocked)</p>
    </figcaption>
</figure>

### World Marker System + Compass

I implemented an in-game compass that lived on the HUD. This showed information such as the front/rear of the train, as well as teammates & other points of interest.

The system that provided the information for these points of interest was developed by me. It was made to be used across both the compass and the in-game map which was developed by our UI programmer.

Considerations that needed to be made while developing this were the memory and replication requirements for clients. This meant that I developed ways of tracking objects both statically and dynamically, and both replicated by the server and grabbed locally on the client.

### Character + Skins System

I made multiple improvements to the character system during my time working on Enginefall.

I also worked on the skinning system for weapons + cosmetics, allowing players to choose a skin to craft a weapon with. This meant that we reduced the amount of duplicated gameplay assets within the engine, which had previously caused bugs where gameplay assets that were intended to be simply cosmetic reskins had different behaviour.

### Misc UI

<figure>
    <div class="figcontent">
        <div> 
        <img src="/assets/images/games/enginefall/Weapon_Stats_1.png" alt="">
        </div>
     </div>
      <figcaption>
        <p class="figure-title">Item Stats</p>
    </figcaption>
</figure>

I was reponsible for implementing the item stats display in the game. Previously, our item stats were written as text in the Item Description. This commonly meant that descriptions would end up out of date and show the incorrect information to users.

I implemented the new Item Stats which was pulled dynamically from each item. It also supported weapon attachments which could be shown as modifiers on the stat itself.

<hr>

<iframe class="large" src="https://www.youtube.com/embed/540oOTdSCAg?si=0WdTqXrQjd2-zqMu" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<iframe class="large" src="https://www.youtube.com/embed/B3XN06oUdPs?si=qqx6EUotllpqZcKI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<hr>

<iframe class="small" src="https://store.steampowered.com/widget/2437390/" frameborder="0" width="646" height="190"></iframe>
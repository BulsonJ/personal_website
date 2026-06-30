---
layout: post
title:  "Enginefall"
category: games
---

<img class="heading_image" src="/assets/images/games/enginefall.jpg" alt=""/>

<hr>

I am currently working as a **Gameplay Programmer** on **Enginefall**, starting from April 2025.

<hr>

# Responsibilities

My responsibilities included:
- 

## Tech Tree

Enginefall has a Tech Tree system that can be used to research knowledge and upgrades within the game.

I implemented multiple versions of the front-end UI as the project progressed.

<figure>
    <div class="figcontent">
        <div> 
        <img src="/assets/images/games/enginefall/Tech_Tree_Old_1.png" alt="">
        </div>
     </div>
      <figcaption>
        <p class="figure-title">Tech Tree (Old Design - no longer in-game)</p>
    </figcaption>
</figure>

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

I also worked on the gameplay code for the Tech Tree, including refactoring how our systems were setup to allow for Tech Trees to be shared by multiple players (players who are a part of the same group train) so they could all contribute together.

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


## World Marker System + Compass

I implemented an in-game compass that lived on the HUD. This showed information such as the front/rear of the train, as well as teammates & other points of interest.

The system that provided the information for these points of interest was developed by me. It was made to be used across both the compass and the in-game map which was developed by our UI programmer.

Considerations that needed to be made while developing this were the memory and replication requirements for clients. This meant that I developed ways of tracking objects both statically and dynamically, and both replicated by the server and grabbed locally on the client.

## Character + Skins System

I made multiple improvements to the character system during my time working on Enginefall.

I also worked on the skinning system for weapons + cosmetics, allowing players to choose a skin to craft a weapon with. This meant that we reduced the amount of duplicated gameplay assets within the engine, which had previously caused bugs where gameplay assets that were intended to be simply cosmetic reskins had different behaviour.

## Misc UI

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
+++
author = "Spencer Obsitnik"
date = "2024-07-25"
title = "Cat-er Wilds (The Physics of Outerwilds with a feline friend)"
description = "An accurate(ish) universe"
tags = [
  "dev",
]
categories = [
    "dev",
    "project"
]
+++

I love Outer Wilds.  And I love my cat.  So I combined them.

![outer wilds cat](/images/physics/CatGif.gif)

I started out simply wanting to replicate the gravity simulation in Outer Wilds.  The physics themselves are easy (gravity, acceleration, velocity, etc.).  Making them feel good, where the player feels in control, is hard.

Each object has a mass, which exerts a gravitational force on all other objects in game (with the exception of the sun, so it sits stationary).  Below you can see orbits traced out, along with gravitational force information, velocity, and distance from the orbiting central body.

However everything felt lonely and empty.  So I added my cat that I modeled for a previous project.  It has a rigidbody that also reacts to gravity, and attempts to follow a target beside the player.  Meow.

I'm currently working on a ground controller for the cat, so it can land with the player and explore planets with them.

![outer wilds orbit](/images/physics/orbit.png)

The hard part was alignment.  I took a rather simplistic approach and added trigger colliders to all "landables".  When inside of the collider, the Y up vector of the player aligns against the gravitational force.

In the future, I may try simply using the gravitational force on the player, and aligning with that force when above a certain threshold compared to velocity.  This would allow the player to smack planets with their faces, which is currently unfortunately not possible in my simulation.

![outer wilds orbit](/images/physics/Landing.gif)

All in all the phsyics are fun to both build and live in.  Maybe I'll turn this into a farming sim.

![outer wilds orbit](/images/physics/takeoff.gif)
+++
author = "Spencer Obsitnik"
date = "2017-11-17"
title = "2birds1stone"
description = "As the adage says..."
tags = [
  "dev",
]
categories = [
    "dev",
    "project"
]
+++

![2birds1stone](/images/2birds1stone/biome.gif)

2 Birds 1 Stone is the first game I ever built.

I was intrigued with VR, at the time a relatively new consumer technology.  The idea that your body itself could be the controller, that physical actions you took could be accurately implemented in a game world, stood out to me.

So I started prototyping simple real world actions in the game.  The simplest, and most rewarding action, was throwing.  Something humans have always done, and now can do virtually as well.

The loop is tight and simple: throw rocks at birds, until your rock hits 2 birds in flight (without touching the ground).

I was shocked in playtesting.  My players could not, and would not, put it down.  Some rolled their eyes and huffed at the premise, only to refuse to reliquish the headset, simply because they hadn't hit 2 birds yet.

Some, even after completing the game by leveling up their equipment (basic rock -> sling shot -> pebble shooter -> rock~~et~~ launcher -> meteor shower), continued to play, reverting back to rocks, in order to satisfy their basic human need to bludgeon dual birds with a single rock.

Players simply *wanted* to do it the old-fashioned way, even after technically beating the game using unlocks and powerups.  This was surprising to me.  I thought the loop was hit bird -> get money -> upgrade equipment -> hit even more birds.  But it was really pick up rock -> hit bird -> repeat.

#### Why did this work?
I'm still not entirely sure what was so enticing about the premise.  It had nice feel: burst of feathers on hit, ragdoll birds, nice sound effects.  But players often opted to ignore their unlocked abilities, yearning to beat the game the most difficult way possible.  Below are some ideas on *why*:
- Its in the title!  Player's felt compelled to satisfy the titular requirements of the game
- Personal pride.  
- The loop of picking up/throwing is as fun as it is easy.  There is something very innate in throwing a rock
- The goal *sounds* easy, but is not.  You get a taste of it when you hit 1 bird: its easy.  But it logarithmically scales in difficulty.  Hitting 2 with 1 rock *feels* like it should be possible (and it is!) but its SO hard.  I would say 3 would be impossible if I hadn't seen one singular playtester achieve the feat.

The birds use a simple rigidbody controller.  It took a lot of tweaking and adding some sensors that I wouldn't need in a traditional gravity driven controller, but in the end they came out nicely.  They still bump into things and roll every once in a while, but paired with the art style of the birds, this felt complementary.

![2birds1stone](/images/2birds1stone/birdsflight.gif)

#### Iterative Playtests
I Experimented a lot, and found that even hitting a single bird was difficult when they landed up high in trees alone.  I ended up adding more props lower in the levels where the birds could perch.

In my own playtests, I found this too easy, so I limited the perch probability on these lower objects.

Players didn't struggle as much, but now they only really aimed for the lower birds.  But they were having fun with it, and the rate of hit birds went up, so I had to keep it in.

To balance it, I placed rarer birds up high as well as lowered rock gravity value the higher it got.  This was pretty much unnoticeable from the ground, but helped the rock travel further in it's desired path, making it feel more accurate.
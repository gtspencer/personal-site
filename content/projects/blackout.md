+++
author = "Spencer Obsitnik"
date = "2022-01-14"
title = "Blackout (or Escape the Piano)"
description = "Escape a giant piano before you black out"
tags = [
  "dev",
]
categories = [
    "dev",
    "project"
]
+++

![blackout](/images/blackout/vid.gif)

Blackout is an experimental "game" about escaping a giant piano before your screen entirely blacks out.

It is an exploration into agency, irrationality, and the feeling of not having control.

The game itself feels frustrating and instills an immediate urgency in the player, who has a mere 12 minutes before their screen entirely blacks out.  However, the game becomes more or less unplayable around the 8 minute mark where 2/3rds of the screen is blacked out.

This game is not fun, and is more akin to Bennett Foddy's Getting Over It, but with a morose and helpless twist.

#### Keys
Each key plays a note when you walked over.  Instead of manually assigning a note to each key, I imported 1 audio clip (middle C), and programmatically determined the pitch by the key's position relative to the other keys.  This gave me an ordering of the keys, which I then applied a modulus operation by 12 to (12 keys in the chromatic scale), to get the octave note and the tone (semitone)

![keys](/images/blackout/keys.png)

#### Blackout Mechanic
I experimented the best way to black out the screen.  First I tried quads covering the screen.  But at the pixel level, this would mean tens of thousands of quads, which tanked performance.

I ultimately settled on a custom texture, placed in front of the camera and and standardized to the resolution so all resolutions have the same "number" of pixels.

Then it was as simple as picking a random pixel, and assigning a black color.
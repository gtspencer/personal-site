+++
author = "Spencer Obsitnik"
date = "2023-05-12"
title = "Elevator Simulator"
description = "I love elevators"
tags = [
  "dev",
]
categories = [
    "dev",
    "project"
]
+++

![elevator gif](/images/elevator/elevator.gif)

I have always loved elevator programming, and the small details and differences between the programming in different elevators.  While seemingly identical, a trained eye can notice small differences in how elevators operate.

![elevator](/images/elevator/elevator.png)

But the details are rarely as simple or straightforward as they might seem.  When considering the system, it becomes easy to become overwhelmed with what we optimize for: shorter ride times, shorter wait times, weight/capacity, wear on elevator (i.e. minimizing pathing to preserve physical longevity), etc.  Outside of indentical systems, what makes sense for 1 elevator rarely makes sense for another.  The Burj Khalifa (the tallest building in the world), very likely has different elevator programming than your typical apartment building.  In face they have 57 elevators, including 2 layered elevators, that reach a speed of 10m/s!.

To explore the endless possibilities of elevator programming, I built a simple simulator.  Floors and shafts can be programmatically added and elevators can be configured to optimize for ride time, wait time, or capacity, all while an endless stream of (super dumb) riders flood in and out of the building.

![elevator upgrades](/images/elevator/elevatorupgrades.png)

Some elevator upgrades

What did I learn?  Elevators are *hard*.  One optimization might work for a small crowd (optimized for shorter ride times), but quicky falls apart when large crowds are present (too many people pile up waiting, and all cannot fit on the elevator).

![elevator floors](/images/elevator/allfloors.png)

There are constant trade offs, and a 1 size fits all solution likely does not exist in regards to elevator programming.

I revisit this project every few weeks or so; really anytime I notice an elevator programming snafu and want to internally remedy the design.
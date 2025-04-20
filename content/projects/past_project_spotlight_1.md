+++
author = "Spencer Obsitnik"
date = "2021-08-17"
title = "Flying Blind, a heart-beat sensing game"
description = "A game controlled with the heart"
tags = [
  "game dev",
  "dev",
  "project",
  "spotlight"
]
categories = [
    "dev",
    "project"
]
+++
![Flying blind game photo](/images/flying_blind.PNG)

[Code](https://github.com/gtspencer/flying-blind-heartbeat-sensing-game)

# Design
Flying blind is an experimental VR game where controls are confided to the heart.  Put simply, raise your heartrate to go up, lower your heart rate to go down.

The purpose of this prototype was to incorporate controls that extended beyond the traditional human-computer interaction in game design.

To achieve this, I chose to use off-the-shelf hardware to track a user's heartbeat, which in turn controls the ship they are on.

### Software
The game polls the heart rate monitor at a rate of 3 hz.  At game start, I "calibrate" the sensor by taking the heart rate and computing a [moving average](https://en.wikipedia.org/wiki/Moving_average) across a range of 30 seconds.  This is their "resting" heart rate.  Once the game starts, participants are encouraged to modulate their breathing to raise or lower their heart rate, thus moving the ship to avoid imminent asteroids.

The game quires the user's heart rate, and compares it to the moving average.  If higher, the ship moves up; if lower, the ship floats down.  That heart rate is then fed in to the moving average, making it easier to reverse the direction of the ship if the future.

### Hardware
The heart beat sensing module is comprised of an Arduino, and a [heart rate monitor attachment](https://create.arduino.cc/projecthub/Ingeimaks/diy-heart-rate-sensor-a96e89):
![Arduino heart rate monitor](/images/heart-rate-monitor.jpg)

This connects to the Arduino, which connects to the computer via USB port.
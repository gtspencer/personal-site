+++
author = "Spencer Obsitnik"
date = "2024-11-28"
title = "Personal Dashboard"
description = "personal dashboard"
tags = [
  "dev",
]
categories = [
    "project"
]
+++

When I'm not developing games, I tend to tinker.

![dashboard](/images/dashboard/dashboard.png)

I can't ever get enough monitors.  I found my screen realestate and habits rarely change:
- I sometimes like to have some sort of media on in the background while I'm working on my personal projects
- I always go through the same motions while opening my dev environment
- I'm awful at checking my calendar.

So I sought to solve these miniscule problems with a custom dashboard.

After measuring my space, I landed on [this 7" HDMI touchscreen monitor](https://www.robotshop.com//products/7-capacitive-lcd-touch-screen-hdmi-interface).  I then 3D modeled the case.

![screenholder](/images/dashboard/screenholder.png)

I'll save you the excruciating iteration on this.  Lots of test prints and modifications to squeeze the screen in the thinnest profile possible, which I think I achieved.

![base](/images/dashboard/base.png)

The base was much easier.  Simple cutting a cube at the right angle.

Here is the finished product in it's space (with my calendar blacked out for privacy).  It's turned into the perfect little screen helper, and the interface is extremely customizable (more on that below).

![irl](/images/dashboard/dashboardIRL.jpg)

#### Interface
The interface is a React front end, combined with a simple Extress server backend, and a helper Chrome Extension.  I needed to use a backend and extension for a couple reasons, explained further below.

![dashboard](/images/dashboard/dashboard.png)

I designed it so my calendar is front and center (again blacked out for privacy).  Then I added a few tabs for quick actions.

##### Media
![media](/images/dashboard/Media.png)

Media contains contains quick links to a few streaming sites.

Initially I wanted to wrap the React app in Electron to make it an executable.  However, I ran into CORS and DRM issues when trying to watch streaming sites on the Electron app.  I opted to just keep it in browser.

One big problem I had was navigating back to the home page from media sites.  To solve this, I build a simple Chrome extension.  On all sites that aren't my home page, I display a small "X" in the corner of the screen, which closes the tab, and defaults back to the homepage.

##### Screensaver
![screensaver](/images/dashboard/screensaver.png)

Instead of starring at the stock ticker at the bottom of the screen, I created a screensaver that displays the time in a fun way.

Inspired by [this project](https://github.com/ligurio/litclock), I created a page that displays the current time, but through some literary quote.  Equally functional and fun.

##### Script Runner
![script runner](/images/dashboard/dev.png)

In the Script Runner section, I put some cards to run some programs and scripts I find myself running frequently.  This is why I need the Express backend: the web browser only has limited access to the file system.  So to solve this, I created the server that exposes a few API endpoints and, when called, executes a BAT script to either open my dev environment, or push my repositories to Github.

The Dev card opens up my frequent dev environment.  It will open Unity to my company's game, along with Rider and Visual Studio.

The Git card will automatically push a few repositories to Github.  I have a few repositories I use daily that I usually commit straight to main, so I implemented a quick action for it.  
---
layout: post
title:  "Ported to Unity"
description: "Over the weekend, I ported my game to Unity from C++11. I feel that Unity will let me
iterate more quickly since it provides so much functionality."
date:   2014-04-01 23:27:00
tags: thesis
---
Over the weekend, I ported my game to Unity from C++11. I feel that Unity will let me iterate more
quickly since it provides so much functionality. Scripting new objects will let me iterate more
rapidly on level design, since it usually takes me about a week to add new functionality to my
C++11 engine.

The Unity port already exceeds what I had before and I was able to add paths and signs, which draw
additional arrow indicators to guide the player in special situations.

The Unity editor surpasses the editor I had written for my game, except for the live-updating
Voronoi diagram that helped me visualize which entities would be narrated to the player when they
viewed the world around them.

Here’s a link to an online version of my prototype:
[robertsdionne.github.io/palimpsest](http://robertsdionne.github.io/palimpsest)

You can use a PlayStation 4 gamepad if you have one, or you can use WASD for movement, hold SHIFT to
run, and press SPACE to see things nearby.

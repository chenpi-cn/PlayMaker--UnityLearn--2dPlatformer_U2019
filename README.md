# UnityLearn 2dPlatformer PlayMaker


This is a 100% PlayMaker port of Unity 2d Platformer learning project 

This project is a work in progress:

## Description

you need the following setup:

 - Unity 4.7.1 at least
 - PlayMaker 1.8.1f10
 
 Improvements over the original version:
 
 - Leak with Enemies
 The original script when enemies fall into the water has a memory leak: the enemy GameObject is not destroyed, leading a definite Memory Warning on Mobile devices and a crash.
 
 - No Pooling system
 The original system creates and destroy rockets, enemies and background props, while it runs fine on most modern platforms, it is known that creating and destroying GameObject has a performance impact. This PlayMaker version offers a simple custom Pooling solution (WIP)
 
 - Bad Scene setup
  The original version is not very clean in the way the hierarchy is organised, typically, objects are being created without proper parenting resulting in a very clunky root with constant creation and deletion of object and so it's near impossible to select a GameObject while the scene is running. The PlayMaker version parent all created object so that the initial hierarchy remains as is.
  
 - Old UI
  This PlayMaker version uses the new Unity UI system, so this is an added value to this project as you can see how to integrate the new UI system in a proper project.
    -- Health Bar is following the Player, so this demonstrate important interaction between the 3d world and the UI Canvas.

## BenchMark
This port is published and playable online. It serves as a comparison between a 100% PlayMaker solution and 100% scripted solution. You will find below benchmarks for the web Player, the Mac Application and and the IOS apps build targets.


### 100% PlayMaker WebPlayer

You can play this version [here](http://htmlpreview.github.io/?https://github.com/jeanfabre/PlayMaker--UnityLearn--2dPlatformer/blob/master/Builds/PlayMakerVersion/PlayMakerVersion.html)

#### Stats:

- Average FPS: 52 -> 55
- Memory Total: 74MB  
- Memory allocation: 43MB
- Build Size: 4.67MB


### 100% Scripted WebPlayer

You can play this version [here](http://htmlpreview.github.io/?https://github.com/jeanfabre/PlayMaker--UnityLearn--2dPlatformer/blob/master/Builds/OriginalVersion/OriginalVersion.html)

#### Stats:

- Average FPS: 53 -> 58 
- Memory Total: 75MB  
- Memory allocation: 44MB
- Build Size: 5.00MB

### 100% PlayMaker Mac Application

#### Stats:

- Average FPS: 59
- Memory Total: 46MB  
- Memory allocation: 17MB
- Build Size: 58.5MB

### 100% Scripted Mac Application

#### Stats:

- Average FPS: 59
- Memory Total: 46MB  
- Memory allocation: 18MB
- Build Size: 60.2MB

### 100% PlayMaker IOS ( IOS 8.1 on iPhone 5S)
It's not really playable because of the Inputs and layout, but I made the test just to get some stats from Xcode

#### Stats:

- Average FPS: 29
- Memory Total: 10MB  
- Memory allocation: 9MB
- CPU usage: 21%-75%
- Memory : 79.6MB

### 100% Scripted IOS ( IOS 8.1 on iPhone 5S)
It's not really playable because of the Inputs and layout, but I made the test just to get some stats from Xcode

#### Stats:

- Average FPS: 29
- Memory Total: 10MB  
- Memory allocation: 10MB
- CPU usage: 12%-74%
- Memory : 61.9MB

**Notes:**

Overall, this is very interesting to see that the pure PlayMaker solution doesn't expose any issues or noticeable downside on playability and performances, a 1 or 2 frame difference for the FPS isn't really an issue given that this will vary very much based on the client computer performances. If you have other states numbers, please share so we can get a sense of the variation across different computers. Noticeable, Memory allocation from Xcode debugging shows 10MB more for PlayMaker. It should be expected that more memory is allocated when using big frameWork like PlayMaker.

#### TODOS:
-- The background parallax system needs porting to PlayMaker
-- Add Touch Support
-- Make a Networked version using Photon

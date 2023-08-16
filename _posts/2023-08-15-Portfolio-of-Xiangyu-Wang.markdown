---
layout: post
title: Xiangyu (Marshall) Wang 王翔宇's Portfolio
date: 2023-08-15 21:30:00 +0800
tags: [Portfolio]
---

## Animation

### Motion Matching: Locomotion
- speed switch, stand_turnAngle_startWalking, move_PlantTurn_move, move_to_stop_(with/without turning after the character stands still)
- Postprocessing: FootIK
- Video: [(contact me for the link)]

### Motion Matching: Walk and Stop at Specific Location
- Work in Progress
- Snapping to the target location by interpolation between source and target trajectories
- Video: [Google Drive](https://drive.google.com/file/d/1us_2IxfPBTAmTX5V8aLL2y0QSVVjuaGL/view?usp=sharing)

### Inverse Kinematics (IK): 
- Video Link: [Google drive](https://drive.google.com/file/d/1It2_k7DA8UtzAzpFaDRzye9Er9p10SdZ/view?usp=sharing)
- Linear Blend Skinning / Dual-Quaternion Skinning
- IK solver: Tikhonov Regularization / PseudoInverse
- Implemented sub-step IK to make the results more stable

### Procedure Animation: Spider
- Video Link [Google drive](https://drive.google.com/file/d/1DbfLFHTmC9cwxE82ETHkv4wJ69afxFFI/view?usp=sharing)


## Simulation

### Physical Jello Cube
- Video Link: [Google drive](https://drive.google.com/file/d/1fCHF-EaUfZFT2wyJ1EcJ-t00Tm6Us9jK/view?usp=sharing)
- Simulated by a mass-spring system
- Collision implemented by penalty method
- Cube responses to a time-independent force field and mouse dragging


### 2D Boid Simulation
- [Github](https://github.com/MarshallW906/BoidSimulation2D)

## Serious Game Projects

### Come with Me: a two-player cooperative game set in a puzzle filled magical world.

- USC Games MFA Thesis Project
- [Steam](https://store.steampowered.com/app/1190760/Come_with_Me/)


### Singleless: Local 2-player competitive shooting game

- Developed by Unity3D
- Available on [itch.io](https://marshallwang.itch.io/singleless)
- Gameplay Video: [Google Drive](https://drive.google.com/file/d/1XgDM_vaslNEWP-JfkybN9cUXELBi6SVO/view?usp=sharing)

## Game Engine Course Project

These are things I implemented in Game Engine Dev class (CSCI 522) by myself.

### CPU/GPU Collision check (Performance comparison)

- GPU Code was implemented by OpenGL compute shader
- Many static imrods with obvious overlaps were spawned for collision detection
- Video: [Youtube](https://youtu.be/bcQw3MEv5ts)

### An basic 3D Audio system implemented by XAudio2

- 3D spatial effect
- Videos:
  - Walk sound attached to a soldier, & ambient sound: [Youtube](https://youtu.be/Zggp_4pUJq4)
  - 3D Sound Music: [Youtube](https://youtu.be/NQvsFHRlgW8)

### An animation system with full/partial/additive animation

- Also a basic 3rd-person controller was implemented
- Videos:
  - 3rd person controller with basic actions: [Youtube](https://youtu.be/afH72g8HpFE)
  - Additive animation: [Youtube](https://youtu.be/sf3T9ywaCkg)
  - Partial animation: [Youtube](https://youtu.be/H27tRPsZw9s)

### AABB Bounding volumes & Culling

- A basic culling test using camera view frustum & AABB.
- Video: [Youtube](https://youtu.be/TEKxZajKNAQ)

### A patrol/aim demo

- One soldier patrolling between randomly selected different waypoint
- Another soldier walk to his destination point and then start aim at an imrod.
- Video: [Youtube](https://youtu.be/8mtKkRWi5Jk)


## Game Demo (designed using Construct 2 free version)

### 'Lightning: South Project' Game:

- This game is available on: [Github Page](https://marshallw906.github.io/South_Project_Lightning_WAB/index.html)
- Also available on [itch.io](https://marshallwang.itch.io/southproject)
- Gameplay video: [Youtube](https://youtu.be/jy-Fuco1HXE)
- Design statement: [Github](https://github.com/MarshallW906/South_Project_Lightning_WAB/blob/gh-pages/design-statement.pdf)

### Customized 'Ghost Shooter' Game:

- This game is available on: [Github Page](https://marshallw906.github.io/ConsGame_Task1/index.html)
- Also available on [itch.io](https://marshallwang.itch.io/ghost-shooter-customized-by-marshall)
- Gameplay video: [Youtube](https://youtu.be/scAq3yZwkeM)
- Design Statement: [Github](https://github.com/MarshallW906/ConsGame_Task1/blob/gh-pages/README.md)


---
title: "Sudokrazy: Videogame"
description: "Sudoku game with 'krazy' shuffle mode"
repo: https://github.com/Aura4G/sudokrazy
tags: ["Videogame", "C++", "OpenGL", "SFML"]
---

## What's Sudokrazy?

Sudokrazy is a **sudoku game written in C++,** using the Simple Fast Multimedia Library (SFML) as the API for which I present onscreen elements.

The videogame is currently unfinished, with my most recent commit coming from a dated September 2025... I hope to complete it this summer though! Not a whole lot is left to do, really.

In its current state, Sudokrazy boasts:

- Difficulty options (Easy, medium and hard), they are unlockable
- Settings menu with music, brightness and contrast settings
- Krazy mode: The board shuffles to a completely new solution every 5 inputs
- Score system
- Earnable "kuukies" currency (sounds like cookies)
- The prototype for a item shop

Sudokrazy boasts colourful graphics, and the **krazy mode:** every 5 turns, the 9x9 grid shuffles: the quantity of each number is kept the same, including your own inputs, but all in different places, making you explore an entirely different solution! You thought you were on the right path to solving the grid? Now all your inputs are muddled, including the ones you may have gotten wrong! It's designed to be teensy bit mean to the player, especially since incorrect moves aren't shown in this mode!

## Why Sudokrazy?

Man **I hate mobile sudoku games.** Ads every minute it feels like. So I wanted to just be able to play sudoku games with colourful graphics repeatedly **without interruption.** I started making the background logic on a train home, and then got to messing around with SFML for the first time on a flight later that week. That's right! **The first 5-6 hours of development on this game were spent on the move.**

This project really reignited my joy I have programming in C++, probably the language I can vouch for the most. What's more is how my existing knowledge of C++ and the quick understanding I gained of SFML made it to where, in the year of 2025 where things were being vibe-coded out the woodwork, I was not. **This passion project was made with no interference from GenAI whatsoever.** So I hope to continue that trend when I pick this thing back up.

Development started on WSL, then I shifted to native windows with the gcc compiler via MinGW64 as there were issues on WSL regarding music and the screen freezing for some reason.

## SFML

First created in 2007, SFML is a cross-platform multimedia library. It provides access to windowing, audio, graphics and networking; these all make up classes within the library, and it definitely eased the transition between the C++ terminal logic I made and the product Sudokrazy has fleshed itself out to be in its current state. SDL is more common, sure, but I grew very fond of SFML quickly as I learnt more about it. It had everything I needed to make sudokrazy possible, and then some!

But that's where the help ends. The rest of it? DIY, chief. You have to make buttons yourself. SFML is object-oriented, so classes you make that wrap screen elements SFML helps draw can be wrapped within other classes that have different functionality. Oh gosh, the joy of figuring out how to make a settings slider class using a button class I had made previously will never be beaten I fear.

It was also fun getting to play around with **GLSL,** the scripting language that interacts with the OpenGL API. This was how I'd allow for future players to change brightness and contrast settings: by having the coefficient on the corresponding slider multiply by a constant value in the GLSL script. The settings save to a local file too. The problem I quickly picked up from using GLSL in conjunction with SFML is that the latter responds best to older GLSL syntax; using updated syntax caused the game's display to freak out, a problem with the only solution I found being to stick to older syntax, and just use frag shaders to change brightness and contrast.

## What's left?

Honestly there's not a whole lot left to do. I dusted off the **trello board** from a year ago just now to peep what's left. And my prospects are looking good it seems!

- Pencil function
- Visual events (e.g. an animation that plays every time the board shuffles in krazy mode)
- Sound effects (along with sfx volume in settings)
- Purchaseable hints in the item shop
- Purchaseable background themes in the item shop (I'll hand-draw these)
- New music potentially? **Can put the MPK mini I got to good use hehehe**

I see bright things for the future of sudokrazy! Maybe it'll a cheap or free lil bit of fun you can get on itch.io or something. But for now, muse at the repo!

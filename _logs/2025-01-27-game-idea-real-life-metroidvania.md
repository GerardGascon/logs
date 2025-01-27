---
layout: log
title: "Game Idea: Real Life Metroidvania"
subtitle: "A game that is played by moving across a building."
version: 0.1
toc: true
---

## Idea

The idea of this video game is to hide some devices across a building and a person needs to find them in a certain order
or something like that, similar to an average metroidvania game but a lot smaller.

## Execution

![Arduino](/assets/images/posts/metroidvania-arduino.png)
_A drawing of an Arduino device with two keys on top, one for reading pulses and one for sending them._

This device would work as if it was a sonar for submarines or something like that.

I'll try explaining the gameplay flow in order to try explaining it in a much clearer way:

- A player starts at a central computer creating their own "morse code signature" and read some introductory dialogues.
  - This step is crucial as this "signature" is what will distinguish players.
- Then they start seeing clues to find other pieces of the submarine or things like that across the building.
- In each of those places, there will be a "sonar" a.k.a. the Arduino from the picture connected to the local Wi-Fi.
- When they find the Arduino, they have to play their signature in order to mark them as found, and maybe a QR code to 
scan and continue the story.
  - Of course, there will be several ways to check if a code is correct, probably a piezo with some sounds to indicate 
  if the player has done it correctly.
- They need to find all of them.

## Limitations

As you can see, it isn't designed in its entirety, but it's a small idea of a device that I've had in my head for a 
while but didn't know what gameplay could suit on that.

There are quite a lot of limitations, like cost and difficulty to enable people outside of that event to be able to play
this game, but at the same time is the charm that alt.ctrl games have.

I don't know if I'll end up turning this into reality, but at least is a fun idea I had yesterday.

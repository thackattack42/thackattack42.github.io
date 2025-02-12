---
title: "Ascendants 2099"
excerpt: "A fast-paced arena FPS game set in the year 2099. Cyberpunk androids are trying to control humans while Solarpunk soldiers are trying to take down the android regime. <br/><img src='/images/Ascendants-light-blue-with-glow.webp'>"
collection: portfolio
---

[![Alpha Gameplay](https://markdown-videos-api.jorgenkh.no/url?url=https%3A%2F%2Fyoutu.be%2FFyOAyGaxZUE)](https://youtu.be/FyOAyGaxZUE)

- Platform: PC
- Engine: Unreal Engine 5.4
- Duration: May 2024 - October 2024
- Team Size: 8-10
- Role: Lead Programmer, Weapon Mechanics, Movement Mechanics

## Responsibilities

- Helped design and implement smooth movement mechanics such as sliding, wall running, mantling and more to create a fun way for the player to navigate the levels using state machines, anim graphs, and blueprints.
- Implemented weapon mechanics using a pre-built system and adapted it to work with our character by using IK rigs to lock the left hand to the gun and implementing dynamic recoil that is fully adjustable.
- Assisted in creating the "gameloop" and how to make the game fun by implementing an oxygen system, abilities system, and various gamemodes.

## Movement Mechanics

The first topic I'm going to be explaining is Ascendants 2099's movement system and how we implemented it. The goal was to create fun, fluid movement mechanics that enhanced the user's gameplay and made traversing the maps unique. The biggest inspiration
for the movement was games like Titanfall that have dynamic movement to allow players the freedom to move around in a way unique to them. Some of the biggest challenges we faced were figuring out how to implement wall running and sliding in a smooth and dynamic way.

### Wall Running

Wall running was the first big hurdle that we needed to figure out since we believed it was the most complex and also one of the central mechanics we wanted implemented. We started by doing research into how other games like Titanfall had implemented wall running. We came across a few YouTube tutorials on how it was done but none of it was exactly what we were looking for. I ended up finding a project on GitHub that had a lot of the functionality we were looking for so what I decided to do was import most of the code and then change different parts of it to fit closer to our vision of how we wanted it to function. After testing out the imported mechanics, we identified what needed to be tweaked such as the duration of the wall run, being able to jump off a wall onto another and continue running, being able to mantle shorter walls and obstacles, and many other changes were made to customize the code to fit our game. After making the necessary changes, we finally had a wall run we were happy with and could then move on to other movement mechanics.

### Sliding

The next mechanic we wanted to include was the ability to slide behind cover, under gaps, and anywhere else you can think of to give you an edge in gun fights. Sliding was much easier to figure out compared to wall running since we already had crouching and sprinting functionality so we basically just had to combine the two to create a slide. The biggest thing I wanted to figure out was getting the player to slow down over the duration of the slide so it looked a bit more realistic. The way I was able to achieve this was by using a simple timeline that interpolated the player's speed over the duration of the slide until it reached the speed we wanted.

## Weapon Mechanics

The next major gameplay system we needed to add was our weapon mechanics. This was by far the most complex and time-comsuming system we implemented. We ended up reiterating and refactoring the weapon system at least 3 or 4 times before we finally got it to a place we were happy with. I started with a simple two-weapon system using an array of weapon objects that allowed the player to switch between the primary and secondary weapon with input from the user. After that we added more variables to the weapon objects to make each weapon more unique by being able to adjust magazine size, recoil, fire type, etc. Now that we had the weapons set up, we needed them to actually fire. To accomplish this, we originally tried using a line trace from a socket on the barrel of the weapon but found out that unless the weapon was placed perfectly in the player's hand, the bullets would eventually veer off of where the player was aiming. So instead of spenidng a ton of time perfectly placing each weapon socket on the players hands, we decided to have the line trace come out of the first-person camera since it was already looking straight in the direction we wanted the bullet to fire. 



<video src="" controls="controls" style="max-width: 730px;">
</video>



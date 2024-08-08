# Portfolio

## Games

### Undisclosed Game

Set in a dystopian future where AI androids and human cyborgs coexist, this futuristic multiplayer first-person shooter promises to bring back the essence of organic gaming. We’re committed to returning gaming to its roots with immersive gameplay, rich storytelling, and a focus on pure, unadulterated fun. Join us as we blend cutting-edge technology with nostalgic elements to create a gaming experience like no other.

Platform | PC      
Engine | Unreal Engine 5      
Duration | April 2024 - Current      
Role | Lead Gameplay Programmer & C++ Developer 

### Responsibilities

- Responsible for designing and implementing movement mechanics, weapon mechanics including weapon pickups, attaching to player, weapon inventory, and shooting mechanics.
- Assisted in setting up Animation Blueprints utilizing custom animations
- Generalist programmer assisting other members with whatever tasks need the most attention

### Combat/Weapon Mechanics

One of the biggest early challenges was figuring out a system to be able to store all of the player's weapons and swap between them so they can use the correct weapon for whatever situation they find themselves in. My first thought was to use a data structure to hold the data for all the weapons and store them on the player themselves, which is what I ended up going with by adding the weapons to a map that the player has access to I also created Enumerators that we can add all of the weapons to stored information about the weapon on the weapon itself that the player then had access to when they equipped the weapon. 


![Weapons](https://github.com/user-attachments/assets/33f3bcad-27ae-4a51-8ebb-41af7c38428d)


Now that the player could store all these weapons, how would they access them? How would they switch their current weapon, whether that be from one in their inventory or another on the ground from a defeated enemy? The hardest part would be picking up other weapons, so I tackled that problem first. The way I was able to get this to work ended up being much simpler than I originally thought, however. All I simply had to do was create an actor that can be picked up by the player, and assign is a class reference to the weapon base I made for the weapons. Since the weapons themselves store all the information the player needs, all I need to do is get the name of the weapon in the pickup and add it to the player's weapons map.


![weapons pick](https://github.com/user-attachments/assets/61182b21-5b90-402d-8d68-5edc64f3498e)


Lastly, I setup being able to swap weapons which was very simple; press a key to access a weapon by type (primary, secondary, grenades, etc.), set it as the current weapon, and hide the other weapon. And what  That gets me is a system that I can swap between weapons with ease.


https://github.com/user-attachments/assets/7cb6593c-056d-4d17-9eb7-106e5a85b2d5


 ### Movement Mechanics

 Movement mechanics are, to me, one of the most importanat distinguishing factors of arena FPS games. Good movement mechanics make the gameplay enjoyable and rewards higher skilled players while not completely overwhelming casual players. As of now, are movement mechanics are still being developed but our goal is to make movement fun and unique for everyone to enjoy. But before I got to the fun stuff, I had to setup the basics. I started with sprinting which was simple enough; increase the player's speed when holding the shift button and set it back to the original when the sprint button is released. Next I went to crouching, which I thought would be just as simple. While Unreal has built in crouch functionality, in my opinion its a bit lacking. The crouch and uncrouch is snappy and instantaneous and doesnt feel very natural. So what I ended up doing is using a timeline and linerar interpolation to smoothly transition the player from standing to crouching and back again and the result is a much more natural crouch.


https://github.com/user-attachments/assets/62b85dce-4a3b-4934-9dd1-c6e6d4a8d492


After I got crouching working, I wanted to setup a slide for when the player presses crouch while they're sprinting. This was a nother one of the mechanics I thought would be pretty tough but ended up being easier than I thought. I setup a branch in the crouch function to see if the player was sprinting or not and then I basically did the same thing I did with crouch except I didn't reduce the players speed quite as much and played a sliding animation instead of the crouch. Visually it looks like the player is sliding but in reality they are just crouching but moving faster than a standard crouch. At the end of the sliding animaiton, the player then gets set to be crouching and slows down to normal crouching speed.
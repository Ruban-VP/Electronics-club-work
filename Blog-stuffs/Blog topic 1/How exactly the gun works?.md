# How exactly the gun works: Fun engineering behind

In order to know how the gun works, let us first analyse what the gaming system must do:

1. First, the user must be provided by a trigger to take a shot at the duck. This is quite intuitive and the gun's physical trigger itself acts as the electronic trigger.

2. Second, there must be a locating mechanism by the gaming system to know whether the user has correctly aimed at the duck or not.

__Actual working:__
So basically the gun contains a photodiode whose resistance changes based on the intensity and color of light falling on it. Whenever the gun's trigger is pressed, the system makes the whole TV screen black for a frame and in the immediate next frame it only changes the spot which the duck occupied at the time shot was taken as white. The remaining screen will remain black. So if the user has aimed correctly, the transition will be captured by the photodiode and hence, the system will perceive it as a correct hit.

If not aimed correctly, transition won't happen and hence the system will perceive it as a wrong aim and hence, the dog will laugh at you. The reason why the screen is made black for a frame is because this will allow the gun to get accustomed with the black screen for a frame. This eliminates the possibility of wrong transitions happening due to the room's lighting conditions.

![img](https://github.com/Ruban-VP/Blog-stuffs/blob/master/Blog%20topic%201/Duck_Hunt_in_slow_mo%20(1).gif)

All these happens within milliseconds and hence cheating is not possible (Thanks to the high transmission speed of electrical signals).

To know why they aren't currently in the market, proceed to this link: [Why this game is currently isn't in market?](https://github.com/Ruban-VP/Blog-stuffs/blob/master/Blog%20topic%201/Why%20this%20game%20is%20currently%20isn't%20in%20market%3F.md)

## References:

Link explaining the working of the NES zapper gun: [How the NES zapper gun works?](https://www.thrillist.com/news/nation/how-does-the-duck-hunt-gun-work-nintendo)

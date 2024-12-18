# TweenService
TweenService is about smooth transitions. Instead of linearly changing position, size, transparency, etc., you can do these changes more smoothly over periods of time.

## Initializing TweenService
Initializing TweenService is pretty much the exact same as intiializing every other service:
```lua
local tweenService = game:GetService("TweenService")
```
Using TweenService, however, is an entire other story.

## Using TweenService
TweenService comes in 2 main parts:
1. Tween Information
2. Creation and Usage

The more complicated part is the Tween information, which I'll elaborate on below.

### Tween Information
To create a tween, first you need to give it its basic information. These are then stored in either a variable, or directly within the Tween. For this example, I'll use a variable:
```lua
local tweenInfo
```
We've initialized the variable, however it has to value. A TweenInfo is it's own type, so it has its own special call:
```lua
local tweenInfo = TweenInfo.new()
```
To create TweenInfo, you don't actually need to initialize TweenService. To play a tween, however, you do need to initialize TweenService. This is generally pretty stupid, but it's the way luau works, so we'll work with it.

Inside the TweenInfo we need multiple parametres:
```lua
local tweenInfo = TweenInfo.new(
  1, -- length (in seconds)
  Enum.EasingStyle.Linear, -- The easing style, the curve shape
  Enum.EasingDirection.In, -- The easing direction, also relates to curve shape
  0, -- amt of times tween plays
  false,  -- does the tween play in reverse
)
```
That's an example of the parametres you could use.

### Easing Curves
Here are visual examples of easing curves. Roblox Studio will allow you about 16 of them - from memory - however you should be using the one that fits best to whatever you need it for.
<img src="https://radialglo.github.io/images/easings.png" alt="Understanding the Intuition of Easing - Anthony Su"/>

<sub>thank you Anthony Su for having this on github so I can use it for my tutorial</sub>

### Creation and Usage
This is the easier part. To create a tween, we create new variable - a Tween variable - and from there we can play it.
```lua
local tween = tweenService:Create()
```
Now, even though we've created a tween, it has no information in it. This tween, it functionally does nothing right now. To make the tween do anything, we need to give it some parametres.<sup>[1]</sup>
```lua
local tween = tweenService:Create(
  part,    -- the object you're tweening
  tweenInfo, -- the tweeninfo from before, you can also just use the information from the tweeninfo here instead of using a variable
  {Position = (0, 0, 0)}, -- the property you're changing, and the values you're setting it to
)
```
Position isn't actually the only property you can tween. You can tween every property with a numeric value using TweenService - however you should experiment and test multiple times throughout the process for the best tween for your situation.

Playing tweens are even easier. You just do this:
```lua
tween:Play()
```
You can also pause tweens like this:
```lua
tween:Pause()
```
There are other things you might want to do, and for extended clarification, check out the Devforum and official documentation.

### Extra Notes
<sup>[1]</sup>That's not how you're supposed to write a position tween - I don't actually remember how they're supposed to be written. That version is just simplified for tutorial's sake.

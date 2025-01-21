# RunService
RunService is very helpful, giving you some very nice, optimized options for time-management within projects.

## Initializing RunService
Initializing RunService is as simple as initializing every other service, adding it in as a variable:
```lua
local runService = game:GetService("RunService")
```
## Time Management With Run Service
RunService, as said before, provides some nice connections you can use for time-management within your project. An example of this is .Heartbeat:
```lua
runService.Heartbeat:Connect(function()

end)
```
Heartbeat runs after every frame, meaning a couple things:
- it sits a frame behind the player
- it operates at a variable frequency
If you're running a .Heartbeat function on the server - yes you can do this - it'll be variable to the servers FPS (frames per second). Otherwise, if it's run on the client, the connection will be called after every single frame your device renders. It's much preferable over a while loop, because of computer optimization that I myself am too tired to get into.

Another thing you can is use .RenderStepped. RenderStepped runs opposite to Heartbeat, instead running before every frame, rather than after. There is one major difference between .RenderStepped and .Heartbeat though, which is who can use it. The server's unable to use .RenderStepped, and this is because the server is the one that's handling the frames first, and then sends that information to the clients after.<sup>[1]</sup>

.RenderStepped can be called in essentially the same way, just with a little change in wording:
```lua
runService.RenderStepped:Connect(function())
           ^^^^^^^^^^^^^
end
```

## isStudio
isStudio is, as the name implies, a function that lets you check if you're running the game in studio. It's generally a nice feature, you can attach it to an if-else, variable, whatever.

# UserInputService
UserInputService is a service that allows you to detect keystrokes, clicks, and the device the player is on. Even though you can still use buttons to detect clicks, it won't tell you any information about where the player kicked, nor will it tell you anything about the device a player may be on.

## Initializing UserInputService
Initializing UserInputService is functionally the same as initializing any other service, where you attach it to a variable within a script<sup>[2]</sup>:
```lua
local uis = game:GetService("UserInputService")
```

## Detecting Inputs
UIS (UserInputService) is commonly used to detect keystroke inputs and for raycasts. Using raycasts is much more complicated - worthy of its own page - so I'll only cover using it to detect keystrokes here.

The first thing we need to do is connect it to an InputBegan:
```lua
uis.InputBegan:Connect()
```
An InputBegan tells you when any sort of input has started - like typing out a letter on your keyboard. You'll likely be connecting these to function, which you can do by either putting it inside the connection, or by creating a function that's linked directly:
```lua
-- use an existing function
uis.InputBegan:Connect(myFunction)
                       ^^^^^^^^^^

-- create a new function exclusively for use here
uis.InputBegan:Connect(function()

end)
```
.InputBegan actually gives you information on what was done - so you actually do know what key was pressed. To access that information, however, you have to use a parametre:
```lua
:Connect(function(keyPressed)
                  ^^^^^^^^^^
end)
```
Keyboard things are considered Enum objects - a data type which in Roblox Studio, contains things that you'll be using alot. To check the key pressed, we can compare the parametre we got to the corresponding enum object:
```lua
    if keyPressed == Enum.KeyCode.Q then
        print("Key Q pressed")
    end
```
In the above example, if the key pressed was Q, it'd print that to console. You can do this with pretty much every key Roblox will support - so allow autocomplete to help you out a little bit.. Sometimes atleast. Please do not use the Roblox AI Assistant.

### Extra Notes
<sup>[1]</sup> This is likely inaccurate. <br>
<sup>[2]</sup> I believe UIS only works in LocalScripts - making it a client-side service exclusively.

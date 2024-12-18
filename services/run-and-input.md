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

### Extra Notes
<sup>[1]</sup>This might be innacurate.

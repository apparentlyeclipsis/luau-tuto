# Variables
Variables are generally one of the most important parts of your project. You use them to make your code more readable, to store values, among other things I'm admittedly too tired to name.

Now, if you've read the entire syntax file - you might not need this page, except for clarifications on linking these to instances. Luau is centered around OOP, controlling objects within set 2D and 3D workspaces.

## Inside Instances
In Luau, you'll likely be using your variables to control instances, and values assigned to them. Linking a variable to an instance is simple, however it's also heavily dependent on how you're organizing your scripts, among other instances. The most common way you'll see these handled - especially with items taken from the Creator Marketplace - is hiding the scripts within the part.

This uses Roblox Studio's ancestry tree - which could look like as follows:

<img src="https://devforum-uploads.s3.dualstack.us-east-2.amazonaws.com/uploads/optimized/4X/3/0/5/305521a57324178e4ce89d567a43824ebbb6662d_2_372x500.png" alt="Filter instance by class - Explorer update - Studio Features - Developer  Forum | Roblox"/>

<sup> thank you, developer forum </sup>

Anyway, if you're putting your scripts inside an instance like how that tree does - every 'child' is indented a level deeper than their parent. To call a parent through script, you'd do this:
```lua
script.Parent
```
You can either directly connect this to a call, through things like ".Touched" and ".Changed", or put them through as a variable first, which would look like this:
```lua
local parent = script.Parent
```
You can connect to function calls in both ways, like this:
```lua
-- without declaring the parent as a variable:
script.Parent.Touched:Connect()

-- after declaring the parent as a variable:
local parent = script.Parent
parent.Touched:Connect()
```
Studio's autocomplete will fill in any calls you can use to connect instances to functions - provided 2 things:
1. it knows what class the instance is of
2. the instance actually exists - and this means a couple of things

For the instance to exist, when it's seen in-game, it needs to match ancestry with what's been declared in the script, and it needs to match names with whatever you've told studio when you stored it.
If you want studio to autocomplete methods based on it, you can 'force' - or more accurately, 'assume' classes onto variables within your scripts. To do this, when declaring a variable for the first time, add its class name behind a colon. In your script, that'll look like this:
```lua
-- with spaces for readability
local part : Part = script.Parent

-- without spaces inbetween for you faster people
local part:Part=script.Parent
```
Studio actually autocompletes class names as well, provided you're handling them correctly. It's generally recommended to keep your code readable, so usually - if you see these types of assumptions, they'll have spaces inbetween making them easier to read.

## Outside Instances
A majority of the time, instead of handling your scripts through parenting them to whatever part they apply you, you'll be handling them through other means - namely the server, or client storage. The main benefit of doing this is that it's much easier to update code for all the instaces it applies to, so you don't have to go back and forth to update code in tens, hundreds, maybe thousands of parts.

This leads us to initializing services within our scripts, which can be done like this:
```lua
-- through "GetService"
local ServerStorage = game:GetService("ServerStorage")

-- through child-finding
local ServerStorage = game.ServerStorage
```
You can do either with pretty much every service, and it generally won't matter which way you're doing it. By using ServerStorage, we can access items stored within the server, however only if the script is only being accessed by the server. The general client is unable to access ServerStorage, and ServerScriptService by default, which makes them safer options for storing important information, because the client won't be able to access them.

To contrast that, theres ReplicatedStorage and ReplicatedFirst. You can get a list of the more important, common ones [here](https://devforum.roblox.com/t/important-services-to-know/1345575). For descriptions, Roblox's documentation is usually enough - except for DatastoreService.

If you want to get an object from anywhere, while also keeping an original copy, the :Clone() connection is quite useful. Using it is commonly handled like this:
```lua
local object = workspace.Model
local clone = object:Clone()
```
It's very important to note that cloning an object doesn't actually parent it to anything - which is really important, because otherwise it exists nowhere. To give an object a parent, or change any of its properties, you'd do something like this:
```lua
clone.Parent = workspace
-- changes the clone's parent to workspace
clone.Transparency = 1
-- sets the clone's transparency to 1 - or 100%
```
These will be more expanded on in other sections, because this section is about variables, not properties, although both are correlated.

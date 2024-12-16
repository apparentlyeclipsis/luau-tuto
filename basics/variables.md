Initializing variables is as simple as this:
```lua
local var
```
You aren't actually required to initialize a variable with a value, unlike some other programming languages. In luau, you can use variables to store pretty much anything, from instances, numbers, strings, and booleans. Examples of all are as follows:
```lua
-- an example of using a variable to store a number
local var = 1

-- an example of using a variable to store a string
local var = "string"

-- an example of using a variable to store an instance, assuming the instance parents the script.
local var = script.Parent
```
Using variables to store instances could quickly get complicated, however its likely the way you'll be using them most often. You can find instances through script variables in multiple different ways, the easiest example being like what we did above, having the instance be the script's parent.

Variables in luau have method autocompletion, assuming the script can figure out what the class of the instance* is. Method calls can be done as follows:
```lua
-- assuming 'var' is representing a generic part,
local var = script.Parent

var.Touched:Connect()
--  ^^^^^^^
```
Assuming the instance 'var' is linked to is just a part - you can autocomplete tons of methods. Most commonly, you'll see these linked to .Touched events, which run when the instance is touched by any other. One of the most important things in luau are functions - however I won't talk about those within this file.

Another example of a method you'll commonly be calling is .Changed:
```lua
var.Changed -- changed represents when a value, within the objects information window, is changed.
```
.Changed is fired when any property of the instance is changed, ranging from name, to material, to transparency. You can get the new value of the property by calling a function after recieving this call, as can be seen below.
```lua
local var = script.Parent

var.Changed:Connect(function(value)
                             ^^^^^
end)
```
This value can be used in any way, however usually when you're using this call, you're only looking for a change in one specific value. Assuming you have this structure for multiple different properties on the same instance, you can use :GetPropertyChangedSignal(), which functions in about the same way. Connections and functions will be expanded on in different sections.

-# *Instances will be expanded on in other sections.

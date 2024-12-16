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
Using variables to store instances could quickly get complicated, however its likely the way you'll be using them most often.

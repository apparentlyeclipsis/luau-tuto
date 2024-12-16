# Conditions
Conditional statements are around the most basic parts of a program. They can split apart the flows of a program, or create detours within it, and allow you extensive control over your program's function.

Conditional statements in lua, or if statements, would look like this:
```lua
if (condition) then
  -- things that happen if the condition is true here
end
```
Anything inside that chunk will only run if the condition required is fulfilled - the value of it is 'true'.
You can do this for as many conditions as you want, and to seperate you'd use an 'elseif'
```lua
if (condition) then
  -- things that happen if the condition is true here
elseif (other condition) then
  -- things that happen if the other condition is true here
end
```
If you want a response for if none of the above conditions are true, you can just use an 'else'.
```lua
if (condition) then
  -- things that happen if the condition is true here
else
  -- things that happen if the condition is false here
end
```

# Conditional Statements
Conditional statements are things like if-else statements, your while loops, among other things. A common example of using them is to seperate your program off into different branches.

## If-else statements
An if else statement is simply a branch off, or can be used to check for specific cases. An example is as follows:
```lua
local variable = 7

if variable > 7 then
  print("number is greater than 7")
end

-- example output:
-->
```
In this example, you get nothing logged to console, because the variable isn't larger than 7. If we want to have it log if its LESS than seven, we can either use another if statement - like this:
```lua
if variable < 7 then
  print("number is less than 7")
end
```
That's one way to go around it, but realistically, that looks stupid and someone would get angry at you. Instead, we introduce the else-if. To add an elseif, you're realistically just adding another if to your already existing one, however first it checks if the first one is not true.
```lua
if variable > 7 then
  print("number larger than 7")
elseif variable < 7 then
  print("number smaller than 7")
end
```
Now although we have the same problem as before - where it's not logging anything if you gave it a 7 - you ARE doing the same thing as just using 2 if statements, but its a) cleaner, and b) shorter compared to just using 2 if statements.

Finally, what if we have other things we didn't count for? What if they put a 7 in? Then we use an 'else' statement. After every if, else-if, you can end off with an else. With the same chunk as before, we can do this:
```lua
if variable > 7 then
  print("variable is larger than 7")
elseif variable < 7 then
  print("variable is smaller than 7")
else
  print("variable is 7")
end
```

## While Loops
A while loop is a loop that runs until a condition is met. An example is you here, reading this page until you reach the end. If I were to visual that, it would look like this:
```lua
while reachedEnd == false do
  readThisPage
end
```
Another way you can do this in Luau is to use the repeat-until. It functions the exact same way, just written differently:
```lua
repeat
  readThisPage
until reachedEnd
```
Both of these will be expanded on with the loops page, because this is the conditional statements page, so I'm supposed to talk about those.

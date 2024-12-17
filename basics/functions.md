# Functions
Arguably the most important thing in any project is the function. These things make so much stuff more convenient - both readability-wise, and bug-fixing-wise. Creating functions is relatively simple, where you simply use the function keyword, name your function, and continue.
```lua
function myFunction()

end
```
Now, calling a function is even easier, because you just write the function's name below, whenever you need it.
```lua
myFunction()
```
Generally, you want to name your functions to tell you what they're doing, like this:
```lua
function addTwo()
  number += 2
end
```
<sub> please do not write functions like this, this is just for the sake of the 'tutorial' </sub>
"addTwo" is a meaningful function name, which also directly tells you the purpose of the function. Most of your functions should be named while giving you clear insight into what they do.

## Returning Functions
Above was an example of a void function<sup>[1]</sup>. Returning functions are generally similar, however they 'return' - haha get it - things back to the main program. Here's an example, using the same addTwo function from before:
```lua
function addTwo()
  return number + 2
end
```
We can attach a retun function to a variable, or conditional statement, as follows:
```lua
local number = 5
local variable = addTwo()
print(variable)

--> 7

if number + 2 == addTwo() then
  print("true")
end

--> true
```

## Parametres
Most commonly, your functions will be running with some sort of input. You shouldn't be dragging global variables<sup>[2]</sup> into random functions. Adding a parametre is very simple, and looks something like this:
```lua
function myFunction(myParametre)
                    ^^^^^^^^^^^
end
```
Realistically, you could add as many parametres as you want, but past 3, 4 at worst, it looks really messy, excessive, and generally stupid. By using a parametre, we can take in modular values, while also keeping temporary ones that might be needed local to their own function. Let's do the 'addTwo' function again - this time with parametres:
```lua
function addTwo(originalNumber)
  return originalNumber + 2
end
```
I note that there's no set length a function must be, so it can be as short, or as long as you'd like it to be. One suggestion is to keep them simple, requiring as little edge cases as possible. After all, you're coding it, you should know what you're putting inside.

### Extra Notes
<sup>[1]</sup> A void function is a function that doesn't return a value. It does its job, and moves on. In contrast, a returning function will send the value you told it to send back to the main program.
<sup>[2]</sup> Check out the variables file for information on this.

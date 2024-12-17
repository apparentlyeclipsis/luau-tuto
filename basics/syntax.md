# Syntax
Syntax is generally the most important thing to get used to when shifting between languages. Generally, the difficulty in switching languages, especially with more experienced programmers, is getting this right.

In lua, the syntax is generally simple, comparable to C and Python.

## Variables
Like C, you need to initialize - create your variables with a keyword. In C, there are multiple, a couple examples being:
```cpp
int myInteger = 0;
float myFloat = 0.1;
```
In contrast, lua only uses one, "local". 
```lua
local myVariable = 0
```
Lua variables are dynamic, and switch types based on the assigned value. This means you can convert variable types simply by replacing the value.
```lua
local myVariable = 0 -- integer
myVariable = 0.1 -- float
myVariable = "myVariable" -- string
```
In both languages, you can also declare a variable without giving it a value:
```lua
local variable  -- create variable

variable = 1    -- give it a value
```

## Conditional Statements
In all programming languages, there's this thing called an 'if-else statement'. If-else statements can generally be explained as a way to branch off from a 'main path', because not all the roads need to go the same way.

In C, a conditional statement would look something like this:
```c
if (condition) {
  // things that happen because of this condition being true
}
```
For contrast, a conditional statement in lua would look like this, at the most basic level.
```lua
if condition then
  -- things that happen because of this condition being true
end
```

## Functions
Functions are generally one of the most important things in any program. In lua, you can create both void and returning functions, and can provide parametres into one - just like pretty much every other programming language.

Creating a void function (without parametres) would look like this:
```lua
function myFunction()

end
```
If you want to make it a returning function, you can just add the keyword 'return'. Here's an example:
```lua
function myFunction()
  return "string"
end
```
Now with this returning function, there are multiple ways you can call it. Assuming the same function above, you can do this:
```lua
print(myFunction())

-- example output:
--> string

local myVariable = myFunction()
print(myVariable)
--> string
```
You can also incorporate functions into if-else statements, the following being an example, using the same function as above.
```lua
local string = "string"
if string == myFunction() then
  print("both strings are the same")
end
```
Parametres are very similar to how other languages, however with one key difference. In C, you can force a parametre type. The function will read the parametre's value as whatever you set it to. If the value isn't of the right type, the program breaks. Example:
```cpp
void myFunction(int integer) {
  return integer*2
}

//  example in/output
//  myFunction(12)       -> 24
//  myFunction(12.5)     -> error
//  myFunction("string") -> error
```
The reason that happens is because the value you provided has to be of the parametre's type. Lua has no check for this natively, however it can still break in a similar way, if you provide a type that isn't similar enough. 
```lua
function myFunction(integer)
  return integer*2
end

--  example in/output
--  myFunction(12)       -> 24
--  myFunction(12.5)     -> 25
--  myFunction("string") -> error
```

## Keywords
Lua keywords are generally more similar to python keywords than keywords from other programming languages. Here are some common lua keywords, in no particular order:

| -        | -      | -     | -      |
| -------- | ------ | ----- | ------ |
| and	     | break	| do    | else   |
| elseif   | end	  | false	| for    |
| function | if     | in    | local  |
| nil	     | not  	| or    | repeat |
| return   | then   | true  | until  |
| while    | -      | -     | -      |

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

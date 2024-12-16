Lua's syntax is relatively simple, and can generally be compared to MATLAB, C.

A MATLAB example is as follows:
```matlab
variable = x
% initialize variable as 'x' - this assumes 'x' 

function variable = x
  % this assumes 'x' is a function - meaning that 'variable' is valued as whatever 'x' gives it.
end

if x == 0
  % things that happens if x's value is 0
end
```
Lua can be handled similarly, as follows:
```lua
local variable = x
-- initialize variable as 'x'
-- this is how you create a variable - only the first time it's seen in the script should be written like this

variable = x
-- using the variable in any other situation will be like this.
-- this is how you'd be changing the value of the variable, and you can change the variable's type like this as well.

variable = "string"
-- assumes variable is a string based on value provided
variable = 101
-- assumes value is an integer - whole number. you can convert a string into a integer, and vice versa, like this
variable = 190.1231
-- assumes value is a float -- same process as conversion to string/integer
```
Unlike other programming languages, there's no need to convert a number to a string to link them together, unlike other languages - example, Python. Lua treats all combined statements like python fstrings, except they remain easier to read.
```python
print("string", str(integer))
print(f"string {integer}")
```
```lua
print("string" .. integer)
print("string", integer)
```

Conditional statements are also relatively simple, and can generally be compared to both Python and C.
```lua
if variable == 0 then
  -- if the variable's value is 0, follow this path
elseif variable == 1 then
  -- otherwise, if the variable's value is 1, follow this path
else
  -- if none of the above conditions are true, follow this last path
end
```

Compared to Python, which looks like this:
```python
if variable == 0:
  -- if variable's value is 0, follow this path
elif variable == 1:
  -- if the variable's value is 1, follow this path
else:
  -- if none of the above conditions are true, follow this last path.
```

In comparison, C looks like this:
```c
if (variable == 0) {
  # follow this path is variable's value is 0
} elseif (variable == 1) {
  # otherwise, if the variable's value is 1, follow this path
} else {
  # if none of the above conditions are true, follow this final path
}
```

You can realistically treat lua's then/end as C's use of curly brackets - or parenthesis.

Creating functions is also simple - comparable to Python and MATLAB:
```matlab
% MATLAB
function variable = x()
  % function things here
end
```
```python
# python
def x():
  # function things here
```
```lua
-- lua
function x()
  -- function things here
end
```
Lua takes tons of things from other languages, which makes it good as a secondary language to learn - or maybe a first one because it crosses over with so many others.

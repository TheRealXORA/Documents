# Getting Environments
The functions provide access to specific environments.

## getgenv
```luau
function getgenv(): { [string]: any }
```
It stands for "Get Global Environment". It returns a table representing the executor’s custom global environment. This allows you to create and access global variables, functions, and tables that persist across different scripts.

You can directly access global variables and functions stored in getgenv() without needing to use `getgenv().variableName`. For example, if a variable is stored as `getgenv().myVariable`, you can access it directly by just using `myVariable`.
However, if a local variable with the same name exists, the local variable will take precedence. In such cases, you must use `getgenv().variableName` to access the global variable.

### Example usage for getgenv

```luau
--// Creating a new global variable \\--
getgenv().global_variable = "Hello, World!"

--// Access the global variable from another script \\--
print(global_variable)  -- Output: Hello, world!

--// Define a global function \\--
getgenv().greet = function(name)
    return "Hello, " .. name .. "!"
end

--// Call the global function \\--
print(getgenv().greet("User"))  -- Output: Hello, User!

--// Create a global table \\--
getgenv().config = {
    speed = 16,
    jump_power = 50,
    fly = true
}

--// Access and modify table values \\--
print(getgenv().config.speed)  -- Output: 16
config.speed = 32
print(getgenv().config.speed)  -- Output: 32

--// Example of local and global variable conflict \\--
getgenv().my_variable = 2   -- Global variable
local my_variable = 1       -- Local variable

--//  If we just print my_variable, it will print the local value \\--
print(my_variable)  -- Output: 1

--// To access the global variable, use getgenv().my_variable \\--
print(getgenv().my_variable)  -- Output: 2

--// Example using [""] to access global variables \\--
getgenv()["global variable"] = "Foo!"

--// Accessing the global variable using [""] syntax \\--
print(getgenv()["global variable"])  -- Output: Foo!
```

## getrenv
```luau
function getrenv(): { [string]: any }
```
It stands for "Get Roblox Environment". It returns a table representing the roblox game’s environment. This allows you to access and alter the client game enviroment variables, functions, and tables, like game and print.

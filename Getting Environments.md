# Getting Environments
The functions provide access to specific environments.

## getgenv
```luau
function getgenv(): { [string]: any }
```
It stands for "Get Global Environment". It returns a table representing the executor’s custom global environment. This allows you to create and access global variables, functions, and tables that persist across different scripts.

You can directly access global variables, functions and tables stored in getgenv() without needing to use getgenv().variableName. For example, if a variable is stored as getgenv().myVariable, you can access it directly by just using myVariable.

## Example usage for getgenv

```luau
--// Creating a new global variable \\--
getgenv().GlobalVariable = "Hello, World!"

--// Access the global variable from another script \\ --
print(GlobalVariable)  -- Output: Hello, world!

--// Define a global function \\--
getgenv().greet = function(name)
    return "Hello, " .. name .. "!"
end

--// Call the global function \\--
print(getgenv().greet("User"))  -- Output: Hello, User!

--// Create a global table \\--
getgenv().config = {
    speed = 10,
    jump_power = 50,
    fly = true
}

--// Access and modify table values \\--
print(getgenv().config.speed)  -- Output: 10
config.speed = 20
print(getgenv().config.speed)  -- Output: 20
```

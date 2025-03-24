# Getting Environments
The functions provide access to specific environments.

## getgenv
```luau
function getgenv(): { [string]: any }
```
Returns a table representing the executor’s global environment. This allows you to create and access global variables, functions, and tables that persist across different scripts.

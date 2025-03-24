# Getting Environments
The functions provide access to specific environments.

## getgenv
```luau
function getgenv(): { [string]: any }
```
Stands for “Get Global Environment.” It returns a table representing the executor’s custom global environment. This allows you to create and access global variables, functions, and tables that persist across different scripts.

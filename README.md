# PerfectSignal (GoodSignal)
The same as GoodSignal, just with a complete type definition and a fix of an error in Signal:Wait found by **[Crusherfire](https://www.youtube.com/watch?v=yevAvHU3ewo&t=297s)**
This module will most probably never be updated - it seems perfect.
A Roblox Lua Signal implementation that has full API and behavioral parity with Roblox' `RBXScriptSignal` type.

# Available Here!
- **[This repository](src/init.luau) ~ [src/init.luau](src/init.luau)**
- **[Wally](<https://wally.run/package/coffilhg/perfectsignal>)**

    ```toml
    PerfectSignal = "coffilhg/perfectsignal@1.0.1"
    ```
- **Rotriever**

    ```toml
    PerfectSignal = "github.com/Coffilhg/PerfectSignal@1.0.1"
    ```

# Full API

```lua
-- Create
local sig = Signal.new()

-- Connect and Fire
local connection = sig:Connect(function(arg1, arg2) ... end)
sig:Fire(param1, param2)

-- Wait on Fire
local param1, param2 = sig:Wait()

-- Disconnect
connection:Disconnect()
sig:DisconnectAll()
```
# No Memory Leaks!
`GoodSignal` is implemented in pure Lua (using the task library, rather than internally using a BindableEvent), so it does not suffer from memory leaks. Even if you don't `Disconnect` all of the connections on a GoodSignal, everything will still be GCed normally.

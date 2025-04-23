# Objective Events

# Prompt

**Type:** `RemoteEvent`  
**Location:** `ReplicatedStorage.Events.Prompt`

---

## Description

`Prompt` is currently used to route all game objectives proximity prompts to a central handler, [Client.Interface.ObjectiveHandler.OnInputFired(model: Model, interface: ScreenGui)](../Client/Interface/ObjectiveHandler.md#oninputfired)

---

## Usage

### 🔁 Listening (Client or Server)

```lua
local ReplicatedStorage = game:GetService("ReplicatedStorage")
local MyCustomEvent = ReplicatedStorage:WaitForChild("Events"):WaitForChild("MyCustomEvent")

MyCustomEvent.Event:Connect(function(player)
    print(player.Name .. " completed the puzzle!")
    -- Add client/server-side logic here
end)
```

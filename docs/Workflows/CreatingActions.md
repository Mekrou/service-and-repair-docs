# Creating Actions

## Overview
So you want to add something for the players to interact with more than just a prompt? No problem!

We use Action Modules to be able to create actions for our players.

## The Action Bus

Inside the client's InputController, it loops through all of the modules inside of the Actions Folder inside InputController, indexes their data and registers them to the Action Registry.
Making an ActionModule inside the action folder is how you make your own player controls / input.

## Creating an Action Module
Action Modules are small module scripts we create to manage specific player input actions.

We tend to follow a certain pattern in order for action modules to work accordingly, but you can always add more functions if needed, you just NEED these three functions in order to work in the bus!

### `ActionModule:BindInputs()`

This is used to bind our action into ContextActionService

#### Example Code:

```
function DefaultCameraActions:BindInputs()
	ActionController:ActivateAction("camera-rotate")
end
```

### `ActionModule:UnbindInputs()`

This is used to unbind our action from ContextActionService

#### Example Code:

```
function DefaultCameraActions:UnbindInputs()
	ActionController:DeactivateAction("camera-rotate")
end
```

### `ActionModule:Register()`

This is used to register our action into the ActionRegistry

#### Example Code:

```
function ActionModule:Register()
    local inputDevice: Shared.InputDevice = Input:GetInputDevice()

	local info: ActionController.ActionInfo = {
		hasButton = false,
		inputs = { 
			Enum.KeyCode.E, 
			Enum.KeyCode.ButtonR1,
			Enum.KeyCode.Q,
			Enum.KeyCode.ButtonL1,
		},
		handler = onCameraSpin
	}

    -- Registering individual actions
	ActionController:RegisterAction("camera-rotate", info)
    -- Registering action into a group
    ActionController:RegisterInActionGroup("Default", "camera-rotate", info)
end
```
# Objectives

## Function Call Sequence

This section describes the sequence of function calls that manage objectives. Below is the flow of the functions in the sequence:

1. **[``Collections.InitializeMapObjects()``](../Server/Collections.md)** - 
2. **[``Collections.InitializeObjectives()``](../Server/Collections.md)** - Loops through all objects tagged "Objective" and calls [``ObjectiveUtil.InitializeModel(model)``](../Server/ObjectiveUtil.md)
3. **[``ObjectiveUtil.InitializeModel(model: Model``)](../Server/ObjectiveUtil.md)** - Finds the model's proximity prompt and hooks up its ``.Triggered`` event handler. Inside the handler, fires [``Prompt``](../Events/ObjectiveEvents.md#prompt) client event. This causes #4 to run:
4. **[``Client.Interface.ObjectiveHandler.OnInputFired(model: Model, interface: ScreenGui)``](../Client/Interface/ObjectiveHandler.md#oninputfired)**

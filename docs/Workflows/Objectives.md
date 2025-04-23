# Objectives

## Function Call Sequence

This section describes the sequence of function calls that manage objectives. Below is the flow of the functions in the sequence:

1. **[``Collections.InitializeMapObjects()``](../Server/Collections.md)** - 
2. **[``Collections.InitializeObjectives()``](../Server/Collections.md)** - Loops through all objects tagged "Objective" and calls [``InitializeModel(model)``](../Server/ObjectiveUtil.md)
3. **[``ObjectiveUtil.InitializeModel(model: Model``)](../Server/ObjectiveUtil.md)** - finds the model's proximity prompt and hooks up its ``.Triggered`` event to fire an client event () which passes the player that triggered the prompt and objective model.

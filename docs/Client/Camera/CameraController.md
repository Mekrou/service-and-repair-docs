# CameraController

## Overview
Manages the client's active camera mode in the game, allowing for switching between multiple camera behaviors dynamically based on remote events.

## Summary
The ``CameraController`` listens for camera mode change events from the server.
It initializes and manages instances of different camera modes, switching between them when necessary.
Each camera mode must implement the ``Init``, ``Update``, and ``Stop`` methods.

## Types
+ ``CameraController``:
Object managing the active camera mode and switching logic.

+ ``CameraMode`` (from Shared):
Represents a camera behavior. Expected to have Init, Update, and Stop methods, and a kind property of type CameraModeName.

+ ``CameraModeName`` (from Shared):
Enum-like string identifying the type of a camera mode.

## Functions

### ``CameraController.new(): CameraController``

> Creates and returns a new instance of ``CameraController``

### ``CameraController:SetMode(mode: CameraMode): ()``
> Switches the currently active camera mode to the given ``mode``.
> 
> * If the ``mode`` is already active, no action is taken
> * If a different mode is active, it is stopped before switching
> * If the mode is not previously tracked, it is added to the controller's list of cameras

### ``CameraController:Start(): ()``
> Begins listening for server events (``CameraModeChanged``) to update the active camera mode. 
> Also binds the active camera mode's ``Update`` method to ``RunService.PreRender``

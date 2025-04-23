# Camera

## Properties

### CamMist: `BasePart`

#### Description:
CamMist is used to create a fog around the character on the client. This is rarely used unless in gameplay testing but it is functional.

### CurrentRotation: `number`

#### Description:
CurrentRotation is used to keep track of the current rotation of the camera focused along a character.

### Highlight: `Highlight`

#### Description:
A highlight used to show the character if the line of sight is obstructed between the camera and character.

## Functions

### Init: `Tnit()`

#### Parameters
|`camera`|`offset`|`FOV`|
|-|-|-|
|`Camera`|`number`|`number`|

#### Description
Initializes the camera module by creating the highlight instance and raycast parameters for the line of sight from the character subject.

### OnInput: `onEvent()`

#### Parameters
|`name`|`amount`|
|-|-|
|`string`|`number`|

#### Description:
This function is used as a callback to when a camera input is recieved and to change the camera rotation.

### OnCharacterAdded: `OnCharacterAdded()`

#### Parameters
|`character`|
|-|
|`Model`|

#### Description:
Fired whenever a character is passed to serve as the camera's subject. This could be either the player has gotten their character, or they are spectating another character.

### SetCameraAnchor: `SetCameraAnchor()`

#### Parameters
|`AnchorPart`|
|-|
|`BasePart`|

#### Description:
Used to set the camera's CFrame equal to the CFrame of the given `AnchorPart`. Used in features of the game that require a different perspective.

### OnCharacterRemoved: `OnCharacterRemoved()`

#### Parameters
| |
|-|
|`()`|

#### Description:
Stops the camera from rendering without a character subject.

### OnCameraModeChanged: `OnCameraModeChanged()`

#### Parameters
|`mode`|
|-|
|`number`|

#### Description:
Sets the camera's mode to the mode provided.

##### Camera Modes:
`1` - Isometric Character View
`2` - AnchorPart Static View
`3` - None (Cutscene View???)

### OnSubjectChanged: `OnSubjectChanged`

#### Parameters
|`subject`|
|-|
|``BasePart OR Model``|

#### Description:
Used to determine if the given subject is a character or a anchored part. If the subject is a character, it will set it as a subject. Otherwise it will act as an anchored part.

### SetRotation: `SetRotation()`

#### Parameters
|`amount`|
|-|
|`number`|

#### Description:
Loops and iterates through the rotation values used for the camera's isometric subject view.

### SetMistEnabled: `SetMistEnabled()`

#### Parameters
|`enabled`|
|-|
|`boolean`|

#### Description:
Used to enable and disable the camera mist.

### Update: `Update()`

#### Parameters
|`dt`|
|-|
|`number`|

#### Description:
Updates the camera every frame inside the client's `PreRender` Lifetime Event.
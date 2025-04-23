# Client

## Functions

### Initialize: `init()`

#### Parameters
| |
|-|
|`()`|

#### Description:
Initializes the client.
This includes initializing any client modules that contain a `init()` function

### OnInput: `onInput()`

#### Parameters
| |
|-|
|`()`|

#### Description:
This is a function the client has that is binded to the `RenderStep` Lifetime Event.
This is where input is updated for the client, this helps with overriding core movement that is unneeded, such as jumping.

### OnPreRender: `onPreRender()`

#### Parameters
|`dt`|
|-|
|`number`|

#### Description:
This is a function used in the client that is binded to the `PreRender` Lifetime Event. This is where visuals are calculated such as camera position and rotation, and User Interface.
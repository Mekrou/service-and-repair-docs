# PromptHandler

## About
The PromptHandler is responsible for handling the styling and formatting of the proximity prompts on the client.
If you want to affect the behavior of the prompts, visit the [``ObjectiveUtil``](/docs/Server/Objectives/ObjectiveUtil.md) for futher information.

The prompt interface is a ImageButton to allow clicking and tapping of the prompt if desired, along with formatted keybinds to support keyboard and console players.

## Combatibility Features

### KeyCode Images
Desktop follows a format to where `prompt.KeyboardKeyCode` is used to format the image to display for the player.

Console follows a format to where `prompt.GamepadKeyCode` is used to format the image to display for the player.

Mobile uses the prompt itself as a button for the player.

## Properties

### `HoldValue: number`

#### Description:
Used to track the amount spent holding down the shown proximity prompt.

### `HoldMax: number`

#### Description:
Used to retain information over the time needed to hold the shown prompt

## Functions

### `onPromptShow(prompt: ProximityPrompt)`

#### Parameters
|                |                                                                  |
| -------------- | ---------------------------------------------------------------- |
| Prompt: **ProximityPrompt** | The ProximityPrompt that is in it's range of interaction. |

#### Description:
Fires whenever a proximity prompt is in range to be interacted with by the local player.

### `onPromptHidden(prompt: ProximityPrompt)`

#### Parameters
|                |                                                                  |
| -------------- | ---------------------------------------------------------------- |
| Prompt: **ProximityPrompt** | The ProximityPrompt that is not longer in it's range of interaction. |

#### Description:
Fires whenever a proximity prompt is no longer in range and able to be interacted with by the local player.

### `onPromptHeld(prompt: ProximityPrompt)`

#### Parameters
|                |                                                                  |
| -------------- | ---------------------------------------------------------------- |
| Prompt: **ProximityPrompt** | The ProximityPrompt that is being interacted with by the local player. |

#### Description:
Fires when the player begins to start holding the proximity prompt.

### `onPromptReleased(prompt: ProximityPrompt)`

#### Parameters
|                |                                                                  |
| -------------- | ---------------------------------------------------------------- |
| Prompt: **ProximityPrompt** | The ProximityPrompt that is being interacted with by the local player. |

#### Description:
Fires when the player releases from holding the proximity prompt.

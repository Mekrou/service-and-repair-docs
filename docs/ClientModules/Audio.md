# Audio

## Properties

### MaxEmitters: `number`

#### Description:
MaxEmitters is used to create a limit to the size of the cache of emitters used in the audio module.

## Functions

### Init: `init()`

#### Parameters
| |
|-|
|`()`|

#### Description:
This is the initialization function of the Audio Module. In the initialization, a Sound Origin is made to house the cache of sound emitters. Sounds from the library are also loaded into the game to reduce chances of the lack of audio or SFX in realtime gameplay.

### OnEmissionEvent: `onEmissionEvent()`

#### Parameters
|`key`|`from`|`props`|
|-|-|-|
|`string`|`Vector3?`|`SoundProperties`|

#### Description:
Emits an Audio whenever the bindable event: `EmitAudio` is fired on the client. Given the key, the sound will play at a given location with the given and supported properties found in a `Sound` Instance, such as `Volume` and `Distance`. If a given distance is not found, then the audio will be played via `game.SoundService:PlayLocalSound()`

### GetSFX: `getSFX()`

#### Parameters
|`key`|
|-|
|`string`|

#### Description:
This is a local function used to return a entry inside the audio module's `Library` module that holds all keys and `SoundID`'s.
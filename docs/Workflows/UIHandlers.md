# Interface Handlers

UIHandlers is a psuedo-class module that initializes a frame or other UI components that are passed when intitializing Handler.

## Composition
UIHandlers are puesdo-classes, meaning that they behave as a collection of helper functions that are for specific instances that you pass as a parameter.

These are very versitile for us in order to manage pieces of GUI without most of the code going inside our main `Interface` Module on the client.

But UIHandlers are composed of atleast two functions.
`init()` and `cleanup()`. As labeled, `init()` will initialize the ui element you want and `cleanup()` will stop the ui element from updating and will disconnect any connections created.

To keep track of connections inside your `init()` function, handlers tend to keep an array inside the module. Inserting your connections into a array for later, easier cleanup of connections is a good practice to save unnecessary updates to non-visible interface.

## Functions

### Init: `init()`

#### Parameters
|`frame`|`any`|
|-|-|
|`GuiBase`|`...`|

#### Description:
A base function to initialize a Interface Handler, usually most init functions, you will just want your specific GUI instance you want to program and any necessary information you want afterwards.

### Cleanup: `cleanup()`

#### Parameters
|`frame`|`any`|
|-|-|
|`GuiBase`|`...`|

#### Description:
The base function used to hide, disconnect, and stop updating the given GUI instance. You could add any other necessary information as well if you'd like.
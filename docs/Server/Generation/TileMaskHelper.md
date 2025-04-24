# TileMaskHelper

## Overview
The ``TileMaskHelper`` module is responsible for calculating and managing tile bitmask values for cells in our grid-based map. It determines the connection state of each walkable tile by evaluating its neighbors in four cardinal directions — North, West, East, and South — and encodes this connectivity using a directional bitmask.

This bitmask is used for purposes such as:

1) Dynamically determining tile appearances (auto-tiling)

2) Broadcasting changes to listeners via events

## Functions
### ``updateCells(map: Grid, cells: { Cell })``

#### Parmeters 
|                |                                                                  |
| -------------- | ---------------------------------------------------------------- |
| map: __Grid__  | The Grid in which the updates are taking place (this should be the global map Grid).  |
| cells: __{ Cell }__ | A list of cells that should be updated. |

#### Description
Recalculates the tile mask of each cell, and fires ``TileMaskUpdateDoneEvent`` when all have been recalculated.
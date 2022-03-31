# Data Values

Data value are block/item variation. Data value can be rotation of the block, block colour, item durability, etc. Data value can be called "Block State"

Data value divided into 2 type, integer only and JSON-List.

For example:
``` py
# For integer
/give @p stone 5
# For JSON-List
/setblock 0 -60 0 stone_button ["facing_direction": 0, "button_pressed_bit": true]
```

!!! info

    For detail block data, you can see the [Minecraft Wiki](https://minecraft.fandom.com/wiki/Block_states)

## List of Data Values

### Coloured Block

``` yaml
# Block List
block: 
  - Concrete
  - Concrete Powder
  - Glazed Terracotta
  - Shulker Box
  - Stained Glass
  - Stained Glass Pane
  - Terracotta
  - Wool

# Integer + List Data Value
colour:
  - 0 : white
  - 1 : orange
  - 2 : magenta
  - 3 : light_blue
  - 4 : yellow
  - 5 : lime
  - 6 : pink
  - 7 : gray
  - 8 : silver
  - 9 : cyan
  - 10: purple
  - 11: blue
  - 12: brown
  - 13: green
  - 14: red
  - 15: black
```

### Stone Type

``` yaml
# Integer + List Data Value
stone_type:
  - 0: stone
  - 1: granite
  - 2: granite_smooth
  - 3: diorite
  - 4: diorite_smooth
  - 5: andesite
  - 6: andesite_smooth
```

### Button

``` yaml
# Block List
block:
  - Woods & Fungus Type Button
  - Stone Button
  - Polished Blackstone Button

# Rotation/Position
facing_direction:
  - 0: Down
  - 1: Up
  - 2: North
  - 3: South
  - 4: West
  - 5: East

# Button Pressed
button_pressed_bit:
  - true : Activated (On)
  - false: Not Activated (Off)
```

Int 0-5 are the button direction, while +8 set the button to be pressed. For example:  
`stone_button 1` -> Button facing up  
`stone_button 9` -> Button facing up and activated [ 1 (Direction) + 8 = 9 (Button Activated) ]
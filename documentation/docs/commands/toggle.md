# Commands T-Flip-Flop

Lever has interesting behavior. They can turn on/off the redstone with single click. On redstone component, there's T-Flip-Flop, which same as lever, but it can do with just button. This can really useful for redstone project as it's works like lever, toggle on/off redstone circuit.

But what if we used on Commands? That can be useful for commands setting to turn on/off something.

For example, I want to turn day and night with commands, you can by `/time set night` and `/time set day`. But we can use it on one single function file and call the same function

## Setup

This is the example of day/night toggle

``` .py title="toggle.mcfunction" linenums="1"
scoreboard players add @s toggle 1
scoreboard players set @s[scores={toggle=2..}] toggle 0
# Switchable commands
execute @s{scores={toggle=0}} ~ ~ ~ time set day
execute @s{scores={toggle=1}} ~ ~ ~ time set night
```

!!! important

    You must add "toggle" objectives to make this function work. You can by adding `scoreboard objectives add toggle dummy` on top of the file

Description:

- Line 1 and 2 are the `Commands T-Flip-Flop`. They must on line 1 and 2, or the order must add the score, then set the score
- Line 1 will add the score 1 everytime the function is called
- Line 2 will set the score into 0 if the score was 2 or more. This make the score just only 1 and 0 as on/off or true/false
- Line 4 will set the time into day if the score is 0 (false/off). This same on line 5, it will set the time to night if the score is 1 (true/on)

This can be extend into more than 2 statement, like change the gamemode into Creative, Survival, and Adventure, etc.
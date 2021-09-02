![Index Framework Banner](../images/ifw/banner.png)
# 7. Weapons

> **Note:** Animations are broken when you publish since it's impossible to make animations public. Roblox plz fix. 

Weapons/Tools are configurable through the tools "ToolConfig" script. This can be located in game.ServerScriptService.IndexFramework.Manifest.Tools[ToolName].
To create weapons, all you need to do is to place your weapon in the same format as the others into this folder.

#### Giving yourself weapons.

To give yourself this weapon in-game, all you need to do is to.

1. In the spawn menu, go to the info tab, spawn an info_map. If you already have one you can skip this step.
2. Go to the Properties tab and make sure "Force HEV" is ticked.
3. In the spawn menu, in the script tab, spawn a script_server.
4. Edit the script in the properties tab and paste in the following.

```lua
-- This is a script_server module

local Module = {}

function Module.PlayerAdded(Player)
    Module.m.Tools.GiveTool(Player, "Crowbar") -- Gives all players the crowbar.
end

return Module
```

You can replace Crowbar with whatever other tool you want.
> **Note:** Index framework only includes the pistol, smg, stunstick, and crowbar. Only the crowbar is functional.

5. Once in-game, just press the number key associated with the weapon to select it (1 for crowbar.)

#### Fixing the animations.

When you publish your game, you may notice that animations won't work. To fix this:
1. Drag the weapon from game.ServerScriptService.IndexFramework.Manifest.Tools into game.Workspace.
2. Select the weapon with the animation editor. Then select the animation to export by clicking 
the three dots near the top left of the animation editor, then selecting the animation.
3. Export the animation by clicking the three dots again and clicking export
4. Replace the animation id in game.ServerScriptService.IndexFramework.Manifest.Animations.Human.Tools[ToolName]







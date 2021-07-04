![Index Framework Banner](../images/ifw/banner.png)
# 6. NPCs

> **Note:** We never added AI to the framework, all movements of NPCs must be pre-planned with nodes.

Index Framework features two types of NPCs (citizens and metropolice), these can be found in the 'npc' section of the spawn tab. To program NPCs you must use a 'script_client' entity. These contain a module script that is loaded into the client when the game starts.

1. Spawn an NPC of your choosing and set the 'Reference Id' field in the properties tab to something unique.
2. Spawn a 'info_nodes' entity and give it a unique id. The NPC will follow these nodes during the scripted event. To add another node to the path, click the 'Place Node' button in the properties tab (you will need to hold ALT when selecting individual nodes).
3. Spawn a 'trigger_block' entity and give it a unique id. This will be used to start the scripted sequence when the player touches it.
4. Spawn a 'script_client' entity, select it, and click 'Edit Script' in the properties tab.
5. Change your script so it matches the code below (make sure to change the values to match the IDs you set in the previous steps).

```lua
-- This is a script_client module

local Module = {}

function Module.Init() -- Runs when the client starts
    Module.Core.WaitForTrigger("TRIGGER ID")

    local NPC = Module.Core.GetCharacters("NPC ID")
    local Nodes = Module.Core.GetMapEntityById("NODES ID")

    Module.Core.FollowNodes(NPC, Nodes)
end

return Module
```

Upon walking into the trigger, the NPC should follow the path you planned out. If it doesn't work, check the output for errors.
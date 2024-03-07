<a href="https://discord.gg/Z9Mxu72zZ6" target="_blank">
    <img src="https://discordapp.com/api/guilds/857672921912836116/widget.png?style=banner3" alt="Andyyy Development Server" height="150px" />
</a>


# Dispatch systems / police alarm:
Integrating your own dispatch can be done in `rob_atm/bridge/<YOUR FRAMEWORK>/server.lua`

By default this script is integrated with `cd_dispatch`, `ps-dispatch`, and `qs-dispatch` if you use QB or ESX.

If you're using the better framework [ND_Core](https://ndcore.dev/) this script is integrated with `ND_MDT` already and will alarm police from there.


# Creating items:
You can find images in `rob_atm/INSTALLATION`, for creating items correctly read below!

### Ox inventory all frameworks!:
If you're using ox_inventory then place this in `ox_inventory/data/items.lua`
```lua
["rope"] = {
    label = "Rope",
    weight = 1000,
    stack = true,
    close = true,
    server = {
        export = "rob_atm.use_item_rope"
    }
},
["drill"] = {
    label = "D-Handle Drill",
    weight = 3500,
    stack = false,
    close = true,
    consume = 0.2,
    server = {
        export = "rob_atm.use_item_drill"
    }
},
```

### ESX other inventories:
If you're using ESX with a different inventory than ox_inventory, run this sql:
```sql
INSERT INTO `items` (`name`, `label`, `weight`) VALUES
	("drill", "D-Handle Drill", 3500),
	("rope", "Rope", 1000),
;
```

### QBCore other inventories:
If you're using QBCore with a different inventory than ox_inventory, add these items to `qb-core/shared/items.lua`
```lua
["rope"] = {
    ["name"] = "rope",
    ["label"] = "Rope",
    ["weight"] = 10,
    ["type"] = "item",
    ["image"] = "rope.png",
    ["unique"] = false,
    ["useable"] = true,
    ["shouldClose"] = true,
    ["combinable"] = nil,
    ["description"] = ""
},
["drill"] = {
    ["name"] = "drill",
    ["label"] = "Drill",
    ["weight"] = 10,
    ["type"] = "item",
    ["image"] = "drill.png",
    ["unique"] = false,
    ["useable"] = true,
    ["shouldClose"] = true,
    ["combinable"] = nil,
    ["description"] = ""
},
```


### Not using a framework?
If you're not using a framework you can still use the drill and rope by using `/use-drill` and `/use-rope` comands.

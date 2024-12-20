<a href="https://discord.gg/Z9Mxu72zZ6" target="_blank">
    <img src="https://discordapp.com/api/guilds/857672921912836116/widget.png?style=banner3" alt="Andyyy Development Server" height="150px" />
</a>


# [FiveM ATM Robbery Script](https://andyyy.tebex.io)
This is the documentation for the best atm robbery script on fivem.
You can find the resource on [andyyy.tebex.io](https://andyyy.tebex.io)

<br>

# Dispatch systems / police alarm:
Integrating your own dispatch can be done in `rob_atm/bridge/<YOUR FRAMEWORK>/server.lua`

By default this script is integrated with `cd_dispatch`, `ps-dispatch`, and `qs-dispatch` if you use QB or ESX.

If you're using the better framework [ND_Core](https://ndcore.dev/) this script is integrated with `ND_MDT` already and will alarm police from there.

<br>

# Creating items:
You can find images in `rob_atm/INSTALLATION`, for creating items correctly read below!

<br>

### Ox inventory all frameworks!:
If you're using ox_inventory then place this in `ox_inventory/data/items.lua`, if you changed the name of the items you need to change the names in `rob_atm/data/config.lua` and in the export for example if you change the "rope" name to "rope2" you need to change the export name to `rob_atm.use_item_rope2`.
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

<br>

### ESX other inventories:
If you're using ESX with a different inventory than ox_inventory, run this sql:
```sql
INSERT INTO `items` (`name`, `label`, `weight`) VALUES
	("drill", "D-Handle Drill", 3500),
	("rope", "Rope", 1000),
;
```

<br>

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

<br>

### Not using a framework?
If you're not using a framework you can still use the drill and rope by using `/use-drill` and `/use-rope` comands.

<br>

# Editing the atm textures:
If you use different atm textures than default you can modify them to your textures in `rob_atm/stream/nd_atms_txt.ytd`.

<br>

# Objects used
If you're using an anticheat that blocks items here's the list used that you can whitelist.
```
nd_atm01_frame
nd_atm02_frame
nd_atm03_frame
nd_atm01_part
nd_atm02_part
nd_amt03_part
prop_rope_hook_01
```

<br>

# Watch the v2 update video:
If you already own this resource you can just download the latest version from keymaster again.

<br>

[![rob_atm_v2](https://github.com/Andyyy7666/andyyy.tebex.io/assets/86536434/bfd748f8-9fb4-4411-a7e2-9f39a1a6d04b)](https://youtu.be/gY6M71NSI5o)

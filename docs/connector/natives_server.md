# Server Natives

Server classed Wosa natives to be used with the API connector.

#### User

```Markdown
-- Desc: Used to get the r* license, Main used identifier in Wosa.

local license = Wosa.User.License(ID --[[ int ]])
```

```Markdown
-- Desc: Used to get the currently active character table or user table. The "Type" can either be "i" for inventory or "c" for character.

local Wosa.User.CurrentDB(ID --[[ int ]], Type --[[ string ]])
```

```Markdown
-- Desc: If you are looking to return a player id from a license you can use this function, This will return nil if the player is not active on the server.

local ID = P_API.User.UserFromLicense(License --[[ string ]])
```

```Markdown
-- Desc: Will kick a user by the "SYSTEM".

Wosa.User.Kick(ID --[[ int ]], Reason --[[ string ]])
```

```Markdown
-- Desc: Will permanent ban the user by the "SYSTEM".

Wosa.User.Ban(ID --[[ int ]], Reason --[[ string ]])
```

#### AntiCheat

```Markdown
-- Desc: This native can be used to ban people from "event" abusing currently. Do not use this native for regular banning as this system will and might work differently.

Wosa.Character.AntiCheat.Ban(ID --[[ int ]], Type --[[ string ]], Custom --[[ string ]])

-- Example:
Wosa.Character.AntiCheat.Ban(1, "event", "MY_EVENT_HEHE")
```

#### Permission

```Markdown
-- Desc: Will return the users rank in the server.

local rank = Wosa.User.Permission.Get(ID --[[ int ]])
```

```Markdown
-- Desc: Will set the users rank. Needs to be a valid rank, If non valid they will not be available to join.

local rank = Wosa.User.Permission.Set(ID --[[ int ]], Rank --[[ string ]])
```

#### Money

```Markdown
-- Desc: Used to remove money from any available payment method.

Wosa.Character.Money.RemoveFromAny(ID --[[ int ]], Amount --[[ int ]])
```

```Markdown
-- Desc: Used to add money to any available payment method.

Wosa.Character.Money.AddToAny(ID --[[ int ]], Amount --[[ int ]])
```

```Markdown
-- Desc: Via this function you can get a players avaliable "payment methods".

local methods = Wosa.Character.Money.Methods(ID --[[ int ]])

-- Example:
print('Vanilla Card: '..tostring(methods[1]))
print('Business Card: '..tostring(methods[2]))
print('Cash: '..tostring(methods[3]))
```

```Markdown
-- Desc: Check the money balance for a specific payment method.

local balance = Wosa.Character.Money.Balance(ID --[[ int ]], Method --[[ string ]])

-- Example:
local balance = Wosa.Character.Money.Balance(ID, 'RE_Cash')

print('The player has '..balance..' as balance as hand cash.')
```

```Markdown
-- Desc: Removes money from a specific payment method.

Wosa.Character.Money.Remove(ID --[[ int ]], Method --[[ string ]], Amount --[[ int ]])
```

```Markdown
-- Desc: Add money to a specific payment method.

Wosa.Character.Money.Add(ID --[[ int ]], Method --[[ string ]], Amount --[[ int ]])
```

```Markdown
-- Desc: Set the money for a specific payment method.

Wosa.Character.Money.Set(ID --[[ int ]], Method --[[ string ]], Amount --[[ int ]])
```

#### Character

```Markdown
-- Desc: Add driver license points to a players current character.

Wosa.Character.AddLicensePoints(ID --[[ int ]], Points --[[ int ]])
```

```Markdown
-- Desc: Return character data for a users current selected character. Table possible indexes:
    -- firstname : string
    -- middlename = : string
    -- lastname = : string
    -- day = : string
    -- month =  : string
    -- year = : int
    -- gender = : string
    -- phone_number : string
    -- driver_license : bool
    -- truck_license : bool
    -- air_license : bool
    -- boat_license : bool
    -- firearm_license : string
    -- job : string

local data = Wosa.Character.Data(ID --[[ int ]])
```

```Markdown
-- Desc: Return characters data from first and lastname (from the database), will return the same table roughly as above ^^.

local data = Wosa.Character.DataFromName(Firstname --[[ string ]], Lastname --[[ string ]])
```

```Markdown
-- Desc: Returns all characters from the database.

local data = Wosa.Character.All()
```

#### Faction

Server faction natives does not take immediate effect on the user, The user is required to relogg in order to notice the changes.

```Markdown
-- Desc: Add a player to a faction manually. This just straight accesses the database and uses a
"insert" method to add it manually to the database.

Wosa.Character.Faction.Add(ID --[[ int ]], Job --[[ string ]], Rank --[[ string ]], SubRank --[[ string ]])
```

```Markdown
-- Desc: This function can be used to remove a player from a faction, As this function utilizes
license + character table means that you can remove players from a faction when they are
offline as well.

Wosa.Character.Faction.Remove(License --[[ string ]], CharacterTable --[[ string ]], Job --[[ string ]])
```

```Markdown
-- Desc: Used if you want to update a specific row in the database for a faction, You can
update users rows when they are offline as well.

Wosa.Character.Faction.Update(License --[[ string ]], CharacterTable --[[ string ]], Job --[[ string ]], newRank -- [[ string ]], newSubRank -- [[ string ]])
```

#### Inventory

```Markdown
-- Desc: Returns all items in a table, loop or index the table to get values. Gets the inventory
table for a specific user on the server. Table possible indexes:
    -- logged_name : string
    -- license_id : string
    -- item_name : string
    -- display_name : string
    -- item_string1 : string
    -- item_string2 : string
    -- item_string3 : string
    -- item_float1 : float
    -- item_float2 : float
    -- item_float3 : float
    -- item_bool1 : bool
    -- item_bool2 : bool
    -- item_bool3 : bool
    -- item_int1 : int
    -- item_int2 : int
    -- item_int3 : int

local items = Wosa.Character.Inventory.Get(ID --[[ int ]])

-- Example:
for i, item in ipairs(items) do
    print('this user has a '..item.display_name..'.')
end
```

```Markdown
-- Desc: Remove all "removable" items from the players inventory, That said all "custom" items but not items such as ID card, cash item, drivers license etc.

Wosa.Character.Inventory.Item.RemoveAllCustom(ID --[[ int ]])
```

```Markdown
-- Desc: Add a item to a users character.

-- // Core Dev Notice: Should prolly remove "InventoryTable" and auto set it for less confusion.

Wosa.Character.Inventory.Item.Add(ID --[[ int ]], InventoryTable --[[ string ]], Data = --[[ table ]])

-- Example:
local Data = {itemName = 'RI_EXAMPLE_ITEM', displayName = 'Example Item', Usable = true, Givable = true, Dropable = true, String1 = '', String2 = '', String3 = '', Bool1 = false, Bool2 = false, Bool3 = false, Int1 = 0, Int2 = 0, Int3 = 0, Float1 = 0.0, Float2 = 0.0, Float3 = 0.0 }
Wosa.Character.Inventory.Item.Add(1, 'inventory_1', Data)
```

```Markdown
-- Desc: So, This can be used in a few ways. If you leave "ItemID" nil then you will remove
all items named the "itemName" in the inventory. If you want to remove a specific
item input the "ItemID".

Wosa.Character.Inventory.Item.Remove(ID --[[ int ]], ItemName --[[ string ]], ItemID --[[ int ]])
```

```Markdown
-- Desc: Check if a person has a item, will return true if the person has more then 1 of the item.

local Exist = Wosa.Character.Inventory.Item.Exist(ID --[[ int ]], ItemName --[[ string ]])
```

#### Other

```Markdown
-- Desc: Converts a SqlData to a readable Lua visible date, useful for transforming a timestamp to a "readable" format.

Wosa.Tools.ConvertSQLDateToLuaFormat(SqlDate -- [[ int? ]])
```

```Markdown
-- Desc: Returns the full data set for all languages from "wosa_core".

local Languages = Wosa.Translate.Get()
```

```Markdown
-- Desc: Return the current used language.

local Language = Wosa.Translate.Language()
```
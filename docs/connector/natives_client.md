# Client Natives

Client classed Wosa natives to be used with the API connector.

#### Scripting

```Markdown
-- Desc: Returns the current usage in kb's as a number (memory) from the core.

local kbs = Wosa.cMemUsage()
```

```Markdown
-- Desc: Creates a thread, "CreateThread" basically.

Wosa.Loop(RequireCharacterLoaded --[[ bool ]], function()

end, WaitMs --[[ int ]])
```

#### Player

```Markdown
-- Desc: Gets the players ped cached, A good memory saving practise.

local ped = Wosa.Player.Ped()
```

```Markdown
-- Desc: Gets the players coords cached, A good memory saving practise.

local coords = Wosa.Player.Coords()
```

#### User

```Markdown
-- Desc: The current character table used, such as "character_1".

local characterTable = Wosa.User.CharacterDB()
```

```Markdown
-- Desc: The current inventory table used, such as "inventory_1".

local characterTable = Wosa.User.InventoryDB()
```

```Markdown
-- Desc: Can be used to manually overwrite the coord saver where you can save with the "last position". Example if you are in a interior you dont want anyone to be avaliable to spawn back in.

Wosa.User.CoordsSaver(bool --[[ bool ]])
```

#### Character

```Markdown
local firstname = Wosa.Character.Firstname()
```

```Markdown
local middlename = Wosa.Character.Middlename()
```

```Markdown
local lastname = Wosa.Character.Lastname()
```

```Markdown
local day = Wosa.Character.Day()
```

```Markdown
local month = Wosa.Character.Month()
```

```Markdown
local year = Wosa.Character.Year()
```

```Markdown
local gender = Wosa.Character.Gender()
```

```Markdown
local drivers_license = Wosa.Character.Drivers()
```

```Markdown
local truck_license = Wosa.Character.Truck()
```

```Markdown
local air_license = Wosa.Character.Air()
```

```Markdown
-- Desc: Not even used lol... *yet*

local boat_license = Wosa.Character.Boat()
```

```Markdown
local firearm_license = Wosa.Character.Firearm()
```

```Markdown
local thirst = Wosa.Character.Thirst()
```

```Markdown
local hunger = Wosa.Character.Hunger()
```

#### Phone

```Markdown
-- Desc: Checks if Mobile-Data in the phone in the menu is enabled.

isMobileDataEnabled = Wosa.Character.Phone.MobileData()
```

#### Appearance

```Markdown
-- Desc: Load the appearance directly from the database and then set it to your character, stuff such as heritage, face stuff etc and clothes.

Wosa.Character.Appearance.Load()
```

```Markdown
-- Desc: Save what your currently wearing directly to the database.

Wosa.Character.Appearance.Save()
```

```Markdown
-- Save the client cached data to the database, Cache the appearance with "Wosa.Character.Appearance.SaveToLocal()".

Wosa.Character.Appearance.SaveLocalToDB()
```

```Markdown
-- Save your current appearance to the client cache, This does get "cleared" once you load something from database, save another time or leave the server.

Wosa.Character.Appearance.SaveToLocal()
```

```Markdown
-- Desc: Load from the local cache that you saved to by using the native "Wosa.Character.Appearance.SaveToLocal()".

Wosa.Character.Appearance.LoadFromLocal()
```

#### Alcohol

```Markdown
-- Can't remember the proper amounts, but would guess its way under 1.0.

Wosa.Character.Alcohol.Add(Amount --[[ float ]])
```

```Markdown
-- Get the current alcohol level in the blood, This can be a good way to see how much you should add to make it somewhat legit.

local amount = Wosa.Character.Alcohol.Get()
```

```Markdown
-- Set the alcohol level to a set point.

Wosa.Character.Alcohol.Set(Amount --[[ float ]])
```

#### Job

```Markdown
Wosa.Character.Job.Set(JobName --[[ string ]], Salary --[[ int ]], JobNameLabel --[[ string ]])
```

```Markdown
local job = Wosa.Character.Job.Get()
```

```Markdown
-- Basically sets you back to "Civilian".

Wosa.Character.Job.Clear()
```

#### Faction

```Markdown

```

```Markdown

```

```Markdown

```
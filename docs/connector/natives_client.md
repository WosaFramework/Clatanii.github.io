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
-- Desc: Download your faction, needs to be downloaded so it can be cached

local rank = Wosa.Character.Job.Faction.Download(JobName --[[ string ]])
```

```Markdown
-- Desc: Gets the rank, Use this after you have downloaded for the first time.

local rank = Wosa.Character.Job.Faction.Rank(JobName --[[ string ]])
```

```Markdown
-- Desc: Gets the sub rank, like a callsign or similar, can be used for anything.

local subRank = Wosa.Character.Job.Faction.SubRank(JobName --[[ string ]])
```

#### Inventory

```Markdown
local inventory = Wosa.Character.Inventory.Get()
```

```Markdown
local cash = Wosa.Character.Inventory.Cash()
```

#### Players

```Markdown
local player = Wosa.Game.ClosestPlayer()
```

```Markdown
local players = Wosa.Game.Players()
```

```Markdown
local playersInArea = Wosa.Game.PlayersArea()
```

#### Vehicle

```Markdown
local fuel = Wosa.Game.Vehicle.GetFuel(Vehicle --[[ int ]])
```

```Markdown
Wosa.Game.Vehicle.SetFuel(Vehicle --[[ int ]], Amount --[[ int ]])
```

```Markdown
local haveAnyExtras = Wosa.Game.Vehicle.HaveExtras(Vehicle --[[ int ]])
```

```Markdown
-- Desc: Convert the vehicle into a table, can be used to store the vehicle in the database etc.

local data = Wosa.Game.Vehicle.ToData(Vehicle --[[ int ]])
```

```Markdown
local vehicle = Wosa.Game.Vehicle.CreateFromData(Data --[[ table ]], X --[[ int ]], Y --[[ int ]], Z --[[ int ]], H --[[ int ]], DontNetwork --[[ bool ]], SpecialData --[[ table ]])
```

```Markdown
local vehicle = Wosa.Game.Vehicle.Create(VehicleName --[[ string ]], Coords --[[ vector3/vector4/table ]], Data --[[ table ]], Network --[[ bool ]], Heading --[[ int ]])
```

```Markdown
local cruiseEnabled = Wosa.Game.Vehicle.isCruiseEnabled()
```

```Markdown
Wosa.Game.Vehicle.Engine(Vehicle --[[ int ]])
```

#### Vehicle Flags

```Markdown
--[[
    ENUM TYPES (USE INT)
	1 = DISABLE_GARAGE_STORAGE_FOR_VEHICLE
	2 = DISABLE_LS_CUSTOMS_FOR_VEHICLE

    You can create own ones of course but these are the official.
]]
```

```Markdown
Wosa.Game.Vehicle.Flag.Set(Vehicle --[[ int ]], Flag --[[ int ]])
```

```Markdown
Wosa.Game.Vehicle.Flag.Remove(Vehicle --[[ int ]], Flag --[[ int ]])
```

```Markdown
Wosa.Game.Vehicle.Flag.ClearAll(Vehicle --[[ int ]])
```

```Markdown
Wosa.Game.Vehicle.Flag.Get(Vehicle --[[ int ]], Flag --[[ int ]])
```

```Markdown
--[[
    Example:

    Wosa.Game.Vehicle.Flag.Set(vehicle, 3)

    if Wosa.Game.Vehicle.Flag.Get(vehicle, 3) then
        print('Flag exists!')
    end
]]
```


#### Request

```Markdown
Wosa.Game.Request.Dict(Dict --[[ string ]])
```

```Markdown
Wosa.Game.Request.Walk(Dict --[[ string ]])
```

```Markdown
Wosa.Game.Request.Ped(PedModelName --[[ string ]])
```

```Markdown
-- Desc: This is hopefully gonna get removed soon so use "Wosa.Game.Request.Model" instead as that supports both hash and model name hehe now.

Wosa.Game.Request.ModelHash(ModelHash --[[ string ]])
```

```Markdown
Wosa.Game.Request.Model(Model --[[ string ]])
```

#### Ped

```Markdown
-- Desc: Revives your ped if your dead.

Wosa.Game.Ped.Revive()
```

``` Markdown
-- Desc: Respawn your ped if your dead.

Wosa.Game.Ped.Respawn()
```

```Markdown
Wosa.Game.Ped.Create(PedName --[[ string ]], Coords --[[ vector3/vector4/table ]], Data --[[ table ]], Network --[[ bool ]], Heading --[[ int ]])
```

```Markdown
-- Desc: gotta have a EUP file loaded into your resource. Take a look at how the police job did it.

Wosa.Game.Ped.LoadEUP(EUPOutfit --[[ string ]])
```

```Markdown
Wosa.Game.Ped.Clothing(Arms --[[ int ]], Arms_tex --[[ int ]], Undershirt --[[ int ]], Undershirt_tex --[[ int ]], Top --[[ int ]], Top_tex --[[ int ]], Pants --[[ int ]], Pants_tex --[[ int ]], Shoes --[[ int ]], Shoes_tex --[[ int ]], Neck --[[ int ]], Neck_tex --[[ int ]])
```

```Markdown
-- Desc: The "OnlyIf" bool can be used so only if "OnlyIf" is true will it get set etc, it is kinda logical once you play around with it.

Wosa.Game.Ped.Cuff(Cuff --[[ bool ]], OnlyIf --[[ bool ]])
```

```Markdown
local isCuffed = Wosa.Game.Ped.isCuffed()
```

```Markdown
-- Desc: The "Source" is the "dragger" so to say.

Wosa.Game.Ped.Drag(Drag --[[ bool ]], Source --[[ int ]])
```

```Markdown
-- Desc: Seats your ped.

Wosa.Game.Ped.Seat()
```

```Markdown
Wosa.Game.Ped.UnSeat()
```

```Markdown
-- Desc: Search a player, you will get up a little menu as well.

Wosa.Game.Ped.Search(Player --[[ int ]])
```

```Markdown
-- Desc: If your ped is giving up by putting up the hands etc.

local surrendering = Wosa.Game.Ped.GivenUp()
```

#### Weapon

```Markdown
-- Desc: Can get the weapon table by returning "Wosa.Game.Ped.Weapon.Get()".

Wosa.Game.Ped.Weapon.Set(WeaponData --[[ table ]])
```

```Markdown
local weaponData = Wosa.Game.Ped.Weapon.Get()
```

#### Camera

```Markdown
-- Desc: "Extra_data" can be "{new_fov = 50.0}" etc and/or "{fade = true}".

Wosa.Game.Camera.View(X --[[ int ]], Y --[[ int ]], Z --[[ int ]], RX --[[ int ]], RY --[[ int ]], RZ --[[ int ]], Extra_data --[[ table ]])
```

```Markdown
-- Desc: Animate a camera slide between two coords. Yes I know its retarded should be vec3 coords instead heh. "Extra_data" used the same as above, Only thing extra is that you can use "{skip = true}" to skip the "wait until no camera is active thing".

Wosa.Game.Camera.Animated(X --[[ int ]], Y --[[ int ]], Z --[[ int ]], RX --[[ int ]], YX --[[ int ]], ZX --[[ int ]], X2 --[[ int ]], Y2 --[[ int ]], Z2 --[[ int ]], RX2 --[[ int ]], RY2 --[[ int ]], RZ2 --[[ int ]], Duration --[[ int ]], Extra_data --[[ table ]])
```

```Markdown
-- Desc: Stop all scripting cameras.

Wosa.Game.Camera.StopAll()
```

#### Screen

```Markdown
-- Desc: You can leave "ShowType" nil or anything, but you can however *set* it if you choose, its for the native "EndTextCommandBusyspinnerOn".

Wosa.Game.Screen.Wheel(ShowText --[[ string ]], ShowTime --[[ int ]], ShowType --[[ int ]])
```

```Markdown
Wosa.Game.Screen.HelpTextTimer(Text1 --[[ string ]], Text2 --[[ string ]], Text3 --[[ string ]], Duration --[[ int ]])
```

```Markdown
Wosa.Game.Screen.HelpText(Text --[[ string ]])
```

```Markdown
Wosa.Game.Screen.MissionText(Text --[[ string ]], Duration --[[ int ]])
```

```Markdown
Wosa.Game.Screen.Notification(Text --[[ string ]])
```

```Markdown
local input = Wosa.Game.Screen.Input(TextEntry --[[ string ]], ExampleText --[[ string ]], MaxStringLenght --[[ int ]])
```

```Markdown
Wosa.Game.Screen.Text(X --[[ float ]], Y --[[ float ]], Width --[[ float ]], Height --[[ float ]], Scale --[[ float ]], Text --[[ string ]], R --[[ int ]], G --[[ int ]], B --[[ int ]], A --[[ int ]], Font --[[ int ]], Centre --[[ bool ]])
```

```Markdown
Wosa.Game.Screen.Text3DTimer(X --[[ float ]], Y --[[ float ]], Z --[[ float ]], Text --[[ string ]], Ms --[[ int ]])
```

```Markdown
Wosa.Game.Screen.Text3D(X --[[ float ]], Y --[[ float ]], Z --[[ float ]], Text --[[ string ]])
```

#### Hud

```Markdown
local isHudDisplayed = Wosa.Game.Screen.Hud.Active()
```

```Markdown
-- Desc: Run this each tick to block the hud from wosa and other stuff such as map.

Wosa.Game.Screen.Hud.Block()
```

```Markdown
Wosa.Game.Screen.Hud.Configure(HideFuel --[[ bool ]], HideThirst --[[ bool ]], HideHunger --[[ bool ]])
```

```Markdown
Wosa.Game.Screen.Hud.NewTextBar(Title --[[ string ]], Text --[[ string ]], Pos --[[ int ]])
```

```Markdown
local hideFuel, hideThirst, hideHunger = Wosa.Game.Screen.Hud.GetSettings()
```

```Markdown
-- Will only work for official wosa resources sadly unless you modify this native.

local anyMenuOpened = Wosa.Game.Screen.Hud.AnyMenuOpened()
```

#### World Instance

```Markdown
local WorldID = Wosa.Game.World.Get()
```

```Markdown
Wosa.Game.World.Set(WorldID --[[ id ]])
```

```Markdown
-- Desc: Sets back to the default world.

Wosa.Game.World.Clear()
```

#### Scaleform

```Markdown
Wosa.Game.Scaleform.Announcement(Time --[[ int ]], Header --[[ string ]], Text --[[ string ]])
```

#### Atc

```Markdown
Wosa.Game.Atc.SetFlightMode(Mode --[[ int? ]], Callsign --[[ string ]], Original_airport --[[ string ]], Atc_header --[[ string ]], Vehicle -- [[ int ]])
```

```Markdown
Wosa.Game.Atc.PreSetAtc(Freq --[[ float ]], Freqfake --[[ float ]], Stationary --[[ bool ]])
```

```Markdown
-- Desc: Disable the ATC window.

Wosa.Game.Atc.DisableWindow(bool --[[ bool ]])
```

```Markdown
local vehicle = Wosa.Game.Atc.Aircraft()
```

```Markdown
local isStationary = Wosa.Game.Atc.Stationary()
```

```Markdown
local freq = Wosa.Game.Atc.Freq()
```

```Markdown
local airport = Wosa.Game.Atc.Airport()
```

```Markdown
local gate = Wosa.Game.Atc.Gate()
```

```Markdown
local runway = Wosa.Game.Atc.GetTaxiToRunway()
```

#### VehicleAI version-1.0
Eh, works fine for more basic stuff and for a few vehicles at the same time (1-3) but the upcoming 2.0 version will be better ;p

```Markdown
Wosa.Game.Vehicle.AI.Attach(entity --[[ int ]], function(vehicle --[[ int ]], data --[[ table ]])

end)
```

```Markdown
Wosa.Game.Vehicle.AI.Avoidance(data --[[ table ]], vehicle --[[ int ]], speed --[[ float ]], function(vehicle --[[ int ]], data --[[ table ]], speed --[[ float ]])

end)
```

```Markdown
Wosa.Game.Vehicle.AI.Task(data --[[ table ]], vehicle --[[ int ]], task --[[ string ]], speed --[[ float ]], function(data --[[ table ]], vehicle --[[ int ]], task --[[ string ]])

end)
```

#### Other

```Markdown
-- Disable/Enable the homescreen button in the character menu.

Wosa.Misc.Homescreen(CanUse --[[ bool ]])
```

```Markdown
-- Return the keybind config from wosa_core (https://github.com/WosaFramework/Framework/blob/master/wosa_core/scripting/scripting_configs/Keybinds_config.lua).

local keybinds = Wosa.Misc.Keybinds()
```

```Markdown
local languages = Wosa.Translate.Get()
```

```Markdown
local current_language = Wosa.Translate.Language()
```
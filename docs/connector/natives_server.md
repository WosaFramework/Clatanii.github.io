# Server Natives


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

local PID = P_API.User.UserFromLicense(License --[[ string ]])
```

#### AntiCheat

```Markdown
-- Desc: This native can be used to ban people from "event" abusing currently. Do not use this native for regular banning as this system will and might work differently.

Wosa.Character.AntiCheat.Ban(PID --[[ int ]], Type --[[ string ]], Custom --[[ string ]])

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
-- Desc: 


```
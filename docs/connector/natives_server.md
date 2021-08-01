# Server-API Natives

Functions that are attached to the server-api set. This page is automated from [public_api_server.lua](https://github.com/WosaFramework/Framework/blob/master/wosa_core/scripting/scripting_api/resource_api_v2/public_api_server.lua).

#### »  Tools Functions

###### ╚  General

```Markdown 			
**formated = Wosa.Tools.ConvertSQLDateToLuaFormat(unix)**

Returnal:
• (*string*) **formated:** the time in a new readable "design".	
	
Parameters:
• (*number*) **unix:** the time and date in unix measurment.	

Used to convert often SQL timestamps to a "readable" date.	
```
			
#### »  Translate Functions

###### ╚  General

```Markdown 			
**languages = Wosa.Translate.Get()**

Returnal:
• (*table*) **languages:** the language data from the core.	
```
			
```Markdown 			
**language = Wosa.Translate.Language()**

Returnal:
• (*string*) **language:** the current language used.	
```
			
#### »  User Functions

###### ╚  Permission 

```Markdown 			
**Wosa.User.Permission.Set(player, rank)**
	
Parameters:
• (*int*) **player:** the player id.	
• (*string*) **rank:** the rank you want the player to receive.	

The rank is required to be taken out of the [rank config](https://github.com/WosaFramework/Framework/blob/master/wosa_core/scripting/scripting_configs/Ranks_config.lua#L13) in your server.	
```

```Markdown 			
**rank = Wosa.User.Permission.Get(player)**

Returnal:
• (*string*) **rank:** the permission level of the user, taken from session library.	
	
Parameters:
• (*int*) **player:** the player id.	
```

###### ╚  General

```Markdown 			
**Wosa.User.Ban(player, reason)**
	
Parameters:
• (*int*) **player:** the player id.	
• (*string*) **reason:** the stated reason for the ban.	

Permanent ban a user from the server.	
```
			
```Markdown 			
**license = Wosa.User.License(player)**

Returnal:
• (*string*) **license:** license identifier (r* license) of the user.	
	
Parameters:
• (*int*) **player:** the player id.	
```
			
```Markdown 			
**Wosa.User.Kick(player, reason)**
	
Parameters:
• (*int*) **player:** the player id.	
• (*string*) **reason:** the stated reason for the kick.	

Kick a user off from the session, Will be kicked by SYSTEM and will be logged in the users history.	
```
			
```Markdown 			
**player = Wosa.User.UserFromLicense(license)**

Returnal:
• (*int*) **player:** the player id.	
	
Parameters:
• (*string*) **license:** license identifier (r* license) of the user.	

Often used when the player id is unkown, will return nil if the player is not active on the session.	
```
			
```Markdown 			
**id = Wosa.User.CurrentDB(player, type)**

Returnal:
• (*string*) **id:** Get back the returned database table name for the current selected character.	
	
Parameters:
• (*int*) **player:** the player id.	
• (*string*) **type:** the type of character "id", "i" is inventory and "c" is character type, will just return character_? or inventory_?, used to fetch stuff from database. Valid ranges are ?_1-?_3	

Used to retrieve the inventory or/and database "id" to do database calls and fetches as data is either stored on "inventory/character_1/2/3", which is fucking stupid but it is what it is.	
```
			
#### »  Character Functions

###### ╚  Ped 

```Markdown 			
**Wosa.Character.Ped.ReviveAnim(user, heading)**
	
Parameters:
• (*int*) **user:** the player id.	
• (*number*) **heading:** The heading of the target	
```

###### ╚  Inventory 

```Markdown 			
**data = Wosa.Character.Inventory.Get(user)**

Returnal:
• (*table*) **data:** the inventory table from database_?.	
	
Parameters:
• (*int*) **user:** the player id.	
```

###### ╚  Item
```Markdown 			
**Wosa.Character.Inventory.Item.Remove(item_id, user, item_name)**
	
Parameters:
• (*int*) **item_id:** The item id	
• (*int*) **user:** the player id.	
• (*string*) **item_name:** The item name, NOT DISPLAY NAME	

If you want to remove a specific item linked to an ID you can leave "item_name" as nil. If you want to do vice versa you can leave "item_id" as nil.	
```

```Markdown 			
**exist = Wosa.Character.Inventory.Item.Exist(user, item_name)**

Returnal:
• (*bool*) **exist:** If the item exists from the fetch.	
	
Parameters:
• (*int*) **user:** the player id.	
• (*string*) **item_name:** The item name	
```

```Markdown 			
**Wosa.Character.Inventory.Item.RemoveAllCustom(user)**
	
Parameters:
• (*int*) **user:** the player id.	

Removes all items that can be dropped from the character, objects like id-card and pocket cash wont be removed.	
```

```Markdown 			
**Wosa.Character.Inventory.Item.Add(item_data, user, license)**
	
Parameters:
• (*table*) **item_data:** The item data, should be setup like the inventory_? struc in db.	
• (*int*) **user:** the player id.	
• (*string*) **license:** license identifier (r* license) of the user.	
```

###### ╚  Money 

```Markdown 			
**Wosa.Character.Money.Remove(player, method, amount)**
	
Parameters:
• (*int*) **player:** the player id.	
• (*string*) **method:** the payment method.	
• (*number*) **amount:** the amount of money.	

Possible payment methods are RE_VanillaC, RE_BusinessC, RE_Cash.	
```

```Markdown 			
**balance = Wosa.Character.Money.Balance(player, method)**

Returnal:
• (*number*) **balance:** the balance on the payment method.	
	
Parameters:
• (*int*) **player:** the player id.	
• (*string*) **method:** the payment method.	

Possible payment methods are RE_VanillaC, RE_BusinessC, RE_Cash.	
```

```Markdown 			
**Wosa.Character.Money.RemoveFromAny(player, amount)**
	
Parameters:
• (*int*) **player:** the player id.	
• (*number*) **amount:** the amount of money.	

Will add money to any avaliable "payment method" as credit card or cash.	
```

```Markdown 			
**methods = Wosa.Character.Money.Methods(player, amount)**

Returnal:
• (*table*) **methods:** In a table form they are listed from index 1 to 3, 1 (RE_VanillaC), 2 (RE_BusinessC), 3 (RE_Cash).	
	
Parameters:
• (*int*) **player:** the player id.	
• (*number*) **amount:** the amount of money.	

Will not return the amount of cash on any of the payment methods, will just see if it actually exists or not.	
```

```Markdown 			
**Wosa.Character.Money.AddToAny(player, amount)**
	
Parameters:
• (*int*) **player:** the player id.	
• (*number*) **amount:** the amount of money.	
```

```Markdown 			
**Wosa.Character.Money.Set(player, method, amount)**
	
Parameters:
• (*int*) **player:** the player id.	
• (*string*) **method:** the payment method.	
• (*number*) **amount:** the amount of money.	

Possible payment methods are RE_VanillaC, RE_BusinessC, RE_Cash.	
```

```Markdown 			
**Wosa.Character.Money.Add(player, method, amount)**
	
Parameters:
• (*int*) **player:** the player id.	
• (*string*) **method:** the payment method.	
• (*number*) **amount:** the amount of money.	

Possible payment methods are RE_VanillaC, RE_BusinessC, RE_Cash.	
```

###### ╚  Faction 

```Markdown 			
**Wosa.Character.Faction.Remove(user, license)**
	
Parameters:
• (*int*) **user:** the player id.	
• (*string*) **license:** license identifier (r* license) of the user.	

Will remove the user from their current faction, the user is required to relogg.	
```

```Markdown 			
**Wosa.Character.Faction.Add(faction_rank_extra, faction_rank, user, job_name)**
	
Parameters:
• (*string*) **faction_rank_extra:** is not required, just if you want to store extra faction rank data such as callsign or something.	
• (*string*) **faction_rank:** the so called faction rank.	
• (*int*) **user:** the player id.	
• (*?*) **job_name:** !!deprecated!! not used anymore, leave it as anything you want, wont matter :P	
```

```Markdown 			
**Wosa.Character.Faction.Update(license, faction_rank_extra, faction_rank, user, job_name)**
	
Parameters:
• (*string*) **license:** license identifier (r* license) of the user.	
• (*string*) **faction_rank_extra:** is not required, just if you want to store extra faction rank data such as callsign or something.	
• (*string*) **faction_rank:** the so called faction rank.	
• (*int*) **user:** the player id.	
• (*?*) **job_name:** !!deprecated!! not used anymore, leave it as anything you want, wont matter :P	
```

###### ╚  Phone 

```Markdown 			
**Wosa.Character.Phone.AutomatedMessage(sender_number, receiver_number, user, message)**
	
Parameters:
• (*string*) **sender_number:** the number that will be "from the number".	
• (*string*) **receiver_number:** the number that will receive the message.	
• (*int*) **user:** the player id.	
• (*string*) **message:** the message the receiver will receive.	
```

###### ╚  AntiCheat 

```Markdown 			
**Wosa.Character.AntiCheat.Ban(player, data, type)**
	
Parameters:
• (*int*) **player:** the player id.	
• (*string*) **data:** data for the "type", often refeered to the "reason" but in other words.	
• (*string*) **type:** the anti-cheat "crime type" they commited.	

Permanent ban a user for being caught cheating in some way. Currently only event cheat abuses can be registered, "type" would be "event" and "data" would be event name. DOES NOT ACTUALLY DETECT THE CHEAT FOR YOU, ONLY TAKES CARE OF THE BAN.	
```

###### ╚  General

```Markdown 			
**data = Wosa.Character.DataFromName(firstname, lastname)**

Returnal:
• (*table*) **data:** character data.	
	
Parameters:
• (*string*) **firstname:** the character firstname.	
• (*string*) **lastname:** the character lastname.	

Character "data" is straight from database (character_?), should be looped or indexed correctly as there might be more than one result(s).	
```
			
```Markdown 			
**data = Wosa.Character.All()**

Returnal:
• (*table*) **data:** character data.	
```
			
```Markdown 			
**Wosa.Character.AddLicensePoints(user, points)**
	
Parameters:
• (*int*) **user:** the player id.	
• (*int*) **points:** Add license points to the drivers license.	

This function does not seem to be real time synced, meaning the player would have to relogg to see the actions on their end for now.	
```
			
```Markdown 			
**data = Wosa.Character.Data(user)**

Returnal:
• (*table*) **data:** character data.	
	
Parameters:
• (*int*) **user:** the player id.	
```
			

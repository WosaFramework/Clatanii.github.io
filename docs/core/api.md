# Base Functions
The most *base* functions, Functions that are related directly to the core of the framework. Should be used with caution.

#### Classes
Classes are used within the core API to isolete different classes and code from each other.

```Markdown
-- Set: Shared
-- Desc: How to register a class and use it.

API.TEST_CLASS = {NewAPIClass('MY TEST CLASS')}

function API.TEST_CLASS.MY_FUNC()
    print('hello!')
end
```

```Markdown
-- Set: Server
-- Desc: Returns all of the classes currently registered, Classes get registered on API startup.
local classes = API.GET_CURRENT_REGISTERED_CLASSES()

-- Example code
for i, item in ipairs(classes) do
    print('Class ID: '..item.id..', Class Label: '..item.class)
end
```

#### Power Access
For the framework to properly boot up and run, API power needs to granted. The **ServerNetV2** system is closed source and is only available to project developers to keep the framework secure. Destroying the `API` table on server or client or both will cause servere issues and will most likley crash your server all togheter.

```Markdown
-- Set: Server
-- Desc: Manually shut down the API, will result in everything server sided breaking.

-- @blockHang: Setting this to true will make the server thread not freeze/hang.
API_MANUAL_SHUTDOWN(blockHang, --[[ bool ]])
```

```Markdown
-- Set: Server
-- Desc: Run a "power check" that will shut down the API if `api_power` is disabled

API_LOCAL_POWER_CHECK()

-- Extra Note: To toggle the power prior to running this function use `API.CONFIG.api_power = status -- [[ int ]]`.
```

```Markdown
-- Set: Server
-- Desc: Get general information about the API system.

local data = API.GET_STATUS()

-- Example code
print('Status: '..data.version)
print('Power: '..data.power)
print('Ghost: '..data.ghost)
```

#### Memory
Certain memory functions within Lua can be used to keep down the memory usage.

```Markdown
-- Set: Shared
-- Desc: Collect "garbage", Straight from Lua.

API.COLLECT_GARBAGE()
```

```Markdown
-- Set: Client
-- Desc: Get the current usage in kb's from the wosa_core client.

API.GET_C_MEM_USAGE()
```

#### Message
The API features a message/log system were you can log different actions to console, discord or both.

```Markdown
-- Set: Server
-- Desc: Send a server to either the s-console or the discord webhook or both.

-- @data_type = 'Error', 'Info', 'Success', 'Warning'(Overwrites Ghostmode / RULES: ->>), 'Overwrite'(Overwrites ghostmode / RULES: ONLY TO BE USED ON VERY IMPORTANT THINGS TO NOT ABUSE IT'S 'POWERS')
-- @data_str = The console message/string.
-- @blockBotMessage = If you want to block the discord bot message to display.
-- @data_bot_str = The discord bot message.
-- @Header = Header for the discord message, optional.
API.MESSAGE(--[[ str ]] data_type, --[[ str ]] data_str, --[[ bool ]] blockBotMessage, --[[ str ]] data_bot_str, --[[ str ]] Header)

-- Example code (only s-console message).
API.MESSAGE('Error', 'The API core could not authenticate power access, Please contact a developer...')
```
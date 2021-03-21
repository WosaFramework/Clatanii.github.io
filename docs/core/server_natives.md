# Server Functions

Core server natives used within the resource wosa_core.

```Markdown
-- CLEAR ALL TABLES FROM DATABASE CONNECTED TO CHARACTER
-- @source = source / ID
-- @source_level = player level to check against @level
-- @level = permission level to check against
-- @returns = true or false depending on if user can procceed with their rank

API.NATIVE.REMOVE_CHARACTER_FROM_DATABASE(source, inv_table, phoneNumber)
```

```Markdown
-- OFFICIAL REGISTERED RANKS AND DEFFERAL RETURN FUNCTION
-- @source = source / ID
-- @source_level = player level to check against @level
-- @level = permission level to check against
-- @returns = true or false depending on if user can procceed with their rank

local bool = API.NATIVE.COMPARE_RANK_AND_RETURN(source, source_level, level)
```

```Markdown
-- IS THE USER ACTIVE ON THE SESSION?

local bool = API.NATIVE.IS_USER_ACTIVE_ON_SESSION(identifier)
```

```Markdown
-- CHECK IF THE USER IS ONLINE WITH A SPECIFIC CHARACTER

local bool = API.NATIVE.IS_USER_ACTIVE_WITH_CHARACTER_ON_SESSION(identifier, inv_table)
```

```Markdown
API.NATIVE.GET_SOURCE_FROM_IDENTIFIER(identifier)
```

```Markdown
-- RETURN THE CHARACTER IDENTIFIER (R* LICENSE)

ID = API.NATIVE.GET_SOURCE_FROM_IDENTIFIER(identifier)
```

```Markdown
local identifier = API.NATIVE.GET_PLAYER_IDENTIFIER(type, source)
```

```Markdown
-- SEND INFO MESSAGE TO PLAYER (FROM SERVER)

API.NATIVE.SEND_INFO_MESSAGE_CLIENT(rec, message)
```

```Markdown
-- GET ALL CHARCTERS FROM DATABASE

local characters = API.NATIVE.GET_ALL_CHARACTERS()
```

```Markdown
-- GET CHARACTER DATA FROM FIRST/LAST-NAME

local characters = API.NATIVE.GET_CHARACTER_DATA_FROM_NAME(firstname, lastname)
```

```Markdown
local formatted = API.NATIVE.RETURN_COMMA_VALUE(amount)
```

```Markdown
local new = API.NATIVE.PAIRS_BY_KEYS(t, f)
```

```Markdown
local date = API.NATIVE.CONVERT_SQL_DATE_TO_LUA_DATE(Unix)
```
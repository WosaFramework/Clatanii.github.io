# Client Functions

Core client natives used within the resource wosa_core.


```Markdown
-- FREEZE ALL MOVEMENTS + PED //Toggle not each tick

API.NATIVE.FREEZE_ALL_MOVEMENT(bool)
```

```Markdown
-- CALL CAMERA VIEW (DEFAULT SCRIPTED CAMERA) ONLY

API.NATIVE.CREATE_CAMERA(x, y, z, rx, ry, rz, extra_data)
```

```Markdown
-- CALL CAMERA VIEW WITH ANIMATION (2 CAMERAS) ONLY

API.NATIVE.CREATE_ANIMATED_CAMERA(x, y, z, rx, ry, rz, x2, y2, z2, rx2, ry2, rz2, duration, extra_data)
```

```Markdown
-- DESTROY ALL "FRAMEWORK" CAMERAS

API.NATIVE.DESTROY_ALL_SCRIPT_CAMERAS()
```

```Markdown
-- DESTROY SPECIFIC CAMERA, KINDA RETARDED CAUSE IT WOULD LITTERLY STOP RENDERING ANY CAMERA

API.NATIVE.DESTROY_CAMERA(cam)
```

```Markdown
-- BLOCK/HIDE HUD THIS FRAME

API.NATIVE.HIDE_HUD_THIS_TICK()
```

```Markdown
local bool = API.NATIVE.IS_HUD_HIDDEN()
```

```Markdown
-- LOADING WHEEL BOTTOM RIGHT

API.NATIVE.LOADING_WHEEL(showText, showTime, showType)
```

```Markdown
-- HELP TEXT NATIVE RIGHT UP CORNER (NEEDS TO BE CALLED ONCE)

API.NATIVE.HELP_TEXT_DUR(lineOne, lineTwo, lineThree, duration)
```

```Markdown
-- DRAW MISSION TEXT FUNCTION

API.NATIVE.MISSION_TEXT_2(m_text, showtime)
```

```Markdown
-- HELP TEXT NATIVE RIGHT UP CORNER (NEEDS TO BE CALLED EACH TICK)

API.NATIVE.HELP_TEXT_TICK(str)
```

```Markdown
-- HELP TEXT NATIVE RIGHT UP CORNER LONG (NEEDS TO BE CALLED EACH TICK)

API.NATIVE.HELP_TEXT_LONG_TICK(str1, str2, str3)
```

```Markdown
-- SHOW NOTIFICATION

API.NATIVE.NOTIFICATION(text)
```

```Markdown
local bool = API.NATIVE.DOES_VEHICLE_HAVE_EXTRAS(veh)
```

```Markdown
-- FROM VEHICLE GET DATA TO A TABLE

local data = API.NATIVE.VEHICLE_TO_DATA(veh)
```

```Markdown
-- SET OUTFIT FOR MP PED (USED FOR EUP MOSTLY BUT NOT LIMITED TO)

API.NATIVE.SET_EUP_OUTFIT(outfit)
```

```Markdown
-- CREATE A VEHICLE FROM DATA (NATIVE.VEHICLE_TO_DATA) FUNCTION

API.NATIVE.CREATE_VEHICLE_FROM_DATA(data, x,y,z,h, dontnetwork, specialData)
```

```Markdown
-- CREATE VEHICLE

API.NATIVE.CREATE_VEHICLE(vehicleName, coords, data, Network, setHeading)
```

```Markdown
API.NATIVE.REQUEST_MODEL(inp)
```

```Markdown
local bool = API.NATIVE.IS_MODEL_LOADED(inp)
```

```Markdown
-- KEY BOARD INPUT BOX

local inp = API.NATIVE.KEYBOARD_INPUT(TextEntry, ExampleText, MaxStringLenght)
```

```Markdown
-- REQUEST A PLAYER NPC/MP MODEL 

API.NATIVE.SET_PLAYER_PED(data)
```

```Markdown
-- REQUEST MP CHARACTER CLOTHING CHANGE

API.NATIVE.SET_PED_CLOTHING(arms, arms_tex, undershirt, undershirt_tex, top, top_tex, pants, pants_tex, shoes, shoes_tex, neck, neck_tex)
```

```Markdown
-- GET DATA FOR FUNCTION ^^ (JUST A TIME SAVER REALLY)

local arms_d, arms_t, undershirt_d, undershirt_t, jacket_d, jacket_t, pants_d, pants_t, shoes_d, shoes_t, neck_d, neck_t = API.NATIVE.GET_PED_CLOTHING()
```

```Markdown
-- DRAW 3D TEXT ON SCREEN

API.NATIVE.DRAW_SCREEN_TEXT(x, y, width, height, scale, text, r, g, b, a, font, centre)
```

```Markdown
-- DRAW 3D TEXT INGAME

API.NATIVE.DRAW_GAME_TEXT(x,y,z, text)
```

```Markdown
-- DRAW 3D TEXT INGAME

API.NATIVE.DRAW_GAME_TEXT_NO_BOX(x,y,z, text, _scale)
```

```Markdown
-- DRAW 3D TEXT INGAME

API.NATIVE.DRAW_GAME_TEXT_REPEAT(x,y,z, text, ms)
```

```Markdown
-- LOAD WALK STYLE

API.NATIVE.REQUEST_ANIMATION_SET(dict)
```

```Markdown
local players = API.NATIVE.GET_PLAYERS_IN_AREA_EXTRA(coords, area)
```

```Markdown
local players = API.NATIVE.GET_PLAYERS_IN_AREA()
```

```Markdown
API.NATIVE.REQUEST_ANIMATION_DICT(dict)
```

```Markdown
local vehicle_cache = API.NATIVE.GET_LOADED_VEHICLES()
```

```Markdown
local vehicle = API.NATIVE.GET_CLOSEST_VEHICLE()
```

```Markdown
local player = API.NATIVE.GET_CLOSE_PLAYER()
```

```Markdown
local players = API.NATIVE.GET_PLAYERS()
```

```Markdown
-- PRINT DEBUG COMMAND IN CONSOLE IF DEV MODE IS ACTIVE
-- print_type (int): 1 = Success, 2 = Warning, 3 = Error

-- (WILL ONLY WORK IF "framework.dev_mode"/Development mode envi is enabled)

API.NATIVE.DEBUG_PRINT(print_type, print_msg)
```

```Markdown
local formatted = API.NATIVE.RETURN_COMMA_VALUE(amount)
```

```Markdown
local new = API.NATIVE.PAIRS_BY_KEYS(t, f)
```
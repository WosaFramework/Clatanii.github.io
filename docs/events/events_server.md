# Server Events

#### Character

```Markdown
AddEventHandler('__WOSA:CHARACTER_CREATED', function(playerID, characterData)

end)
```

```Markdown
AddEventHandler('__WOSA:CHARACTER_LOADED', function(playerID, characterData)

end)
```

```Markdown
AddEventHandler('__WOSA:CHARACTER_REMOVED', function(playerID, characterData)

end)
```

#### User

```Markdown
AddEventHandler('__WOSA:SERVER:USER_CONNECTING', function(playerID, playerLicense, playerRank, isPlayerNew)

end)
```

```Markdown
AddEventHandler('__WOSA:SERVER:USER_LEAVING', function(playerID, playerLicense, playerRank, leaveReason)

end)
```
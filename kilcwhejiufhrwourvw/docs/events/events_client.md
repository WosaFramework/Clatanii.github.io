# Client Events

#### Character

```Markdown
AddEventHandler('__WOSA:ON_CHARACTER_SWITCH', function()

end)
```

```Markdown
AddEventHandler('__WOSA:ON_CHARACTER_LOAD', function()

end)
```

```Markdown
AddEventHandler('__WOSA:ON_CHARACTER_PRELOAD', function()

end)
```

```Markdown
AddEventHandler('__WOSA:ON_NEW_CHARACTER', function()

end)
```

```Markdown
AddEventHandler('__WOSA:ON_OFFDUTY', function(job)

end)
```

#### Inventory

```Markdown
AddEventHandler('__WOSA:INVENTORY_UPDATE', function(inv_data)

end)
```

```Markdown
AddEventHandler('__WOSA:ITEM_USE', function(itemName, itemDisplayName, itemDatabaseID, itemRemovedOnUse)

end)
```

```Markdown
AddEventHandler('__WOSA:ITEM_ADD', function(itemName, itemDisplayName)

end)
```

```Markdown
AddEventHandler('__WOSA:ITEM_GIVE', function(receiverPlayerID, itemName, itemDisplayName, itemDatabaseID)

end)
```

```Markdown
AddEventHandler('__WOSA:ITEM_DROP', function(itemName, itemDisplayName, itemDatabaseID)

end)
```

```Markdown
AddEventHandler('__WOSA:ITEM_PICKUP', function(coordsOfItem, itemName, itemDisplayName)

end)
```

#### Phone

```Markdown
AddEventHandler('__WOSA:911_CALL', function(CallerPlayerID, coords, callInfo, serviceCalled, callID)

end)
```

```Markdown
AddEventHandler('__WOSA:SERVICE_CALL', function(CallerPlayerID, coords, callInfo, serviceCalled, callID)

end)
```
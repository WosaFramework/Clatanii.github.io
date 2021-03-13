#### Classes
Classes are used within the core API to isolete different classes and code from each other.

```
-- Set: Server
-- Desc: Returns all of the classes currently registered, Classes get registered on API startup.
local classes = API.GET_CURRENT_REGISTERED_CLASSES()

-- Example code
for i, item in ipairs(classes) do
    print('Class ID: '..item.id..', Class Label: '..item.class)
end
```
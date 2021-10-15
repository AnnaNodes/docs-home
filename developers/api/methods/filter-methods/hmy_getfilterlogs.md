---
description: hmy_getFilterLogs
---

# hmy_getFilterLogs

Returns an array of all logs matching filter with given id.

**Parameters**

1. `QUANTITY` - The filter id.

**Example Parameters**

```
params: [
  "0x16" // 22
]
```

**Returns**

See hmy_getFilterChanges

**Example**

```
// Request
curl -X POST --data '{"jsonrpc":"2.0","method":"hmy_getFilterLogs","params":["0x16"],"id":74}'
```

Result see hmy_getFilterChanges

# Repl.it Database client

This is a Deno port of [the official client for Node](https://github.com/replit/database-node). It took like 5 minutes to port, so props to the repl.it team!

## Get started

```typescript
import { Client } from "https://deno.land/x/replit_database/mod.ts";
const client = new Client();
await Client.set("key", "value");
let key = await Client.get("key");
console.log(key);
```

## Docs

### `class Client(String key?)`

The key is the optional custom URL.

#### Native Functions

These functions are specified in the repl.it DB.

> `get(String key, Object options?)`

Gets a key. Returns Promise.

```typescript
Client.get("key", { raw: false }).then(console.log);
```

> `set(String key, Any value)`

Sets a key to value. Returns Client.

> `delete(String key)`

Deletes a key. Returns Client.

> `list(String? prefix)`

Lists all of the keys, or all of the keys starting with `prefix` if specifed.

#### Dynamic Functions

These functions have been added by me.

> `empty()`

Clears the database. Returns Client

> `getAll()`

Get all key/value pairs and return as an object.

> `setAll(Object obj)`

Sets the entire database through a key/value object. Returns Client

> `deleteMultiple(...String args)`

Deletes multiple keys. Returns client.

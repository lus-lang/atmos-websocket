# websocket

Speaks the WebSocket protocol of RFC 6455, as a server on `web` or `network.serve` and as a client.

```lus nocheck
local web = require("https://atmosp.here/2.0/web.lus")
local ws = require("https://atmosp.here/2.0/websocket.lus")

local app = web.app()
app:get("/echo", ws.route(function(conn)
    for message in conn:messages() do
        conn:send(message)
    end
end))
```

The package requires Lus 2.0. It declares the permission network:tcp, which only `websocket.connect` uses. It calls no `pledge` of its own, so the program that loads it keeps control of its permissions.

The reference is in the doc comments of `websocket.lus`. Run `lus doc websocket.lus` to print it.

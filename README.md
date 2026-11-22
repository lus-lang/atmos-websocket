# websocket

`websocket` implements the WebSocket protocol of RFC 6455 for servers on `web` or `network.serve` and for clients of `ws://` and `wss://` URLs.

The following example adds an endpoint to a web application that sends every message back to its client.

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

The package requires Lus 2.0 and declares the permission `network:tcp`, which only `websocket.connect` uses. It never calls `pledge`, so the program that loads it keeps control of its permissions.

The reference is in the doc comments of `websocket.lus`, which `lus doc websocket.lus` prints.

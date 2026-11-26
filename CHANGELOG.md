# Changelog

## 1.0.0

**Release date:** TBD

Version 1.0.0 is the first release of `websocket`, which runs on Lus 2.0.

- Added the `websocket` package.
  - `websocket.route`: Returns a handler for `web` or `network.serve` that accepts WebSocket connections.
  - `websocket.connect`: Opens a client connection to a `ws://` or `wss://` URL.
  - `websocket.accept_key`: Returns the `Sec-WebSocket-Accept` value for a `Sec-WebSocket-Key`.
  - `websocket.iserror`: Returns true for an error object that `websocket` raised.
  - `conn:receive` and `conn:messages`: Wait for the next message, or iterate over the messages until the connection closes.
  - `conn:send` and `conn:ping`: Send a text or binary message, or a ping.
  - `conn:close`: Sends a close frame and closes the connection.

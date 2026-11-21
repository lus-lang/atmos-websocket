# AGENTS.md

This repository, `lus-lang/atmos-websocket`, is the `websocket` package of the atmosphere registry. Programs load it with `require("https://atmosp.here/2.0/websocket.lus")`.

## Scope

Speaks the WebSocket protocol of RFC 6455, as a server on `web` or `network.serve` and as a client. The public API is every function that `websocket.lus` returns in its module table. A change to that API needs a new entry in `CHANGELOG.md` and a version change in the header.

## Layout

- `websocket.lus` is the whole package. Its header doc comment carries the package metadata and the declared permissions.
- `tests/*_test.lus` are the tests. They load the package from the parent directory through `TEST_DIR`.

## Dependencies

- the stdlib `crypto` module, for client keys and masks
- web, in the tests only

The tests load `web` from a checkout of `lus-lang/atmos-web` next to this repository, so clone it into the same parent directory first.

## Commands

```sh
lus test tests          # run the tests
lus check websocket.lus     # lint
lus doc websocket.lus       # print the reference
```

## Rules

- Every public function has a doc comment that states each result and each error, following `spec/design/style.md` of the Lus repository.
- The package never calls `pledge`. A new permission is declared in the header and in the README.
- Prose has no dashes and no semicolons, and never names the Roblox Lua dialect.
- Every bug fix comes with a test that fails without it.

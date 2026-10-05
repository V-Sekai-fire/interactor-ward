# interactor-ward

A server-authoritative networked physics service for one ward, whose state is a SQLite database over a FoundationDB-backed VFS.

## What it is for

No client opens the ward's database, so authority over a body stays on the server, and a priority accumulator chooses which bodies each subscriber hears about in a tick. `queen`, a settlement game, is the ward's tenant and plays it as database transactions. The benchmarks ask how many players one core holds under a physics engine.

## Build and run

The build needs a FoundationDB client and SQLite.

```sh
cmake -B build
cmake --build build
```

`queen` prints its subcommands when run without arguments, and it needs a live cluster to start. `docker compose run --rm ci` runs the CI job against a cluster in a container.

## Licence

`LICENSE` is MIT; the source files carry Apache-2.0 SPDX headers.

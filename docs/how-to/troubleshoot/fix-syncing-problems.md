description: Fix syncing problems
<!--- END of page meta data -->

# Fix syncing problems

## Before you begin

1. Close Quiver.

1. Go to your [data directory](find-data-dir.md), and backup your `wallet.dat` file.

1. Download the [Arrow bootstrap](http://explorer.arrowchain.io/Arrow-bootstrap.rar).

1. Save the file somewhere so that you can reuse it later without needing to download it again.

## macOS

1. Delete all files except `arrow.conf`, `wallet.dat`, or `quiver-lite-wallet.dat`.

1. Unpack the contents of `Arrow-bootstrap.rar` in a temporary folder. The blocks and chainstate directories are extracted.

1. Drag and drop the blocks and chainstate folders into `~/Library/Application Support/arrow`.

1. Open Quiver, and let it sync.

## Windows

1. Delete all files except `arrow.conf`, `wallet.dat`, or `quiver-lite-wallet.dat`.

1. Unpack the contents of `Arrow-bootstrap.rar` in `%appdata%\arrow`. The blocks and chainstate directories are extracted.

1. Open Quiver, and let it sync.

## Linux

1. Delete all files except `arrow.conf` and `wallet.dat`.

1. Unpack the contents of `Arrow-bootstrap.rar` into the Quiver folder. The blocks and chainstate directories are extracted.

1. Open Quiver, and let it sync.

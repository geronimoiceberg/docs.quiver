description: Reindex
<!--- END of page meta data -->

# Reindex

If blockchain data becomes corrupt, reindex Quiver to download the complete blockchain again. Because reindexing is a time-consuming process, use this function only when it is necessary.

To reindex Quiver:

1. Close Quiver.
1. Go to your [data directory](../troubleshoot/find-data-dir.md).
1. In `arrow.conf`, add `reindex=1`, and save the change.
1. Restart Quiver. Reindexing begins.
1. After rescanning ends, remove `reindex=1` from `arrow.conf`. Otherwise, reindexing begins every time you open Quiver.

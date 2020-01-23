description: Rescan
<!--- END of page meta data -->

# Rescan

If you restored a backup version of Quiver or modified Quiver by adding new addresses or removing transactions, use the rescan function.

Rescanning explores every downloaded block, searches for transactions affecting your Quiver addresses, and updates Quiver's transaction store and balances to reflect those transactions.

To rescan Quiver:

1. Close Quiver.
1. Go to your [data directory](../troubleshoot/find-data-dir.md).
1. In `arrow.conf`, add `rescan=1`, and save the change.
1. Restart Quiver. Rescanning begins.
1. After rescanning ends, remove `rescan=1` from `arrow.conf`. Otherwise, rescanning begins every time you open Quiver.

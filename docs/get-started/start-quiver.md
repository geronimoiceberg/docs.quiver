description: Start Quiver
<!--- END of page meta data -->

# Start Quiver

To start Quiver on macOS, Windows, or Linux, open the Quiver application.

When you run Quiver for the first time, Quiver automatically does the following tasks:

* Creates `arrow.conf`, the settings file for `arrowd`, the core Arrow client software
* Downloads the required parameters for `arrowd` and configures them
* Starts an embedded `arrowd` node

If you have run Quiver previously, Quiver automatically connects to the embedded `arrowd` node.

While Quiver runs, the blockchain syncs. Depending on the hardware you use and your network conditions, syncing might last eight hours or longer.

## Monitor syncing progress

Monitor the syncing progress in the status bar at the bottom of Quiver where the number of downloaded blocks downloaded and the percentage of completion is displayed.

!!! example "Not synced"
    ![Not synced](../images/not_synced.png)

!!! example "Synced"
    ![Synced](../images/fully_synced.png)

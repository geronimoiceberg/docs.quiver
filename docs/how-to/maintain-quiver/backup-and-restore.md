description: Backup private keys and data
<!--- END of page meta data -->

# Backup and restore

Backup [one private key](#backup-one-private-key), [all your private keys](#backup-all-private-keys), or [the wallet data file](#backup-wallet-data-file). Use the backup of your `wallet.dat` file to [restore your wallet](#restore-your-wallet).

## Before you begin

Close Quiver.

## Backup one private key

1. Open the **Receive** tab.
1. Select the address whose private key you want to backup.
1. Click **Export Private Key**. The private key for the selected address is displayed in a new window.
1. Store it securely.

!!! Tip "Alternative method"

    1. On the **Balance** tab, right-click the address in the list of balances, and select **Get private key**.
    1. Store it securely.

## Backup all private keys

1. Select **File->Export all private keys**. All your private keys are displayed in a new window.
1. Store them securely.

!!! Tip "Save keys as a file"

    If you'd like to save the keys as a file, click **Save** and place them in a secure place.

## Backup wallet data file

1. Go to the [default data directory](../troubleshoot/find-data-dir.md) for your platform.
1. Make a copy of the `wallet.dat` file.
1. Store it securely.

!!! Warning "New private keys aren't in your backup"

    When you create a new address, create a new backup of the `wallet.dat` file.

## Restore your wallet

1. Replace the existing `wallet.dat` file with your backup.
1. Start Quiver.

description: Memos
<!--- END of page meta data -->

# Memos

When you receive ARW, you can see the amount of ARW received, the recipient address, and the date and time you recieved it. Optionally, you can retrieve the transaction ID, which you can use to view the encrypted transaction on the blockchain through [block explorers](../reference/arrow-explorers.md).

By design, Arrow hides information about senders, including addresses. Private transactions in Arrow are just that —  private.

However, in some cases, you might want to give more information to your recipient. In these cases, [put your information in the encrypted **Memo** field](../how-to/make-transactions/send-view-reply-to-memos.md) in your transaction. Every transaction includes the memo field, and it is always 512 characters. Even if you don't add personalized content to the **Memo** field, the field is included in the transaction, and it is automatically padded with all zeroes before encryption. If your personalized content is less than 512 characters, the remaining space is padded with zeroes before encryption. This padding promotes privacy, so that people who watch the blockchain can't spot differences between different usage patterns in the memos. Whether you include personalized content in the **Memo** field, the transaction fee is the same.

Only the recipient can view the encrypted memo unless either the sender or recipient shares the transaction view key with a third party. If the key is shared, the third party who has it can see the memo, the amount of the transaction, and the recipient address of the transaction in the blockchain.

## What is good content for an encrypted memo?

  * Invoice number or account number for which you're making a payment
  * Return address to which refunds can be sent
  * Personal note for the recipient
  * Personal information from financial institutions to satisfy the [travel rule](https://www.sec.gov/about/offices/ocie/aml2007/fincen-advissu7.pdf)

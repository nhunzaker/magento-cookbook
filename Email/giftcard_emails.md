# Constructing Giftcard Emails

## List of variables

The following list of variables can be found in full detail on `line 200` at `app/code/core/Enterprise/GiftCard/Observer.php`:

```
$templateData = array(
    'name'                   => $item->getProductOptionByCode('giftcard_recipient_name'),
    'email'                  => $item->getProductOptionByCode('giftcard_recipient_email'),
    'sender_name_with_email' => $sender,
    'sender_name'            => $senderName,
    'gift_message'           => $item->getProductOptionByCode('giftcard_message'),
    'giftcards'              => $codeList->toHtml(),
    'balance'                => $balance,
    'is_multiple_codes'      => 1 < $goodCodes,
    'store'                  => $order->getStore(),
    'store_name'             => $order->getStore()->getName(), // @deprecated after 1.4.0.0-beta1
    'is_redeemable'          => $isRedeemable,
);
```

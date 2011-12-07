# Constructing Giftcard Emails

## What's in here:

1. How to enable custom email templates for giftcards
2. List of giftcard variables

---

### How to enable custom email templates for giftcards

You can configure the settings at:

`System > Configuration > Sales > Gift Cards > Gift Card Email Settings `

---

### List of variables

- Gift Message: `{{var gift_message|escape|nl2br}}`

The following list of variables can be found in full detail on `line 200` at `app/code/core/Enterprise/GiftCard/Observer.php`:

*with annotations*:

```
$templateData = array(

    # The recipient's name
    'name'                   => $item->getProductOptionByCode('giftcard_recipient_name'),
    
    # The recipient's email
    'email'                  => $item->getProductOptionByCode('giftcard_recipient_email'),
    
    # The sender's name and email
    'sender_name_with_email' => $sender,
    
    # The sender's name
    'sender_name'            => $senderName,
    
    # The message associated with the giftcard
    'gift_message'           => $item->getProductOptionByCode('giftcard_message'),
    
    # A list of the giftcards
    'giftcards'              => $codeList->toHtml(),
    
    # The current balance
    'balance'                => $balance,
    
    # A boolean if multiple codes exist
    'is_multiple_codes'      => 1 < $goodCodes,
    
    # What store the giftcard is for
    'store'                  => $order->getStore(),
    
    # The name of the store
    'store_name'             => $order->getStore()->getName(), // @deprecated after 1.4.0.0-beta1
    
    # A boolean if the code may be redeemed
    'is_redeemable'          => $isRedeemable,
);
```

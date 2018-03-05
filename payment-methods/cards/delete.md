#### Delete a card

You can delete cards from a customer.

If you delete a card that is currently the default card on a customer, the most recently added card will be used as the new default.

If you delete the last remaining card on a customer, the default_card attribute on the card's owner will become null.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$customerId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The customer unique identifier.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$cardId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The card unique identifier.
            </td>
        </tr>
    </tbody>
</table>

##### Usage

```php
$card = $stripe->cards()->delete('cus_4EBumIjyaKooft', 'card_4DmaB3muM8SNdZ');
```

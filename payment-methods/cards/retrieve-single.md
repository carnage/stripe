#### Retrieve a Card

Retrieves the details of an existing credit card.

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
$card = $stripe->cards()->find('cus_4EBumIjyaKooft', 'card_4DmaB3muM8SNdZ');

echo $card['last4'];
```

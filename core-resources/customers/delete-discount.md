#### Delete a customer discount

Removes the currently applied discount on a customer.

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
    </tbody>
</table>

##### Usage

```php
$customer = $stripe->customers()->deleteDiscount('cus_4EBumIjyaKooft');
```

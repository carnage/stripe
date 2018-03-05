#### Retrieve a refund

By default, you can see the 10 most recent refunds stored on a charge directly on the charge object, but you can also retrieve details about a specific refund stored on the charge.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$chargeId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The charge unique identifier.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$refundId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The refund unique identifier.
            </td>
        </tr>
    </tbody>
</table>

##### Usage

```php
$refund = $stripe->refunds()->find('ch_4ECWMVQp5SJKEx', 'txn_4IgdBGArAOeiQw');
```

#### Retrieve a balance transaction

Retrieves the balance transaction with the given ID.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$transactionId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The transaction unique identifier.
            </td>
        </tr>
    </tbody>
</table>

##### Usage

```php
$balance = $stripe->balance()->find('txn_4EI2Pu1gPR27yT');

echo $balance['amount'];
```

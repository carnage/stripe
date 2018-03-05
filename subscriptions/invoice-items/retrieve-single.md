#### Retrieve an invoice item

Retrieves the invoice item with the given ID.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$invoiceItemId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The invoice item unique identifier.
            </td>
        </tr>
    </tbody>
</table>

##### Usage

```php
$invoiceItem = $stripe->invoiceItems()->find('ii_4Egr3tUtHjVEnm');

echo $invoiceItem['amount'];
```

#### Delete an invoice item

Removes an invoice item from the upcoming invoice. Removing an invoice item is only possible before the invoice it's attached to is closed.

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
$stripe->invoiceItems()->delete('ii_4Egr3tUtHjVEnm');
```

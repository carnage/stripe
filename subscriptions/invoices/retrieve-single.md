#### Retrieve an invoice

Retrieves the invoice with the given ID.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$invoiceId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The invoice unique identifier.
            </td>
        </tr>
    </tbody>
</table>

##### Usage

```php
$invoice = $stripe->invoices()->find('in_4EgP02zb8qxsLq');

echo $invoice['paid'];
```

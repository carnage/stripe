#### Pay an invoice

Stripe automatically creates and then attempts to pay invoices for customers on subscriptions. We'll also retry unpaid invoices according to your [retry settings](https://dashboard.stripe.com/account/recurring). However, if you'd like to attempt to collect payment on an invoice out of the normal retry schedule or for some other reason, you can do so.

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
$invoice = $stripe->invoices()->pay('in_4EgP02zb8qxsLq');
```

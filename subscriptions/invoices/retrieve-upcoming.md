#### Retrieve an upcoming invoice

At any time, you can preview the upcoming invoice for a customer. This will show you all the charges that are pending, including subscription renewal charges, invoice item charges, etc. It will also show you any discount that is applicable to the customer.

Note that when you are viewing an upcoming invoice, you are simply viewing a preview -- the invoice has not yet been created. As such, the upcoming invoice will not show up in invoice listing calls, and you cannot use the API to pay or edit the invoice. If you want to change the amount that your customer will be billed, you can add, remove, or update pending invoice items, or update the customer's discount.

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
                <small>string</small> <strong>$subscriptionId</strong><br />
            </td>
            <td width="80%">
                The subscription unique identifier.
            </td>
        </tr>
    </tbody>
</table>

##### Usage

```php
$invoice = $stripe->invoices()->upcomingInvoice('cus_4EBumIjyaKooft');

foreach ($invoice['lines']['data'] as $item) {
    var_dump($item['id']);
}
```

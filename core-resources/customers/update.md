#### Update a customer

Updates the specified customer by setting the values of the parameters passed.

This request accepts mostly the same arguments as the customer creation call.

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
                <small>associative array</small> <strong>$parameters</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                Please refer to the list below for a valid list of keys that can be passed on this array.
            </td>
        </tr>
    </tbody>
</table>

###### $parameters

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>integer</small> <strong>account_balance</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                An integer amount in cents that is the starting account balance for your customer. A negative amount represents a credit that will be used before attempting any charges to the customer’s card; a positive amount will be added to the next invoice.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>business_vat_id</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                The customer’s VAT identification number. If you are using Relay, this field gets passed to tax provider you are using for your orders.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>coupon</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                If you provide a coupon code, the customer will have a discount applied on all recurring charges. Charges you create through the API will not have the discount.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>description</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                An arbitrary string that you can attach to a customer object. It is displayed alongside the customer in the dashboard.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>email</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                Customer’s email address. It’s displayed alongside the customer in your dashboard and can be useful for searching and tracking.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>metadata</strong><br />
                <small style="color: grey;">optional, default is <strong>array()</strong></small>
            </td>
            <td width="80%">
                A set of key/value pairs that you can attach to a customer object.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>shipping</strong><br />
                <small style="color: grey;">optional, default is <strong>array()</strong></small>
            </td>
            <td width="80%">
            </td>
        </tr>
    </tbody>
</table>

> **Note:** For a more up to date list of parameters, please refer to the official Stripe documentation located [here](https://stripe.com/docs/api#update_customer).

##### Usage

```php
$customer = $stripe->customers()->update('cus_4EBumIjyaKooft', [
    'email' => 'jonathan@doe.com',
]);

echo $customer['email'];
```

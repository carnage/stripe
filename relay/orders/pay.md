#### Pay an order

Pay an order by providing a source to create a payment.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$orderId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The order unique identifier.
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
                <small>string</small> <strong>customer</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                The ID of an existing customer to use for this order. If provided, the customer email and shipping address will be used to create the order. Subsequently, the customer will also be charged to pay the order. If `email` or `shipping` are also provided, they will override the values retrieved from the customer object.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>source</strong><br />
                <small style="color: grey;">optional, either <strong>source/strong> or <strong>customer/strong> is required</small>
            </td>
            <td width="80%">
                A payment source to be charged, such as a credit card. If you also pass a customer ID, the source must be the ID of a source belonging to the customer (e.g., a saved card).
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>integer</small> <strong>application_fee</strong><br />
                <small style="color: teal;">CONNECT ONLY</small><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                An application fee to add on to this order.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>email</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                The email address of the customer placing the order.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>metadata</strong><br />
                <small style="color: grey;">optional, default is <strong>array()</strong></small>
            </td>
            <td width="80%">
                A set of key/value pairs that you can attach to a order object. It can be useful for storing additional information about the order in a structured format.
            </td>
        </tr>
    </tbody>
</table>

> **Note:** For a more up to date list of parameters, please refer to the official Stripe documentation located [here](https://stripe.com/docs/api#pay_order).

##### Usage

```php
$order = $stripe->orders()->pay('or_16nYXbJvzVWl1WTe7t5ODS8z');

echo $order['status'];
```

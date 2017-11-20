#### Update an order

Updates the specific order by setting the values of the parameters passed. Any parameters not provided will be left unchanged. This request accepts only the `metadata`, and `status` as arguments.

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
                <small>string</small> <strong>coupon</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                A coupon code that represents a discount to be applied to this order. Must be one-time duration and in same currency as the order.
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
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>shipping</strong><br />
                <small style="color: grey;">optional, default is <strong>array()</strong></small>
            </td>
            <td width="80%">
                Shipping information for the charge. Helps prevent fraud on charges for physica l goods.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>boolean</small> <strong>status</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                Current order status. One of `created`, `paid`, `canceled`, `fulfilled`, or `returned`.
            </td>
        </tr>
    </tbody>
</table>

> **Note:** For a more up to date list of parameters, please refer to the official Stripe documentation located [here](https://stripe.com/docs/api#update_order).

##### Usage

```php
$order = $stripe->orders()->update('or_16nYXbJvzVWl1WTe7t5ODS8z', [
    'metadata' => [
        'foo' => 'Bar',
    ],
]);

echo $order['status'];
```

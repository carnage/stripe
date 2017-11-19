#### Create an order

Creates a new order object.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>$parameters</strong><br />
                <small style="color: teal;">REQUIRED</small>
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
                <small>string</small> <strong>currency</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                3-letter ISO code for currency.
            </td>
        </tr>
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
                <small>string</small> <strong>customer</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                The ID of an existing customer to use for this order. If provided, the customer email and shipping address will be used to create the order. Subsequently, the customer will also be charged to pay the order. If `email` or `shipping` are also provided, they will override the values retrieved from the customer object.
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
                <small>associative array</small> <strong>items</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                List of items constituting the order.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>metadata</strong><br />
                <small style="color: grey;">optional, default is <strong>array()</strong></small>
            </td>
            <td width="80%">
                A set of key/value pairs that you can attach to a charge object.
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
    </tbody>
</table>

> **Note:** For a more up to date list of parameters, please refer to the official Stripe documentation located [here](https://stripe.com/docs/api#create_order).

##### Usage

```php
$order = $stripe->orders()->create([
    'currency' => 'usd',
    'items' => [
        [
            'type'   => 'sku',
            'parent' => 't-shirt-small-red',
        ],
    ],
    'shipping' => [
        'name'    => 'Jenny Rosen',
        'address' => [
            'line1'       => '1234 Main street',
            'city'        => 'Anytown',
            'country'     => 'US',
            'postal_code' => '123456',
        ],
    ],
    'email' => 'jenny@ros.en'
]);

echo $order['id'];
```

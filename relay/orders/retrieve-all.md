#### Retrieve all orders

Returns a list of your orders. The orders are returned sorted by creation date, with the most recently created orders appearing first.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>$parameters</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                Please refer to the list below for a valid list of key/value pairs that can be passed on this array.
            </td>
        </tr>
    </tbody>
</table>

###### $parameters

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>created</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">A filter on the list based on the object created field.</td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>customer</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">Only return charges for the customer specified by this customer ID.</td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>ending_before</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">A cursor to be used in pagination.</td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>integer</small> <strong>limit</strong><br />
                <small style="color: grey;">optional, default is <strong>10</strong></small>
            </td>
            <td width="80%">A limit on the number of objects to be returned.</td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>starting_after</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">A cursor to be used in pagination.</td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>status</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">Only return orders that have the given status. One of `created`, `paid`, `fulfilled`, or `refunded`.</td>
        </tr>
    </tbody>
</table>

> **Note:** For a more up to date list of parameters, please refer to the official Stripe documentation located [here](https://stripe.com/docs/api#list_charges).

##### Usage

```php
$orders = $stripe->orders()->all();

foreach ($orders['data'] as $order) {
    var_dump($order['id']);
}
```

#### Retrieve all the balance history

Returns a list of transactions that have contributed to the Stripe account balance (includes charges, refunds, transfers, and so on). The transactions are returned in sorted order, with the most recent transactions appearing first.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>array</small> <strong>$parameters</strong>
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
                <strong>available_on</strong><br />
                <small style="color: grey;">optional associative array</small>
            </td>
            <td width="80%">A filter on the list based on the object available_on field.</td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <strong>created</strong><br />
                <small style="color: grey;">optional associative array</small>
            </td>
            <td width="80%">A filter on the list based on the object created field.</td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <strong>currency</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%"></td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <strong>ending_before</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">A cursor to be used in pagination.</td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <strong>limit</strong><br />
                <small style="color: grey;">optional, default is <strong>10</strong></small>
            </td>
            <td width="80%">A limit on the number of objects to be returned.</td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <strong>payout</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">For automatic Stripe payouts only, only returns transactions that were payed out on the specified payout ID.</td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <strong>source</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">Only returns the original transaction.</td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <strong>starting_after</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">A cursor to be used in pagination.</td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <strong>type</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">Only returns transactions of the given type. One of: `charge`, `refund`, `adjustment`, `application_fee`, `application_fee_refund`, `transfer` or `transfer_failure`.</td>
        </tr>
    </tbody>
</table>

> **Note:** For a more up to date list of parameters, please refer to the official Stripe documentation located [here](https://stripe.com/docs/api#balance_history).

##### Usage

```php
$history = $stripe->balance()->all();

foreach ($history['data'] as $balance) {
    var_dump($balance['id']);
}
```

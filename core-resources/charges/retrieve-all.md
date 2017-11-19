#### Retrieve all charges

Returns a list of charges you've previously created. The charges are returned in sorted order, with the most recent charges appearing first.

##### Arguments

<table>
    <tbody>
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
                <small>string</small> <strong>transfer_group</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">Only return charges for this transfer group.</td>
        </tr>
    </tbody>
</table>

> **Note:** For a more up to date list of parameters, please refer to the official Stripe documentation located [here](https://stripe.com/docs/api#list_charges).

##### Usage

```php
$charges = $stripe->charges()->all();

foreach ($charges['data'] as $charge) {
    var_dump($charge['id']);
}
```

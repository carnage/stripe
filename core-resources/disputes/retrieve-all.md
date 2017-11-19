#### Retrieve all disputes

Returns a list of your disputes.

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
    </tbody>
</table>

> **Note:** For a more up to date list of parameters, please refer to the official Stripe documentation located [here](https://stripe.com/docs/api#list_disputes).

##### Usage

```php
$disputes = $stripe->disputes()->all();

foreach ($disputes['data'] as $dispute) {
    var_dump($dispute['id']);
}
```

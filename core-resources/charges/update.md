#### Update a charge

Updates the specified charge by setting the values of the parameters passed. Any parameters not provided will be left unchanged.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$chargeId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The charge unique identifier.
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
                <small>string</small> <strong>description</strong><br />
                <small style="color: grey;">optional, default is <strong>null</strong></small>
            </td>
            <td width="80%">
                An arbitrary string which you can attach to a charge object.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>fraud_details</strong><br />
                <small style="color: grey;">optional, default is <strong>array()</strong></small>
            </td>
            <td width="80%">
                An arbitrary string which you can attach to a charge object.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>metadata</strong><br />
                <small style="color: grey;">optional, default is <strong>array()</strong></small>
            </td>
            <td width="80%">
                A set of key/value pairs you can attach to a charge giving information about its riskiness. If you believe a charge is fraudulent, include a `user_report` key with a value of `fraudulent`. If you believe a charge is safe, include a `user_report` key with a value of `safe`. Note that you must refund a charge before setting the `user_report` to `fraudulent`. Stripe will use the information you send to improve our fraud detection algorithms.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>receipt_email</strong><br />
                <small style="color: grey;">optional, default is <strong>null</strong></small>
            </td>
            <td width="80%">
                The email address to send this charge’s receipt to.
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
                <small>string</small> <strong>transfer_group</strong><br />
                <small style="color: teal;">CONNECT ONLY</small><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                A string that identifies this transaction as part of a group.
            </td>
        </tr>
    </tbody>
</table>

> **Note:** For a more up to date list of parameters, please refer to the official Stripe documentation located [here](https://stripe.com/docs/api#update_charge).

##### Usage

```php
$charge = $stripe->charges()->update('ch_4ECWMVQp5SJKEx', [
    'description' => 'Payment to foo bar',
]);
```

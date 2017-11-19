#### Capture a charge

Capture the payment of an existing, uncaptured, charge. This is the second half of the two-step payment flow, where first you [created a charge](#create-a-new-charge) with the capture option set to false.

Uncaptured payments expire exactly seven days after they are created. If they are not captured by that point in time, they will be marked as refunded and will no longer be capturable.

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
                <small>string</small> <strong>amount</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                The amount to capture, which must be less than or equal to the original amount. Any additional amount will be automatically refunded.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small></small> <strong>application_fee</strong><br />
                <small style="color: teal;">CONNECT ONLY</small><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                An application fee to add on to this charge. Can only be used with Stripe Connect.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>destination</strong><br />
                <small style="color: teal;">CONNECT ONLY</small><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                An optional dictionary containing a new destination amount to use. Can only be used with destination charges created with Stripe Connect.
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
                <small>string</small> <strong>statement_descriptor</strong><br />
                <small style="color: grey;">optional, default is <strong>null</strong></small>
            </td>
            <td width="80%">
                An arbitrary string to be displayed alongside your company name on your customer's credit card statement.
            </td>
        </tr>
    </tbody>
</table>

> **Note:** For a more up to date list of parameters, please refer to the official Stripe documentation located [here](https://stripe.com/docs/api#capture_charge).

##### Usage

```php
$charge = $stripe->charges()->capture('ch_4ECWMVQp5SJKEx');
```

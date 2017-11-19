#### Update a dispute

When you get a dispute, contacting your customer is always the best first step. If that doesn't work, you can submit evidence in order to help us resolve the dispute in your favor. You can do this in your [dashboard](https://dashboard.stripe.com/#disputes), but if you prefer, you can use the API to submit evidence programmatically.

Depending on your dispute type, different evidence fields will give you a better chance of winning your dispute. You may want to consult the Stripe [guide to dispute types](https://stripe.com/help/dispute-types) to help you figure out which evidence fields to provide.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$disputeId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The dispute unique identifier.
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
                <small>associative array</small> <strong>evidence</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                Evidence to upload to respond to a dispute. Updating any field in the hash will submit all fields in the hash for review.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>metadata</strong><br />
                <small style="color: grey;">optional, default is <strong>array()</strong></small>
            </td>
            <td width="80%">
                A set of key/value pairs that you can attach to a dispute object.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>boolean</small> <strong>submit</strong><br />
                <small style="color: grey;">optional, default is <strong>true</strong></small>
            </td>
            <td width="80%">
                Whether or not to immediately submit evidence to the bank. If `false`, evidence is staged on the dispute. Staged evidence is visible in the API and Dashboard, and can be submitted to the bank by making another request with this attribute set to `true` (the default).
            </td>
        </tr>
    </tbody>
</table>

##### Usage

```php
$dispute = $stripe->disputes()->update('dp_1BPtTyK2uxncQly2o2gALyTT', [
    'evidence' => 'Customer agreed to drop the dispute.',
]);
```

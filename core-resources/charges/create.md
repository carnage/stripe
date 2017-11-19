#### Create a charge

To charge a credit card, you need to create a new charge object. If your API key is in test mode, the supplied card won't actually be charged, though everything else will occur as if in live mode. (Stripe will assume that the charge would have completed successfully).

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
                <small>string</small> <strong>amount</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                A positive amount representing how much to charge the card. Note that this should be a dollar amount, and will automatically be converted in to cents for you before being transmitted to Stripe.
            </td>
        </tr>
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
                <small></small> <strong>application_fee</strong><br />
                <small style="color: teal;">CONNECT ONLY</small><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                An application fee to add on to this charge.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>boolean</small> <strong>capture</strong><br />
                <small style="color: grey;">optional, default is <strong>true</strong></small>
            </td>
            <td width="80%">
                Whether or not to immediately capture the charge.
            </td>
        </tr>
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
                <small>associative array</small> <strong>destination</strong><br />
                <small style="color: teal;">CONNECT ONLY</small><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                If specified, the charge will be attributed to the destination account for tax reporting, and the funds from the charge will be transferred to the destination account. The ID of the resulting transfer will be returned in the transfer field of the response.
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
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>on_behalf_of</strong><br />
                <small style="color: teal;">CONNECT ONLY</small><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                The Stripe account ID that these funds are intended for. Automatically set if you use the `destination` parameter.
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
                <small>string</small> <strong>customer</strong><br />
                <small style="color: grey;">optional, either <strong>customer</strong> or <strong>source</strong> is required</small>
            </td>
            <td width="80%">
                The customer unique identifier.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string|array</small> <strong>source</strong><br />
                <small style="color: grey;">optional, either <strong>source</strong> or <strong>customer</strong> is required</small>
            </td>
            <td width="80%">
                The source can either be a token or a dictionary containing the source details.
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

> **Note:** For a more up to date list of parameters, please refer to the official Stripe documentation located [here](https://stripe.com/docs/api#create_charge).

##### Usage

```php
$charge = $stripe->charges()->create([
    'customer' => 'cus_4EBumIjyaKooft',
    'currency' => 'USD',
    'amount'   => 50.49,
]);

echo $charge['id'];
```

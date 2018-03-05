#### Create a bank account token

Creates a single use token that wraps the details of a bank account. This token can be used in place of a bank account dictionary with any API method. These tokens can only be used once: by attaching them to a [recipient](#create-a-new-recipient).

##### Arguments

<table>
    <tr valign="top">
        <td width="20%" style="text-align: right">
            <small>array</small> <strong>$parameters</strong><br />
            <small style="color: teal;">REQUIRED</small>
        </td>
        <td width="80%">
            Please refer to the list below for a valid list of keys that can be passed on this array.
        </td>
    </tr>
</table>

###### $parameters

<table>
    <thead>
        <th>Key</th>
        <th>Required</th>
        <th>Type</th>
        <th>Default</th>
        <th>Description</th>
    </thead>
    <tbody>
        <tr>
            <td>bank_account</td>
            <td>true</td>
            <td>string | array</td>
            <td>null</td>
            <td>A bank account to attach to the recipient.</td>
        </tr>
    </tbody>
</table>

##### Usage

```php
$token = $stripe->tokens()->create([
    'bank_account' => [
        'country'        => 'US',
        'routing_number' => '110000000',
        'account_number' => '000123456789',
    ],
]);

echo $token['id'];
```

#### Retrieve a subscription

Retrieves the details of an existing customer subscription.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$customerId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The customer unique identifier.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$subscriptionId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The subscription unique identifier.
            </td>
        </tr>
    </tbody>
</table>

##### Usage

```php
$subscription = $stripe->subscriptions()->find('cus_4EBumIjyaKooft', 'sub_4ETjGeEPC5ai9J');

echo $subscription['id'];
```

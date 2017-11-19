#### Retrieve a customer

Retrieves the details of an existing customer.

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
    </tbody>
</table>

##### Usage

```php
$customer = $stripe->customers()->find('cus_4EBumIjyaKooft');

echo $customer['email'];
```

#### Retrieve a charge

Retrieves the details of a charge that has been previously created. Supply the unique charge ID that was returned from a previous request, and Stripe will return the corresponding charge information. The same information is returned when creating or refunding the charge.

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
    </tbody>
</table>

##### Usage

```php
$charge = $stripe->charges()->find('ch_4ECWMVQp5SJKEx');
```

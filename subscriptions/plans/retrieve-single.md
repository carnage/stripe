#### Retrieve a plan

Retrieves the plan with the given ID.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$planId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The plan unique identifier.
            </td>
        </tr>
    </tbody>
</table>

##### Usage

```php
$plan = $stripe->plans()->find('monthly');

echo $plan['name'];
```

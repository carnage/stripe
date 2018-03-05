#### Delete a plan

You can delete plans via the [plan management](https://dashboard.stripe.com/plans) page of the Stripe dashboard. However, deleting a plan does not affect any current subscribers to the plan; it merely means that new subscribers can't be added to that plan. You can also delete plans via the API.

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
$plan = $stripe->plans()->delete('monthly');
```

#### Retrieve an order

Retrieves the details of an existing order. Supply the unique order ID from either an order creation request or the order list, and Stripe will return the corresponding order information.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$orderId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The order unique identifier.
            </td>
        </tr>
    </tbody>
</table>

##### Usage

```php
$order = $stripe->orders()->find('or_16nYXbJvzVWl1WTe7t5ODS8z');

echo $order['status'];
```

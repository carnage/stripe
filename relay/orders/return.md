#### Return an order

Return all or part of an order. The order must have a status of `paid` or `fulfilled` before it can be returned. Once all items have been returned, the order will become `canceled` or `returned` depending on which status the order started in.

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
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>$items</strong><br />
                <small style="color: grey;">optional, default is <strong>array()</strong></small>
            </td>
            <td width="80%">List of items to return.</td>
        </tr>
    </tbody>
</table>

##### Usage

```php
$order = $stripe->orders()->returnItems('or_16nYXbJvzVWl1WTe7t5ODS8z', [
    [
        'type'   => 'sku',
        'parent' => 'sku_BnUToYqZtxv2mA'
    ],
]);

echo $order['status'];
```

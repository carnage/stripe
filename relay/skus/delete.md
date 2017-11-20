#### Delete a SKU

Delete a SKU. Deleting a SKU is only possible until it has been used in an order.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$skuId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The SKU unique identifier.
            </td>
        </tr>
    </tbody>
</table>

##### Usage

```php
$sku = $stripe->skus()->delete('sku_Bnf8QnZxQ2UVtx');

echo $sku['deleted'];
```

#### Retrieve a product

Retrieves the details of an existing product. Supply the unique product ID from either a product creation request or the product list, and Stripe will return the corresponding product information.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$productId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The product unique identifier.
            </td>
        </tr>
    </tbody>
</table>

##### Usage

```php
$product = $stripe->products()->find('prod_72587E4aVLiMy6');

echo $product['name'];
```

#### Update a SKU

Updates the specific product by setting the values of the parameters passed. Any parameters not provided will be left unchanged.

Note that a product's `attributes` are not editable. Instead, you would need to deactivate the existing product and create a new one with the new attribute values.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$skuId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The sKU unique identifier.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>$parameters</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                Please refer to the list below for a valid list of keys that can be passed on this array.
            </td>
        </tr>
    </tbody>
</table>

###### $parameters

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>boolean</small> <strong>active</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                Whether or not the SKU is available for purchase. Default to `true`.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>array</small> <strong>attributes</strong><br />
                <small style="color: grey;">optional, default is <strong>array()</strong></small>
            </td>
            <td width="80%">
                A dictionary of attributes and values for the attributes defined by the product. When specified, `attributes` will partially update the existing attributes dictionary on the product, with the postcondition that a value must be present for each attribute key on the product, and that all SKUs for the product must have unique sets of attributes.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>currency</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                3-letter ISO code for currency.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>image</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                Whether or not the SKU is available for purchase. Default to `true`.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>inventory</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                Description of the SKU’s inventory.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>metadata</strong><br />
                <small style="color: grey;">optional, default is <strong>array()</strong></small>
            </td>
            <td width="80%">
                A set of key/value pairs that you can attach to a SKU object. It can be useful for storing additional information about the SKU in a structured format.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>package_dimensions</strong><br />
                <small style="color: grey;">optional, default is <strong>array()</strong></small>
            </td>
            <td width="80%">
                The dimensions of this SKU for shipping purposes.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>integer</small> <strong>price</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The cost of the item as a nonnegative integer in the smallest currency unit (that is, 100 cents to charge $1.00, or 100 to charge ¥100, Japanese Yen being a zero-decimal currency).
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>product</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The ID of the product this SKU is associated with.
            </td>
        </tr>
    </tbody>
</table>

> **Note:** For a more up to date list of parameters, please refer to the official Stripe documentation located [here](https://stripe.com/docs/api#update_sku).

##### Usage

```php
$sku = $stripe->skus()->update('sku_Bnf8QnZxQ2UVtx', [
    'metadata' => [
        'foo' => 'Bar',
    ],
]);

echo $sku['id'];
```

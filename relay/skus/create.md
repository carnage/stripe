#### Create a SKU

Creates a new product object.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>$parameters</strong><br />
                <small style="color: teal;">REQUIRED</small>
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
                <small>string</small> <strong>id</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                The identifier for the SKU. Must be unique. If not provided, an identifier will be randomly generated.
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
                <small>associative array</small> <strong>inventory</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                Description of the SKU’s inventory.
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
                A dictionary of attributes and values for the attributes defined by the product. If, for example, a product’s attributes are `["size", "gender"]`, a valid SKU has the following dictionary of attributes: `{"size": "Medium", "gender": "Unisex"}`.
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
    </tbody>
</table>

> **Note:** For a more up to date list of parameters, please refer to the official Stripe documentation located [here](https://stripe.com/docs/api#create_sku).

##### Usage

```php
$sku = $stripe->skus()->create([
    'product'   => 'prod_Bnf8BfTecezAca',
    'attributes' => [
        'size'   => 'Medium',
        'gender' => 'Unisex',
    ],
    'price'     => 1500,
    'currency'  => 'usd',
    'inventory' => [
        'type'     => 'finite',
        'quantity' => 500
    ],
]);

echo $sku['id'];
```

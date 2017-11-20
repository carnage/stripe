#### Updates a product

Updates the specific product by setting the values of the parameters passed. Any parameters not provided will be left unchanged.

Note that a product's `attributes` are not editable. Instead, you would need to deactivate the existing product and create a new one with the new attribute values.

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
                Whether or not the product is currently available for purchase. Defaults to `true`.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>array</small> <strong>attributes</strong><br />
                <small style="color: grey;">optional, default is <strong>array()</strong></small>
            </td>
            <td width="80%">
                A list of up to 5 alphanumeric attributes that each SKU can provide values for (e.g. `["color", "size"]`).
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>caption</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                A short one-line description of the product, meant to be displayable to the customer.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>description</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                The product’s description, meant to be displayable to the customer.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>array</small> <strong>images</strong><br />
                <small style="color: grey;">optional, default is <strong>array()</strong></small>
            </td>
            <td width="80%">
                A list of up to 8 URLs of images for this product, meant to be displayable to the customer.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>metadata</strong><br />
                <small style="color: grey;">optional, default is <strong>array()</strong></small>
            </td>
            <td width="80%">
                A set of key/value pairs that you can attach to a product object. It can be useful for storing additional information about the product in a structured format.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>name</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The product’s name, meant to be displayable to the customer.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>package_dimensions</strong><br />
                <small style="color: grey;">optional, default is <strong>array()</strong></small>
            </td>
            <td width="80%">
                The dimensions of this product for shipping purposes. A SKU associated with this product can override this value by having its own `package_dimensions`.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>boolean</small> <strong>shippable</strong><br />
                <small style="color: grey;">optional, default is <strong>true</strong></small>
            </td>
            <td width="80%">
                Whether this product is shipped (i.e. physical goods). Defaults to `true`.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>url</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                A URL of a publicly-accessible webpage for this product.
            </td>
        </tr>
    </tbody>
</table>

> **Note:** For a more up to date list of parameters, please refer to the official Stripe documentation located [here](https://stripe.com/docs/api#update_product).

##### Usage

```php
$product = $stripe->products()->update('pr_16nYIkJvzVWl1WTezKYABD87', [
    'description' => 'Comfortable gray cotton t-shirts',
]);

echo $product['id'];
```

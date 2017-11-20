#### Retrieve all SKUs

Returns a list of your SKUs. The SKUs are returned sorted by creation date, with the most recently created SKUs appearing first.

##### Arguments

<table>
    <tbody>
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
            <td width="80%">Only return SKUs that are active or inactive (e.g. pass `false` to list all inactive products).</td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>associative array</small> <strong>attributes</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">
                Only return SKUs that have the specified key/value pairs in this partially constructed dictionary. Can be specified only if product is also supplied. For instance, if the associated `product` has attributes `["color", "size"]`, passing `in attributes[color]=red` returns all the SKUs for this product that have `color` set to `red`.
            </td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>ending_before</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">A cursor to be used in pagination.</td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>array</small> <strong>ids</strong><br />
                <small style="color: grey;">optional, default is <strong>array()</strong></small>
            </td>
            <td width="80%">Only return products with the given IDs.</td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>boolean</small> <strong>in_stock</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">Only return SKUs that are either in stock or out of stock (e.g. pass `false` to list all SKUs that are out of stock). If no value is provided, all SKUs are returned.</td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>integer</small> <strong>limit</strong><br />
                <small style="color: grey;">optional, default is <strong>10</strong></small>
            </td>
            <td width="80%">A limit on the number of objects to be returned.</td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>product</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">The ID of the product whose SKUs will be retrieved.</td>
        </tr>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>starting_after</strong><br />
                <small style="color: grey;">optional</small>
            </td>
            <td width="80%">A cursor to be used in pagination.</td>
        </tr>
    </tbody>
</table>

> **Note:** For a more up to date list of parameters, please refer to the official Stripe documentation located [here](https://stripe.com/docs/api#list_skus).

##### Usage

```php
$skus = $stripe->skus()->all();

foreach ($skus['data'] as $sku) {
    var_dump($sku['id']);
}
```

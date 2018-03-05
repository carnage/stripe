#### Delete a coupon

You can delete coupons via the [coupon management](https://dashboard.stripe.com/coupons) page of the Stripe dashboard. However, deleting a coupon does not affect any customers who have already applied the coupon; it means that new customers can't redeem the coupon. You can also delete coupons via the API.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$couponId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The coupon unique identifier.
            </td>
        </tr>
    </tbody>
</table>

##### Usage

```php
$coupon = $stripe->coupons()->delete('50-PERCENT-OFF');
```

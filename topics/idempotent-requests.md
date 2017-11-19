### Idempotent Requests

The Stripe API supports [idempotency](https://en.wikipedia.org/wiki/Idempotence) for safely retrying requests without accidentally performing the same operation twice.

For example, if a request to create a charge fails due to a network connection error, you can retry the request with the same idempotency key to guarantee that only a single charge is created.

`GET` and `DELETE` requests are idempotent by definition, meaning that the same backend work will occur no matter how many times the same request is issued. You shouldn't send an idempotency key with these verbs because it will have no effect.

To perform an idempotent request, just call the `idempotent()` method and pass an idempotency key as the first and only argument.

How you create unique keys is up to you, but we suggest using V4 UUIDs or another appropriately random string. We'll always send back the same response for requests made with the same key, and keys can't be reused with different request parameters. Keys expire after 24 hours.

```php
Stripe::idempotent('MosoFzVCQnUYejX5')->charges()->create([
    'customer' => 'cus_4EBumIjyaKooft',
    'currency' => 'USD',
    'amount'   => 50.49,
]);
```

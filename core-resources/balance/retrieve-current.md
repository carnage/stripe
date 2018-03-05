#### Retrieve balance

Retrieves the current account balance, based on the API key that was used to make the request.

##### Arguments

<small style="color: grey;">No arguments...</small>

##### Usage

```php
$balance = $stripe->balance()->current();

echo $balance['pending']['amount'];
```

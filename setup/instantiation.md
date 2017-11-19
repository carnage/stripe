### Instantiation

Creating a new Stripe instance is very easy and straightforward. Please check the examples below for further explanation.

```php
use Cartalyst\Stripe\Stripe;

$stripe = new Stripe('your-stripe-api-key', 'your-stripe-api-version');
```

or

```php
use Cartalyst\Stripe\Stripe;

$stripe = Stripe::make('your-stripe-api-key', 'your-stripe-api-version');
```

You can use environment variables instead of passing them as arguments.

Considering that there are a few different ways of setting these environment variables, we're going to use the `export` as an example.

> **Note:** On the following example, the keys will not be permanently set and you should instead use a file like `.bashrc` to set them in a more permanent way.

On your terminal run the following

```php
export STRIPE_API_KEY=your-stripe-api-key

export STRIPE_API_VERSION=your-stripe-api-version
```

Then upon instantiation, Stripe will auto detect these and use the variables accordingly.

```php
use Cartalyst\Stripe\Stripe;

$stripe = new Stripe();
```

or

```php
$stripe = Stripe::make();
```

> **Note:** Please do note that the Stripe API KEY is always required to be defined, either through an environment variable or by just passing it as the first argument to the constructor.

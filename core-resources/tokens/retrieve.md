#### Retrieve a token

Retrieves the token with the given ID.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$tokenId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The token unique identifier.
            </td>
        </tr>
    </tbody>
</table>

##### Usage

```php
$token = $stripe->tokens()->find('tok_15D2JOJvzVWl1WTewpv4hU8c');
```

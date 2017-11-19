#### Retrieve an event

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$eventId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The event unique identifier.
            </td>
        </tr>
    </tbody>
</table>

##### Usage

```php
$event = $stripe->events()->find('evt_4ECnKrmXyNn8IM');

echo $event['type'];
```

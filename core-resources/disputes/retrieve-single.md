#### Retrieve a dispute

Retrieves the dispute with the given ID.

##### Arguments

<table>
    <tbody>
        <tr valign="top">
            <td width="20%" style="text-align: right">
                <small>string</small> <strong>$disputeId</strong><br />
                <small style="color: teal;">REQUIRED</small>
            </td>
            <td width="80%">
                The dispute unique identifier.
            </td>
        </tr>
    </tbody>
</table>

##### Usage

```php
$charge = $stripe->disputes()->find('dp_1BPtTyK2uxncQly2o2gALyTT');
```

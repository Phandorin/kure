## Use

`gen [-l length] [-f format] [-i include] [-e exclude] [-r repeat] [-q qr]`

## Description

Generate a random password.

## Flags 

|  Name     | Shorthand |     Type      |    Default    |                           Usage                                       |
|-----------|-----------|---------------|---------------|-----------------------------------------------------------------------|
| length    | l         | uint64        | 1             | Password length                                                       |
| format    | f         | []string      | nil           | Password format                                                       |
| include   | i         | string        | ""            | Characters to include in the password (except 2 byte ¡¿° chars)       |
| exclude   | e         | string        | ""            | Characters to exclude from the password                               |
| repeat    | r         | bool          | false         | Allow duplicated characters or not                                    |
| qr        | q         | bool          | false         | Create an image with the password QR code on the user home directory  |

### Format levels

> Default is [1, 2, 3, 4, 5]

1. Lowercases (a, b, c...)
2. Uppercases (A, B, C...)
3. Digits (0, 1, 2...)
4. Space
5. Special (!, $, %...)

### Subcommands

kure gen **phrase**: Generate a random passphrase.

### Examples

Generate a password:
```
kure gen -f 1,2,3,4,5 -l 16 -i s4^%$
```
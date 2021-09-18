# Changing the Admin Password

There will be no password change form to change the password for the admin id. The password must only be changed programmatically.

Once changed, the hash should be copied into the `password` column of the `admin` table.

## **Password change process**

:fontawesome-solid-hand-point-right:{ .main } Select a strong password<br />

```
# Examples to generate password

# Option 1: Python
import secrets

secrets.token_hex(16)

# Output: 99ad83de41a9d0ab58f69931468e706c

# Option 2: Ubuntu
openssl rand 16 | openssl base64 -A

# Output: lEBf/7eKp+L4XtsUXmU3pg==

```

:fontawesome-solid-hand-point-right:{ .main } Use **Python's** `passlib` library to hash the password<br />

```
from passlib.hash import pbkdf2_sha256

pbkdf2_sha256.hash("99ad83de41a9d0ab58f69931468e706c")

# Output: '$pbkdf2-sha256$29000$5Lx3LuX8/997j7EWotS6dw$66AQzTY2Fn4VpMcXU7xWkkZOmMM0T2DaN6eu6veDBf4'
```

:fontawesome-solid-hand-point-right:{ .main } Copy the output to `admin.password`

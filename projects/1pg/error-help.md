---
description: Solutions to common 1PG errors.
---

# Error Help

#### `SyntaxError: Unexpected token =`

```text
on = '';
     ^
SyntaxError: Unexpected token =
```

**Solution**: NodeJS v14 is required for this syntax

#### `TypeError: Cannot read property 'access_token' of undefined`

```text
  let token = access['access_token'],
                    ^
  TypeError: Cannot read property 'access_token' of undefined
```

**Solution**: Use [twopg/oauth](https://twopg.github.io/oauth) instead of disco-oauth.


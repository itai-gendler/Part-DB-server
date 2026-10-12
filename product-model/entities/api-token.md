---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/UserSystem/ApiToken.php"
    }
  ],
  "domain": "api-tokens"
}
---

# API token

A User-owned REST credential with an expiry, permission level and usage information. The raw secret is stored; a displayed suffix is derived from it.

## Information kept

- **Name** — The token name.
- **Permission level** — The token’s source-declared permission level.
- **Expires at** — The optional expiration time.
- **Last used at** — The recorded last-use time.
- **Added at** — When the token was added.
- **Secret** — The stored raw token secret, distinct from its derived suffix display.

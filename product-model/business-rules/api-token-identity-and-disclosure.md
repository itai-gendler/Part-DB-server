---
{
  "appliesTo": [
    {
      "type": "entity",
      "id": "api-token"
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Security/ApiTokenAuthenticator.php"
    }
  ]
}
---

# Stored token secrets identify credentials while metadata excludes their full reveal

API-token authentication compares the raw stored secret and optional expiry. Creation reveals the secret; ordinary metadata excludes its full reveal and a displayed suffix is derived. Last-used changes and reached flushes follow the actual minute-component comparison rather than a universal ten-minute freshness guarantee.

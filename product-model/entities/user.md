---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/UserSystem/User.php"
    }
  ],
  "acts": "external",
  "kind": "person",
  "relations": [
    {
      "entity": "part-lot",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "storage-location",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "api-token",
      "verb": "owns",
      "cardinality": "one-to-many"
    },
    {
      "entity": "attachment",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "activity-entry",
      "verb": "performs",
      "cardinality": "one-to-many"
    }
  ]
}
---

# User

A person using Part-DB, with a kept account, personal information and preferences. Configurable Groups do not establish separate fixed Actor types.

## Information kept

- **Username** — The account’s sign-in and displayed username.
- **Personal profile** — First and last names, department, email and disclosure choice, about text and avatar selection.
- **Preferences** — Preferred language, timezone, theme and currency together with the kept personal options.
- **Password credential** — The stored local password credential.
- **Reset credential verifier** — The stored verifier for a password-recovery credential.
- **Reset credential expiry** — The time at which that recovery credential expires.
- **Password change required** — Whether the account must change its password.
- **Disabled** — Whether the account is disabled.
- **SAML account** — Whether this is a SAML account.
- **Permission overrides** — The account’s configured permission values, including inherited values.
- **Added at** — When this record was added.
- **Modified at** — When this record was last modified.

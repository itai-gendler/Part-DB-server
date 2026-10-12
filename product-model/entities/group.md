---
{
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/UserSystem/Group.php"
    }
  ],
  "domain": "groups",
  "relations": [
    {
      "entity": "user",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "group",
      "verb": "contains",
      "cardinality": "one-to-many"
    },
    {
      "entity": "parameter",
      "verb": "has",
      "cardinality": "one-to-many"
    },
    {
      "entity": "attachment",
      "verb": "has",
      "cardinality": "one-to-many"
    }
  ]
}
---

# Group

A configurable User grouping with inherited permission configuration and second-factor policy.

## Information kept

- **Name** — The Group name.
- **Comment** — The Group comment.
- **Permission overrides** — The Group’s configured permission values, including inherited values.
- **Enforce second factor** — Whether the Group requires second-factor authentication.
- **Parent assignment** — The optional parent Group.
- **Added at** — When this record was added.
- **Modified at** — When this record was last modified.

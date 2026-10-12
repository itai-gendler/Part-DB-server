---
{
  "kind": "edge",
  "routes": {
    "route": "Authenticated Web"
  },
  "steps": [
    {
      "text": "The caller merges components with nested records and existing requirement references.",
      "kind": "actor",
      "actor": "user",
      "entities": [],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-part"
        }
      }
    },
    {
      "text": "The Product reconciles supported Part information and merger-specific nested identities.",
      "kind": "product",
      "actor": "user",
      "entities": [
        {
          "entity": "part",
          "effect": "changes",
          "facts": [
            "Description",
            "Comment",
            "Tags",
            "Modified at"
          ],
          "as": "target"
        },
        {
          "entity": "part",
          "effect": "removes",
          "as": "source"
        },
        {
          "entity": "bom-entry",
          "effect": "changes",
          "facts": [
            "Part assignment",
            "Modified at"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "web::authenticated::authenticated-part"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Part.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/PartController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/EntityMergers/Mergers/EntityMergerHelperTrait.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/EntityMergers/Mergers/PartMerger.php"
    }
  ]
}
---

# Merge parts — Merger-specific comparisons reconcile nested records/BOM references (Authenticated Web)

## Trigger

The caller merges components with nested records and existing requirement references.

## Outcome

The target survives with reconciled supported information and BOM references; nested records are compared by their merger-specific identities.

## Edge cases

- Stock lots are cloned into the target; nonmatching Parameters are cloned after comparing name, grouping, symbol, unit and all values.
- Purchasing records compare vendor and vendor component number. A newer known availability value replaces older information; an empty target URL can take the other URL.
- Price tiers compare discount threshold and currency. A matching zero target price can take the other price and related quantity; distinct tiers are cloned.
- Owned associations compare their other component and type description; incoming associations are recreated toward the target unless already present.
- Attachments compare name/type and normalized external URL or internal reference. Matching external references may refresh signed or tracking URL details.
- A requirement referencing only the source is repointed to the target. An existing target requirement in the same assembly merges quantity, names, mounts, comment and supported price information, then removes the redundant row.

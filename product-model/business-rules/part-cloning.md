---
{
  "appliesTo": [
    {
      "type": "capability",
      "id": "create-part",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        }
      ]
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Part.php"
    }
  ]
}
---

# Cloned components and their supported dependents have distinct identities

Clone preparation creates a distinct Part identity and supported copied lot, parameter, purchasing, price, association and attachment identities. Source-specific copy behavior and selections remain distinct from arbitrary collection duplication.

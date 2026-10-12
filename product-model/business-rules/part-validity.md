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
        },
        {
          "place": "rest-api"
        },
        {
          "place": "mcp"
        }
      ]
    },
    {
      "type": "capability",
      "id": "edit-part",
      "contexts": [
        {
          "place": "web::public"
        },
        {
          "place": "web::authenticated"
        },
        {
          "place": "rest-api"
        },
        {
          "place": "mcp"
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

# Saved component information satisfies its declared field and Category constraints

Declared field validation and Category-sensitive constraints apply to accepted Part creation/editing. Name rules, numeric validity, source field types and supplied nested validation remain applicable rather than inferred interface parity.

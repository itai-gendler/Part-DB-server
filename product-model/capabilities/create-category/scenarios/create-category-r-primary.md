---
{
  "kind": "primary",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller submits a unique sibling name and valid comment, keeping the default EDA and naming information.",
      "kind": "actor",
      "actor": "api-client",
      "entities": [],
      "contexts": {
        "route": {
          "place": "rest-api"
        }
      }
    },
    {
      "text": "The Product consults the resolved User permission configuration.",
      "kind": "product",
      "actor": "api-client",
      "entities": [
        {
          "entity": "user",
          "effect": "reads",
          "facts": [
            "Permission overrides"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "rest-api"
        }
      }
    },
    {
      "text": "The Product saves the new Category with its supplied information and source-supported defaults.",
      "kind": "product",
      "actor": "api-client",
      "entities": [
        {
          "entity": "category",
          "effect": "creates",
          "facts": [
            "Name",
            "Comment",
            "Not selectable",
            "Alternative names",
            "Preview attachment",
            "Added at",
            "Modified at",
            "Part name hint",
            "Part name pattern",
            "Internal part number prefix",
            "Default description",
            "Default comment",
            "Disabled Part features",
            "EDA information",
            "Parent assignment"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "rest-api"
        }
      }
    }
  ],
  "references": [
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Parts/Category.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/CategoryController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Controller/AdminPages/BaseAdminController.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Entity/Base/TimestampTrait.php"
    }
  ]
}
---

# Create category — REST primary

## Trigger

The caller submits a unique sibling name and valid comment, keeping the default EDA and naming information.

## Outcome

A distinct Category is saved with its supported information.

---
{
  "kind": "primary",
  "routes": {
    "route": "REST"
  },
  "steps": [
    {
      "text": "The caller requests matching classification record information through this contract’s supported selection.",
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
      "text": "The Product discloses matching Category information through this contract.",
      "kind": "product",
      "actor": "api-client",
      "entities": [
        {
          "entity": "category",
          "effect": "reads",
          "facts": [
            "Name",
            "Comment",
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
      "target": "src/Entity/Base/AbstractStructuralDBElement.php"
    }
  ]
}
---

# Browse categories — REST primary

## Trigger

The caller requests matching classification record information through this contract’s supported selection.

## Outcome

Matching Category records are disclosed.

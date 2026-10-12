---
{
  "kind": "primary",
  "routes": {
    "route": "KiCad library"
  },
  "steps": [
    {
      "text": "The caller requests matching classification record information through this contract’s supported selection.",
      "kind": "actor",
      "actor": "kicad-client",
      "entities": [],
      "contexts": {
        "route": {
          "place": "kicad-library"
        }
      }
    },
    {
      "text": "The Product consults the resolved User permission configuration.",
      "kind": "product",
      "actor": "kicad-client",
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
          "place": "kicad-library"
        }
      }
    },
    {
      "text": "The Product discloses matching Category information through this contract.",
      "kind": "product",
      "actor": "kicad-client",
      "entities": [
        {
          "entity": "category",
          "effect": "reads",
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
            "EDA information"
          ]
        }
      ],
      "contexts": {
        "route": {
          "place": "kicad-library"
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
      "target": "src/Controller/KiCadApiController.php"
    }
  ]
}
---

# Browse categories — KiCad library primary

## Trigger

The caller requests matching classification record information through this contract’s supported selection.

## Outcome

Matching Category records are disclosed.

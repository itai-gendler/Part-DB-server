---
{
  "kind": "primary",
  "routes": {
    "route": "KiCad library"
  },
  "steps": [
    {
      "text": "The caller requests library classifications when the saved library depth is negative.",
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
      "text": "The Product reads the configured library depth from Product settings and returns a synthetic single library entry before querying saved classification records.",
      "kind": "product",
      "actor": "kicad-client",
      "entities": [
        {
          "entity": "product-settings",
          "effect": "reads",
          "facts": [
            "Miscellaneous options"
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
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Services/EDA/KiCadHelper.php"
    },
    {
      "kind": "code",
      "role": "implementation",
      "target": "src/Settings/MiscSettings/KiCadEDASettings.php"
    }
  ]
}
---

# Browse categories — Negative configured depth produces synthetic Part-DB category (KiCad library)

## Trigger

The caller requests library classifications when the saved library depth is negative.

## Outcome

Negative configured depth collapses the category projection into the synthetic Part-DB category.

---
{
  "kind": "validation",
  "routes": {
    "route": "KiCad library"
  },
  "steps": [
    {
      "text": "The caller requests browse categories through this contract.",
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
      "text": "The Product stops the requested browse categories operation at its actual refusal boundary.",
      "kind": "product",
      "actor": "kicad-client",
      "entities": [],
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

# Browse categories — KiCad library refusal

## Trigger

The caller requests browse categories and reaches its closed entry or disabled-control result.

## Outcome

The requested browse categories result is withheld; no accepted change or removal of the requested subject is produced.

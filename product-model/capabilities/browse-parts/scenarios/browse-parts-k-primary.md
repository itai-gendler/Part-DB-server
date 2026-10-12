---
{
  "kind": "primary",
  "routes": {
    "route": "KiCad library"
  },
  "steps": [
    {
      "text": "The caller requests matching component information through this contract’s supported selection.",
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
      "text": "The Product reads the selected Category and returns its eligible Part component projection, including cached stock fields and classification EDA defaults.",
      "kind": "product",
      "actor": "kicad-client",
      "entities": [
        {
          "entity": "part",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "Internal part number",
            "Manufacturer product number",
            "EDA information",
            "Stock summary",
            "Category assignment",
            "Footprint assignment"
          ]
        },
        {
          "entity": "category",
          "effect": "reads",
          "facts": [
            "Name",
            "EDA information",
            "Parent assignment"
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

# Browse parts — KiCad library primary

## Trigger

The caller requests matching component information through this contract’s supported selection.

## Outcome

Matching Parts disclosed through the relevant projection

---
{
  "kind": "primary",
  "routes": {
    "route": "KiCad library"
  },
  "steps": [
    {
      "text": "The caller requests the supported information of one existing selected record.",
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
      "text": "The Product returns the selected Part component details, including its EDA defaults and cached stock fields; collection visibility filtering is not a separate detail refusal.",
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

# Browse parts — KiCad library detail primary

## Trigger

One existing subject is selected for its detail information.

## Outcome

Matching Parts disclosed through the relevant projection

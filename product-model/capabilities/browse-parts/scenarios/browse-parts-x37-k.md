---
{
  "kind": "edge",
  "routes": {
    "route": "KiCad library"
  },
  "steps": [
    {
      "text": "The caller requests direct details for a component omitted from library enumeration by its visibility conditions.",
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
      "text": "The Product retrieves direct Part detail even when that record was omitted from enumeration by EDA visibility.",
      "kind": "product",
      "actor": "kicad-client",
      "entities": [
        {
          "entity": "part",
          "effect": "reads",
          "facts": [
            "Name",
            "Description",
            "EDA information",
            "Stock summary"
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
    }
  ]
}
---

# Browse parts — Enumeration omission does not establish direct-detail refusal (KiCad library)

## Trigger

The caller requests direct details for a component omitted from library enumeration by its visibility conditions.

## Outcome

Enumeration omission does not establish a direct-detail visibility refusal; direct detail follows its own inspected checks.

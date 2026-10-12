---
{
  "kind": "validation",
  "routes": {
    "route": "KiCad library"
  },
  "steps": [
    {
      "text": "The caller requests browse components through this contract.",
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
      "text": "The Product stops the requested browse component operation at its actual refusal boundary.",
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

# Browse parts — KiCad library refusal

## Trigger

The caller requests browse parts and reaches its closed entry or disabled-control result.

## Outcome

The requested browse parts result is withheld; no accepted change or removal of the requested subject is produced.
